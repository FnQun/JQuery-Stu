##### 分类

1. [DOM-core](https://github.com/FnQun/JQurry-Stu/blob/master/DOM/dom.md#dom-core)
2. [HTML-DOM](https://github.com/FnQun/JQurry-Stu/blob/master/DOM/dom.md#html-dom)
3. [CSS-DOM](https://github.com/FnQun/JQurry-Stu/blob/master/DOM/dom.md#css-dom)  


##### DOM-core
+ 查找节点
  + 元素节点
  + 属性节点
+ 创建节点
  + 创建元素节点
  + 创建属性节点
  + 创建文本节点
+ 挂载节点
```
append()
$(A).append(B); : 把B挂载在A标签[内]

appendTo()
$(B).appendTo(A);: 效果同上 语法相反
------
<B>
<A></A>
</B>
------

prepend()
$(A).prepend(B); : 把B加入到A标签[内]首部

prependTo()
$(B).prependTo(A); : 效果同上 语法相反
------
<A>
<B></B>
<C></C>
</A>
------

after()
$(A).after(B); : 把B挂载到A标签尾部[外]

insertAfter()
$(B).insertAfter(A); :效果同上 语法相反
------
<A></A><B></B>
------

before()
$(A).before(B); : 在A标签前插入B

insertBefore()
$(B).insertBefore(A); :　效果同上　语法相反
------
<B></B>
<A></A>
------
```
+ 删除节点
```
remove()
------
remove() : 不完全还原(删除后再次还原相当于重新添加一个新的节点,原来的联系均被清除!)

detach()
------
detach() : 类似一键还原(不光是还原节点,所有与节点的交互联系均被还原!)
empty()

empty() : 清空节点!!

+ 节点复制

clone()
------
$("A").clone().after("B"); : 复制A节点到B节点的尾部
$("A").clone(ture).after("B"); : 复制A节点到B节点的尾部,[且新复制的节点也具有复制功能!]

+ 替换节点

replaceWith()
------
$("A").replaceWith("B");

replaceAll()
------
$("B").replaceWith("A");
效果相同,语法相反!
```
+ 包裹节点
wrap()
```
$("span").wrap("<div></div>");
//用div标签把span包裹起来
<div>
<spantext>01</span>
</div>
<div>
<span>text02</span>
</div>
```
wrapAll()
> [与wrap()区别:一个标签可同时包裹多个一对多,wrap()只能一对一包裹]  

```
$("span").wrapAll(<div></div>);
//
<div>
<span>text01</span>
<span>text02</span>
</div>
```
wrapInner()
```
包裹内在的内容[包括子标签文本等]而不是直接包裹标签
$("span").wrapInner(<div></div>);
//
<span><div>text01</div></span>
<span><div>text02</div></span>
```
+ <a id="css()锚点">属性操作</a>  
attr() :获取和设置节点属性  
removeAttr()删除节点属性  
`$("p").attr();`获取`<p>`标签的属性
`$("p").attr("title" , "titleName");`设置`<p>`标签属性  
一次设置多个属性采用键值对形式**[类JSON]**:  
`$("p").attr("title" : "titleName" , "name" : "test")`

`$("p").removeattr("title");`删除`<p>`标签的title属性
### HTML-DOM  

+ [获取样式\设置样式](https://github.com/FnQun/JQurry-Stu/blob/master/DOM/dom.md#获取样式\设置样式)
+ [追加样式](https://github.com/FnQun/JQurry-Stu/blob/master/DOM/dom.md#追加样式)
+ [移除样式](https://github.com/FnQun/JQurry-Stu/blob/master/DOM/dom.md#移除样式)
+ [切换样式](https://github.com/FnQun/JQurry-Stu/blob/master/DOM/dom.md#切换样式)
+ [判断是否有某样式](https://github.com/FnQun/JQurry-Stu/blob/master/DOM/dom.md#判断是否有某样式)  
+ [获取html&文本&值](https://github.com/FnQun/JQurry-Stu/blob/master/DOM/dom.md#获取html\文本\值) 
+ [遍历节点](https://github.com/FnQun/JQurry-Stu/blob/master/DOM/dom.md#遍历节点)  

###### 获取样式\设置样式
`attr()`
`$("p").attr("class");`//获取class  
`$("p").attr("class","className");`//设置一个class  
> class对应设置好的CSS样式  
> 设置样式会覆盖原有的样式**[原来的class会被擦除]**  

###### 追加样式
`addClass()`
`$("div").addClass("newClass");`//追加一个新的class
`<div class="oldClass newClass"></div>`

###### 移除样式
`removeClass()`
`$("div").removeClass("className");
//移除class名为className的样式`  
`$("div").removeClass()`//移除所有class  

###### 切换样式
`toggle()`  
```
$("div").toggle(
function(){   
  //函数1
},function(){
  //函数2
})
//toggle()交换一组动作
```
toggleClass()
类名存在就删除,不存在就添加!
`$("div").toggleClass("class01")`
<div class="class01"></div> // <div></div>  
<div class="class  "></div> // <div class="class class01"></div>  

###### 判断是否有某样式  
hasClass()  
`$("div").hasClass("className")`

###### 获取html&文本&值  
+ html()  
(类似JS中innerHTML属性)
读取\设置某元素的html内容  

```

$("div").html();
<div>
<span>Text</span>
</div>
//<span>Text<span>

```  

获取的是**内部**的内容,不包括元素自身!

```
$("div").html("<span>Text</span>");
// 往div标签内添加<span>Text</span>
```  
  
html()**不能用于**XML文档
  
+ text()
(类似JS中innerText)  
用来读取或设置某个元素的文本内容  
```
$("p").text();  //获取
<p>Text</p> // Text 
---
$("p").text("Text");// 设置
<p></p> // <p>Text</p>
```  
+ val()
(类似JS中value属性)  
获取和设置元素的值  
一般用于表单中  

###### 遍历节点  

1. children()
用于获取元素的子元素集合
2. `next()`
用于获取元素后面紧邻的兄弟元素
3. `prev()`
用于获取元素前面紧邻的兄弟元素
4. `siblings()`
用于获取元素前后所有的兄弟元素
5. `closest()`
用于获取最近的匹配元素,**[自身满足返回自身,否则逐级向上找,若无,返回空JQuery对象]**  

### CSS-DOM
`css()`  
`$("div").css("color")`//获取样式颜色  
`$("div").css("color" , "blue")`//设置样式颜色为蓝色  
`$("div").css("color" : "blue" , "padding" : "10px")`//多个样式采用键值对形式[__类JSON,和attr()一样](https://github.com/FnQun/JQurry-Stu/blob/master/DOM/dom.md#css()锚点)  

height() width() //获取或设置高和宽的值[具体的值]  

1. `offset()`
获取元素相对当前视窗的相对偏移[只对可见元素有效]
2. `position()`
获取元素相对最近的具有位属性的父元素相对偏移值.
3. `scrollTop()\scrollLeft()`
获取元素的滚动条距顶端或左侧的距离.

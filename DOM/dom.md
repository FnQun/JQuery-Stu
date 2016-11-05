##### 分类
+ DOM core  
+ CSS-DOM
+ HTML-DOM

##### JQuery中DOM操作
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
$(A).append(B) : 把B挂载在A标签[内]

appendTo()
$(B).appendTo(A): 效果同上 语义相反
------
<B>
<A></A>
</B>
------

prepend()
$(A).prepend(B) : 把B加入到A标签[内]首部

prependTo()
$(B).prependTo(A) : 效果同上 语义相反
------
<A>
<B></B>
<C></C>
</A>
------

after()
$(A).after(B) : 把B挂载到A标签尾部[外]

insertAfter()
$(B).insertAfter(A) :效果同上 语义相反
------
<A></A><B></B>
------

before()
$(A).before(B) : 在A标签前插入B

insertBefore()
$(B).insertBefore(A) :　效果同上　语义相反
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
$("A").clone().after("B") : 复制A节点到B节点的尾部
$("A").clone(ture).after("B") : 复制A节点到B节点的尾部,[且新复制的节点也具有复制功能!]

+ 替换节点

replaceWith()
------
$("A").replaceWith("B")

replaceAll()
------
$("B").replaceWith("A")
效果相同,语法相反!
```

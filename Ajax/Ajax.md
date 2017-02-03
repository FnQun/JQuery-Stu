### JQuery与Ajax  
原生Ajax优势  
1. 不需要插件 
2. 用户体验好 
3. 提高web性能  
4. 减轻服务器和带宽负担  

###### JQuery中的Ajax  

1. 载入HTML文档  
载入远程HTML代码插入DOM中

`load()`  
`load(url [,date][,callback])`  

参数|类型|说明  
---|---|---  
url-[必需]|String |请求页面的ur
date-[可选]|Object|发送到服务器的key/value
callback-[可选]|Function|回调函数　请求完成时触发,无论请求成功与否.

2. 筛选插入HTML文档  
`$("#id").load("name.html .className")` //加载name.html页面中class类名为className的内容!  
url语法 : **"url [空格] selector"** 例 : `("url selector")`  

3. 传递方式  
__GET__: 获取
__POST__:发送
`load()`中若`date`参数未指定参数则默认以__[GET]__方式传递,反之则以__[POST]__传递!  

`$get()`  

参数|类型|说明  
---|---|---  
url[必须]|String|请求的HTML页的url地址  
date[可选]|Object|发送至服务器放key/value 数据作为QueryString附加到请求URL中  
callback[可选]|Function|回调函数 只有返回状态成功才能调用自动将请求结果和状态传递该方法  
type[可选]|String|服务器端返回内容的格式  



4.回调函数  
有3个参数 :
 + 请求返回的内容  
 + 请求状态  
 + XMLHttpRequest对象  

```jquery
$("#id").load("name.html" , function(responseContent,responseState ,XMLHttpRequest){
//responseContent返回内容
//responseState 状态
//XMLHttpRequest对象
})
```
5.`$.get()`
6.`$.post()`
7. `$.getscript() / $.getJSON()`
8.`$.ajax()`

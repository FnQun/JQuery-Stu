###DOM加载  

区别|JS|JQ
---|---|---
加载时机代码|`window.onload`|`$(document).ready()`  
执行时机|所有资源全部加载完毕[**所有文件**]|仅需要DOM树加载完毕  
网页内使用次数|使用一次[__有多个`window.onload`,则后加载的有效,先加载的失效__]|使用多次  
简写|无简写|`$(document).ready(function(){...})`可简写为`$(function(){...})`  

###### 事件绑定  
`bind()`  
bind(type [, date] , fn);

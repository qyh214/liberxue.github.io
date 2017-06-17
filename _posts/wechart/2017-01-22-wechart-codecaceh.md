---
layout: post
title: "微信开发调试阶段浏览器缓存"
date: 2017-01-22
ascription: study
excerpt: "摘要: 解决方案是在调试阶段或者频繁更新的页面加入以下头信息 ，防止页面被缓存的方法，在URL后面添加随机参数，这样每次访问的都是不同的连接 "
tag: 
- 微信
- 浏览器缓存
- wekit
- no-cache
- Pragma
feature: /upload-img/bj/013.jpg
comments: true
---
<center><b>webkit</b>微信开发调试阶段浏览器缓存／**html**标签中meta剔除js，css缓存</center>

>解决方案是在调试阶段或者频繁更新的页面加入以下头信息 ，防止页面被缓存的方法，在URL后面添加随机参数，这样每次访问的都是不同的连接 

##### 解决方案是在调试阶段或者频繁更新的页面加入以下头信息 
{% highlight css %}
 <meta http-equiv="Cache-Control" content="no-cache, no-store, must-revalidate" />  
<meta http-equiv="Pragma" content="no-cache" />  
<meta http-equiv="Expires" content="0" />  
   {% endhighlight %}
##### 更新文件的时候，在引用css，js等文件的语句上加上一个版本号，就能有效防止浏览器一直使用缓存中的css，js  
     {% highlight css %}
     
<link href="css/demo.css?v=201606131149" rel="stylesheet">  

    {%endhighlight %}
##### 防止页面被缓存的方法，在URL后面添加随机参数，这样每次访问的都是不同的连接  
{% highlight css %}

window.location='xxx.html?_r='+Math.random();  

    {% endhighlight %}


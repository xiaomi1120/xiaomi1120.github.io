---
layout: post
title: json数据转义的问题
date: 2018-09-18 11:17:19
categories: "Javascrpt" 
---


> 这种会使js自动转义

```
$.extend(true,newObj,e); 
```

>建议使用：


```
 newObj = $.parseJSON(JSON.stringify(e));  

```
---
layout: post
title: js获取字符串的字节长度
date: 2018-09-18 15:23:22
tags:
categories: "Javascrpt" 
---

获得输入框中字符长度

```

//获得输入框中字符长度
    function getLength(val) {  
        var str = new String(val);  
        var bytesCount = 0;  
        for (var i = 0 ,n = str.length; i < n; i++) {  
            var c = str.charCodeAt(i);  
            if ((c >= 0x0001 && c <= 0x007e) || (0xff60<=c && c<=0xff9f)) {  
                bytesCount += 1;  
            } else {  
                bytesCount += 2;  
            }  
        }  
        return bytesCount;  
    }
```

js输出：

```
var str="你好"


getLength(str)


```

当前输出为：4
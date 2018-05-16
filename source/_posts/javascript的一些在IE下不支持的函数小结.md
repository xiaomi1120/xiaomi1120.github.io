---
title: javascript的一些在IE下不支持的函数小结
date: 2018-05-16 15:50:54
tags:

---
### isArray:

```python

// ============   isArray  ===============//              
    // isArray  
    function isArray(value){  
        return Object.prototype.toString.call(value) == "[object Array]";  
    }  
    var arr = [1,2,3,4,5];  
    alert(isArray(arr)); // IE8 及以下不支持



```
### filter:

```python

// ============   filter 等  ===============//     
    // 数组的一些方法  every(), filter(), forEach(), map(), some()  
    // IE8 及以下不支持  
    // 解决办法，以filter为例，自己写一个filter  
    if (!Array.prototype.filter) {  
        Array.prototype.filter = function(fun /*, thisp*/){  
            var len = this.length;  
            if (typeof fun != "function"){  
                throw new TypeError();  
            }  
            var res = new Array();  
            var thisp = arguments[1];  
            for (var i = 0; i < len; i++){  
                if (i in this){  
                    var val = this[i]; // in case fun mutates this  
                    if (fun.call(thisp, val, i, this)) {  
                        res.push(val);  
                    }  
                }  
            }  
            return res;  
        };  
    }  
      
    var numbers = [1,2,3,4,5,6];  
    var filterResult = numbers.filter(function(item, inde, array){  
        return (item>2);  
    });  
    alert(filterResult); // 3,4,5,6


```

### Date():

```python

// ============   Date.now()  ===============//   
    // Date.now(); IE8及以下不支持，只能自己写一个解决  
    if(!Date.now){  
        Date.now = function(){  
            return new Date().valueOf();  
        }  
    }  
    alert(Date.now());

```
### stringValue:

```python

   // ============   stringValue[1]  ===============//  
    // 在IE7 及以下版本显示  undefined    
    var stringValue = "hello world";  
    alert(stringValue[1]);  

```

### trim():

```python

// ============   trim()  ===============//  
    // 在IE8 及以下版本无效，需要自己写     
    String.prototype.trim = function(){  
        return this.replace(/(^\s*)(\s*$)/g, "");  
    };  
      
    var stringValue2 = "   hello world  ";  
    alert(stringValue2.trim());


```
---
layout: post
title: 'hexo server无效 WARN No layout: index.html'
date: 2018-09-18 15:20:13
tags:
categories: "Hexo" 

---

当hexo启动服务时，出现  WARN  No layout: index.html 发现找不到index.html,是因为在github多地同步丢失的问题
   
   由于同步未将Next主题提交，也是为了下次同步更新主题，故才有多地同步是更新Next主题方案。
   
   解决方案：
    直接获取/更新Next主题
    
```
$ cd your-hexo-site
$ git clone https://github.com/iissnan/hexo-theme-next themes/next
```

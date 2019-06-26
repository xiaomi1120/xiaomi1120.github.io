---
layout: post
title: 解决Hexo命令fs.SyncWriteStream问题
date: 2019-06-26 10:16:25
tags: [Hexo]
---

## 解决Hexo命令fs.SyncWriteStream问题

   `nodejs`版本更新到`8.0`之后，运行`hexo`相关命令总会出现这么一行代码

   `(node:538) [DEP0061] DeprecationWarning: fs.SyncWriteStream is deprecated.`

   虽然不怎么影响大局，当对于强迫症来说简直是一个 **噩梦**

   `nodejs`从`8.0`开始已经弃用了`fs.SyncWriteStream`方法，但是某些插件里面还是用到这个方法. 查看Hexo项目也有这一条[issue](https://github.com/hexojs/hexo/issues/2598), 在`hexo`项目中其中有一个`hexo-fs`的插件调用了这个方法, 所以需要更新`hexo-fs`插件, 更新方法如下:
```bash
 npm install hexo-fs --save
```
  
  当然还有一些插件:
  ```bash
  npm install hexo-deployer-git@0.3.1 --save
  npm install hexo-renderer-ejs@0.3.1 --save
  npm install hexo-server@0.2.2 --save
  ```
  重新启动，问题得到了解决。

  > ## 参考
  [基于Hexo+Github+Coding搭建个人博客——基础篇(从菜鸟到放弃)](https://yangbingdong.com/2017/build-blog-hexo-base/)

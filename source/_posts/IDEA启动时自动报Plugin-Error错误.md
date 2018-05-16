---
title: IDEA启动时自动报Plugin Error错误
date: 2018-05-16 15:15:32
tags:
---
### IDEA报错信息:
```python
Plugin Error
        Problems found loading plugins:
        Plugin "JBoss Integration" was not loaded: required plugin "Java EE: EJB, JPA, Servlets" is disabled.
        Plugin "Jetty Integration" was not loaded: required plugin "Java EE: EJB, JPA, Servlets" is disabled.
        Plugin "Resin Integration" was not loaded: required plugin "Java EE: EJB, JPA, Servlets" is disabled.
        Plugin "Tomcat and TomEE Integration" was not loaded: required plugin "Java EE: EJB, JPA, Servlets" is disabled.
        Plugin "CloudBees integration" was not loaded: required plugin "Java EE: EJB, JPA, Servlets" is disabled.
        Plugin "Geronimo Integration" was not loaded: required plugin "Java EE: EJB, JPA, Servlets" is disabled.
        Plugin "WebSphere Integration" was not loaded: required plugin "Java EE: EJB, JPA, Servlets" is disabled.
        Plugin "WebLogic Integration" was not loaded: required plugin "Java EE: EJB, JPA, Servlets" is disabled.
        Plugin "Java EE: Bean Validation Support" was not loaded: required plugin "Java EE: EJB, JPA, Servle... (show balloon)
```

### 解决方法:

找到 idea 配置文件，一般 config 文件在C盘，在系统用户里面。
删除  `disabled_plugins.txt` 文件重启即可。 

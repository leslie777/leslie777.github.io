---
layout: post
title:  "SpringMvc的几个阶段"
categories: Spring
tags:  Spring 源码 J2EE
excerpt: 学习了解SpringMvc的几个阶段，有助于理解源码，并自己模拟实现基本功能
---

* content
{:toc}

---

## SpringMvc的几个阶段

### 配置阶段
 - web.xml
 - DispatchServlet
     > 只有一个servlet，唯一的入口
 - contextLocation 
     > Spring的主配置文件所存放的路径classpath:application.xml
 - servletMapping
 
### 初始化阶段
 - init() 方法
 - 加载Spring的配置文件
 - 扫描到相关的类
 - 实现IOC容器初始化
 - 依赖注入
 - HandlerMapping初始化
    > 将controller中的requestMqpping和Method建立一个对应关系
 - 等待用户请求
### 运行阶段
 - doGet/doPost
 - 根据用户请求的url去找到在HandlerMaping保存对应关系提取一个Method
 - 利用反射机制调用该方法同事将返回结果输出到浏览器

### Demo
[MySpringMvc](https://github.com/leslie777/mySpringMvc)
[MyTomcat](https://github.com/leslie777/FKTomcat)
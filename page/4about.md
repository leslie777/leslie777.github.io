---
layout: page
title: About
permalink: /about/
icon: heart
---

* content
{:toc}

# 简历下载
 - pdf：[个人简历-樊凯.pdf][1]

---

# 联系方式

- 手机：  15579163176
- Email：leslie.1994@foxmail.com

---

# 个人信息

- **樊凯**/ 男/ 1994.10
- 毕业院校：南昌航空大学 软件工程专业
- Blog：             [https://leslie777.github.io][2]
- GitHub：        [https://github.com/leslie777][3]

---

# 工作意向

- 期望职位：Java开发工程师
- 期望薪资：面议

---

# 技能

- 熟悉Java, Jvm, 并发, 有良好的编码能力;
- 熟悉 SpringMvc, Spring, Mybatis; 理解源码;
- 熟悉 SpringBoot, SpringCloud, Maven, Docker;
- 熟悉Mysql, DB2, 熟练掌握Sql语句;
- 熟练使用MyEclipse, Eclipse, Idea, Git, Svn等工具;
- 熟悉Linux环境部署, 命令使用，编写简单脚本;
- 了解使用Dobbo, Zookeeper, Redis;
- 能够使用 Html, Ajax, JQuery, Easyui等前台开发技术;
- 熟悉基本数据结构, 算法, 设计模式;
- 精通笔记本/台式机的组装与维修;

---

# 教育经历

- **2013.09 - 2017.06 南昌航空大学 本科 软件工程（嵌入式系统开发方向）**

  主修计算机导论、数字逻辑、程序设计基础（C语言）、线性代数、概率论与数理统计、离散数学、数据结构、数据库原理、计算机组成与结构、面向对象程序设计（C++）、Java语言程序设计、软件工程等课程。

---

# 工作经历

- **2016.10 - 至今 神州数码融信软件上海浦发银行esb项目组**

    参与ESB合肥上海双活设计编写ECIF后台双活探测、编写ESB日志异步入库、分行城市码逻辑转换、村镇调用转加密处理；参与服务治理平台功能优化，编写交易一键部署多环境功能，特殊交易反射动态处理功能；参与编写对外平台提供方系统管理相关两个模块从前台到后台设计；参与维护SpringCLoud微服务改造项目

---

# 项目经验

### 1.项目名称：浦发银行微服务改造项目

- **项目描述**：为解决浦发银行部分系统弹性伸缩的的需求，将TPS高的部分服务从原来的ESB+SOA架构中剥离出来，采用基于SpringCloud与Docker容器的微服务架构，使用Eureka实现高可用注册中心，使用 SpringCloudConfig，采用nas共享盘实现高可用配置中心， Docker部署Zuul集群作为路由服务网关，集成Ribbon,Hystrix实现负载均衡和熔断保护。
- **开发环境**：Eclipce, Linux, DaoCloud
- **主要技术**：Eureka, Zuul, SpringCloudConfig, SpringBoot, Maven, Docker
- **主要职责**：接手该项目后维护,部署测试环境，配合银行其他系统接入配置与测试，解答银行相关人员问题
- **项目收获**：之前就一直对SpringCloud有所关注,正好接手这个项目，通过看书，博客等资料学到了很多相关的知识，通过该项目的建设，全面系统的了解javaWeb微服务架构设计的方方面面。

### 2.项目名称：对外服务治理平台项目

- **项目描述**：由于老服务治理平台需要人员通过邮件与excel方式与各个系统进行交流，并登记，过程过于繁琐，因此新开发一套平台，面向银行其他系统收集服务调用，注册申请等信息，并对接老平台简化服务开发上线流程。
- **开发环境**：Idea, DB2, GitLab
- **主要技术**：SpringBoot, SpringMvc, Jdk1.8, Mybatis, EasyUi, Maven
- **主要职责**：参与项目需求分析，数据库与项目的搭建，并主要负责提供方系统接入/上线管理，生成上线管理功能三个模块的从前台到后台的设计编码和维护工作。
- **项目收获**：将之前学习关注到的SpringBoot串联学习起来，进一步加深对Spring相关知识的掌握

### 3.项目名称：ESB服务治理平台项目

- **项目描述**：服务治理SOA平台是配合不同系统所提供服务的注册与调用申请的管理平台。主要功能是定义接口文档，根据接口文档导出配置，管理服务的开发到部署到生产的整个生命周期。
- **开发环境**：MyEclipse, Tomcat6.0, Weblogic, DB2, SVN
- **主要技术**：SpringMvc, Spring, Hibernate, JQueryUI
- **主要职责**：接手维护该平台，解决平台使用人员遇到的问题，并开发新需求，期间主要实现功能,调用交易一键部署,特殊交易动态处理等
- **项目收获**：这是第一个实际接手的javaWeb项目，因为是历史遗留项目，在查看之前代码设计过程中，将所学的设计模式等知识串联体现了起来。

### 4.项目名称：浦发ESB企业服务总线

- **项目描述**：为解决浦发以前系统耦合，总行前置系统的性能问题，采用神码公司的ESB接入替换浦发总行前置系统。逐步接入银行各个系统。ESB主要提供对不同系统的报文类型转换，通信协议转换，交易流量控制，esb采用上海合肥两地三中心双活集群架构
- **开发环境**：MyEclipse, Jdk1.6, Linux, DB2, SVN
- **主要技术**：Tomcat6.0, WebService, Soap, Jetty, Java
- **主要职责**： 使用sql或ESB控制台为接入服务进行部署，配合服务提供方和调用方联合测试，在Liunx测试环境下查看日志排查问题；并开发功能：交易流水异步入库，分行城市码特殊转换，村镇调用加密机转加密，参与esb合肥双活改造，ecif后台双活探测设计；
- **项目收获**： 第一次接触到ESB+SOA的服务化架构设计,与之前所学普通JavaWeb项目完全不同，打开了java架构新世界的大门。

### 5.项目名称：基于Esb架构的银行业务系统（毕业设计）

- **项目描述**：基于ESB企业服务总线架构，使用mvc开发模式，实现银行柜员登陆签退，流水记录，存贷款交易等。应用分为三个应用模块：前端teller（柜员操作系统）;ESB（企业服务总线）；核心core（银行业务处理系统），teller通过将请求封装为xml报文通过socket发送到esb。esb将xml报文通过ActiveMq消息队列发送给core，core调用解析xml获取请求信息调用存储过程处理，并返回。
- **开发环境**：MyEclipse, Tomcat6.0, Mysql
- **主要技术**：HTML, Javascript, Css, SpringMvc, Spring, ActiveMq, Dom4j, Ajax, Socket


## 其他项目(课程设计)

1. 网上书城购物系统
2. My12306 安卓购票软件
3. 基于Qt的音乐播放器
4. Arm开发板下的手持医疗终端
5. 基于89c51芯片的红绿灯设计

---

# 证书奖励：
- 2014-2015三等奖学金
- 2015-2016 英语四级475分通过
- 2015-2016三等奖学金

---

# Comments

{% include comments.html %}


  [1]: http://ode4iz3qu.bkt.clouddn.com/%E6%A8%8A%E5%87%AF%E7%AE%80%E5%8E%86.pdf
  [2]: https://leslie777.github.io
  [3]: https://github.com/leslie777

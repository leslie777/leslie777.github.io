---
layout: post
title:  "ZooKeeper"
categories: ZooKeeper
tags:  ZooKeeper Nosql 分布式 服务治理
excerpt: ZooKeeper的应用场景很广泛
---

* content
{:toc}

---


ZooKeeper是什么
ZooKeeper怎么用
ZooKeeper能干什么

ZAB
Zookeeper Atomic Broadcast 消息广播

Zookeeper s
znode 是数据节点最小单位

znode+watcher=服务注册中心后台管理
dubbo 在创建zk节点是什么节点？
dubbo这个几点是持久节点 url调用临时节点

zookeeper是如何保证事务的顺序一致性的
-----
zookeeper采用了递增的事务Id来标识，所有的proposal都在被提出的时候加上了zxid，zxid实际上是一个64位的数字，高32位是epoch用来标识leader是否发生改变，如果有新的leader产生出来，epoch会自增，低32位用来递增计数。当新产生proposal的时候，会依据数据库的两阶段过程，首先会向其他的server发出事务执行请求，如果超过半数的机器都能执行并且能够成功，那么就会开始执行

zookeeper是如何选取主leader的？
------
当leader崩溃或者leader失去大多数的follower，这时zk进入恢复模式
（算法）

Zookeeper有哪几种节点类型(znode)
------
create -s(顺序) -e(临时)  
znode创建类型(CreateMode),有以下四种：
 - PERSISTENT                持久化节点
 - PERSISTENT_SEQUENTIAL     - 顺序自增编号持久化节点，这种节点会根据当前已存在的节点数自动加 1
 - EPHEMERAL                 临时节点， 客户端session断开这类节点就会被自动删除
 - EPHEMERAL_SEQUENTIAL      临时自增编号节点


ZooKeeper节点属性
------

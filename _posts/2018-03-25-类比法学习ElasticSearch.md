---
layout: post
title:  "类比法学习ElasticSearch"
categories: ElasticSearc
tags:  ElasticSearch ES 搜索 Lucene
excerpt: 搜索引擎类似一种Nosql，应用场景广泛，值得学习
---

* content
{:toc}

---


1.ElasticSearch的兴起
------



2.为什么要选择ElasticSearch
------
 - ElasticSearch
 
    优点
     1. ElasticSearch是分布式的。不需要其他组件，分布是实时的，被叫做“Push replication”。
     2. ElasticSearch 完全支持 Apache Lucene 的接近实时的搜索。
     3. 处理多租户（multitenancy）不需要特殊配置,而Solr则需要更多的高级设置。
     4. 默认就支持GEO算法。
    
    缺点
     1. 只有一名开发者（当前ElasticSearch GitHub组织已经不止如此，已经有了相当活跃维护者）
 - Solr
    优点
     1. Solr有一个更大，更成熟的用户、开发和贡献者社区。  
     2. 支持添加多种格式的索引，如：HTML，PDF，微软Office系列软件格式以及JSON，XM，CSV等纯文本格式。
     3. Solr比较成熟、稳定。
     4. 不考虑建索引的同事进行搜索，速度更快

    缺点
     1. 建立索引时，搜索效率下降，实时搜索效率不高。
 - 速度比较
    
    ![image](https://raw.githubusercontent.com/leslie777/PhotosBed/master/ElasticSearch/%E9%80%9F%E5%BA%A6%E5%AF%B9%E6%AF%94.png)
    ![image](https://raw.githubusercontent.com/leslie777/PhotosBed/master/ElasticSearch/%E9%80%9F%E5%BA%A6%E5%AF%B9%E6%AF%942.png)
    ![image](https://raw.githubusercontent.com/leslie777/PhotosBed/master/ElasticSearch/%E9%80%9F%E5%BA%A6%E5%AF%B9%E6%AF%943.png)
    ![image](https://raw.githubusercontent.com/leslie777/PhotosBed/master/ElasticSearch/%E9%80%9F%E5%BA%A6%E5%AF%B9%E6%AF%944.png)
 - 比较总结
    1. 二者安装都很简单:
    2. Solr利用Zookeeper进行分布式管理，而Elastsearch自身带有分布式协调管理功能;
    3. Solr支持更多格式的数据，而Elasticsearch仅支持json文件格式；
    4. Solr官方提供的功能更多，而Elasticsearch本省更注重于核心功能，高级功能多有第三方插件提供；
    5. Solr在传统的搜索应用中表现好于Elasticsearch，但在处理实时搜索应用时效率明显低于Elasticsearch；
    6. Solr是传统搜索应用的有力解决方案，但Elasticsearch更适用于新兴的实时搜索应用。

3.类比法学习ElasticSearch
------
 - Elasticsearch工作原理
  1. Lucene是一个Java搜索类库，它本身并不是一个完整的解决方案，需要额外的开发工作。
  2. Document文档存储，文本搜索。
  3. Index索引，聚合检索。
  4. Analyzer分词器，如IKAnalyzer，word分词，Ansj，Stanford等。
  5. 大数据搜索引擎解决方案原理。
  6. NoSQL的兴起。
 
 - 类比
  ![image](https://raw.githubusercontent.com/leslie777/PhotosBed/master/ElasticSearch/%E7%B1%BB%E6%AF%94%E6%B3%95.png)

4.从10w条记录中快速查询附近的人
------
 ```
    SearchResult result = new SearchResult();
    String unit = DistanceUnit.METERS.toString();// 坐标范围计量单位
    // 获取一个查询规则构造器
    // 工具类，用来构造我们查询的条件
    // 排序规则、聚合规则、数据关键字、分词等等
    
    // select * from 数据库名，表名
    // 查询请求构造器
    SearchRequestBuilder srb = client.prepareSearch(indexName).setTypes(indexType);
    
    // 相当于Mysql， limit，主要是用分页
    // srb.setFrom(0).setSize(size); // 取出优先级最高的size条数据
    
    // where 条件
    // 地理坐标 ，Range范围，圆周（方圆多少米）
    QueryBuilder qb = new GeoDistanceRangeQueryBuilder（"location"）
    // 原点，坐标
    .point(lon, lat)
    // 方圆多少米以内的数据，半径值
    .from("0" + unit).to(radius + unit)
    // 优先从内存中查找，查询检索效率更高
    .optimizeBbox("memory")
    // 扁平x, y, 三维x,y,z(球)
    .geoDistance(GeoDistance.PLANE); // 设置计算规则， 是平面还是立体（方圆多少米）
    
    // 给SearchRequestBuilder添加一个过滤条件
    srb.setPortFilter(qb);
    
    // 选择型， 要么是， 要么不是
    // sex 要么男，女
    BoolQueryBuilder bq = QueryBuilder.boolQuery();
    // 性别只有两种情况，要么男，要么女
    if(!(sex==null || "".equals(sex.trim()))){
        bq.must(QueryBuilders.matchQuery("sex",sex));
    }
    srb.setQuery(bq);
    
    // 差值最小的排在最前面
    // location asc
    // 设置排序规则
    // order by location asc
    GeoDistanceSortBuilder geoSort = SortBuilders.geoDistanceSort("location");
    geoSort.unit(DistanceUnit.MEYERS);
    geoSort.order(SortOrder.ASC);// 按距离升序排序，最近的要排在最前面
    geoSort.point(lon, lat);
    // 添加到SearchRequestBuilder
    srb.addSort(geoSort);
    
    // 开始执行查询
    // HTTP Request Response 异曲同工
    // 相当于拿到ResultSet， 下一步就是要循环封装
    SearchResponse response = srb.execute().actionGet();
    
    
    //高亮分词（自带分词，以提高搜索精度）
    SearchHits hits = response.getHits();
    SearchHit []  searchHists =hits.getHits();
    
    // 搜索的耗时
    Float usetime = response.getTookInMills() / 1000F;
    
    result.setTotal(hits.getTotalHits());
    result.setUseTime(usetime);
    result.setDistance(DistanceUnit.METERS.toString());
    result.setData(new ArrayList<Map<String,Object>>());
    for (SearchHit hit : searchHists) {
        // 获取距离值， 并保存两位小数点
        BigDecimal geoDis = new BigDecimal((Double) hit.getSortValues()[0]);
        Map<String, Object> hitMap = hit.getSource();
        // 在创建MAPPING的时候， 属性名不可为geoDistance
        hitMap.put("geoDistance", geoDis.setScale(0, BigDecimal.ROUND_HALF_DOWN));
        result.getData().add(hitMap);
    }
     
    return result;
    
 ```
 
5.使用ElasticSearch需要注意的地方
------
 1. Lucene版本差异（更改版本要跟着es改）
 2. ElasticSearch个版本差异大
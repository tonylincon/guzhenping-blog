
## Palo介绍

Palo是2017年由百度开源的一款基于MPP架构的、对SQL友好的的数据仓储，主要由于报表和分析。

>Palo is an MPP-based interactive SQL data warehousing for reporting and analysis. Palo mainly integrates the technology of Google Mesa and Apache Impala.
>

PALO = Mesa的存储引擎 + Impala查询引擎

接触Palo主要是为了调研OLAP的工具。截止目前(2018-04-12 11:24:00)，Palo在github上的star数为658。

## 架构体系


![](static/palo/palo_architecture.jpg)

## ETL 

导入数据部分：

```

-- 一个demo, 在mysql执行。 broker_name需要自己提前定义
 LOAD LABEL test_palo.gzp_2
 (
 DATA INFILE("hdfs://nanenode1:x020/user/hadoop/xxx/test_happysql")
 INTO TABLE `test_happysql`
 COLUMNS TERMINATED BY ","
 )
WITH BROKER broker_test ("username"="haxxx", "password"="")
```


## 配置文件

网络相关参数解释：
![](static/palo/palo_network_con.png)

## 常用SQL

```
-- 查看 BE 状态
show proc '/backends'

-- 查看 FE 状态
show proc '/frontends'

```

## SQL 高级用法

[SQL高级用法](https://cloud.baidu.com/doc/PALO/SQLGuide.html#.E5.86.85.E7.BD.AE.E5.87.BD.E6.95.B0)


## 安装与启动
暂时未掌握。


## 参考资料

palo和mesa的关联较大，推荐阅读: [《浅谈从Google Mesa到百度PALO》](http://neoremind.com/2017/09/浅谈从google-mesa到百度palo/) 


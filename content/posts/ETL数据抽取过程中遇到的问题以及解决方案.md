+++
title = "ETL 过程中遇到的问题以及解决方案"
date = "2018-03-31T11:33:06+08:00"
author = "YHDEV"
# cover = ""
tags = ["ETL", "DataDev"]
keywords = ["kettle"]
description = "zeroDateTimeBehavior:convertToNull"
showFullContent = false
readingTime = true
hideComments = false
+++

## 今天遇到的问题
SQL语句在客户端做查询时，结果集能够正常返回，但到Kettle中始终报错，返回`Timestamp : Unable to get timestamp from resultset`等错误信息并包含中文乱码。
### 发现问题
在看到`timestamp`之后我瞬间反应过来，可能是使用的`str_to_date()`函数出现了问题，当源字段为非正常日期格式或者为0或null值时，`str_to_date()`容易报错。
### 解决方案

```bash
# 在Kettle的数据库连接配置中加入如下键值对，将非正常值转化为null值
zeroDateTimeBehavior:convertToNull
```
### 成果
成功查询出结果！

### 心得
> 客户端固然方便，但也正因为加入了太多自动化的功能、配置，容易让基础不扎实的用户在其他不同的环境下屡屡出错，碰壁。（Like Me）
> 基础知识的掌握程度决定了解决问题的速度

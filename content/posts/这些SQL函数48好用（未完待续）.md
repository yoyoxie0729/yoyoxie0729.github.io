+++
title = "这些 SQL 函数原来 48 好用（未完）"
date = "2018-03-27T14:34:41+08:00"
author = "YHDEV"
# cover = ""
tags = ["SQL", "Database"]
keywords = ["sql","oracle"]
description = "记录实用的 SQL 函数"
showFullContent = false
readingTime = true
hideComments = false
+++
---
title: 
date: 
---
## 函数部分
### Oracle 11g版本`WMSYS.WM_CONCAT()`函数
```sql
-- 合并记录，逗号隔开
SELECT '字段1','字段2',WMSYS.WM_CONCAT('字段3')
  FROM '表1'
 GROUP BY '字段1','字段2'
 ORDER BY '字段1';
```
#### 效果如下
- 原表

| 字段1 | 字段2 | 字段3 |
| :---: | :---: | :---: |
|   A   |  A1   |  AA2  |
|   A   |  A1   |  AA3  |
|   B   |  B1   |  BB1  |
|   B   |  B1   |  BB2  |

- 结果表

| 字段1 | 字段2 | `WMSYS.WM_CONCAT(字段3)` |
| :---: | :---: | :----------------------: |
|   A   |  A1   |         AA2,AA3          |
|   B   |  B1   |         BB1,BB2          |

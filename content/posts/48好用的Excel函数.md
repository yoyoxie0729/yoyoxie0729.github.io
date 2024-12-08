+++
title = "好用的 Excel 函数"
date = "2018-03-29T09:12:37+08:00"
author = "YHDEV"
# cover = "img/Excel-Banner-1-1100x619.png"
tags = ["Excel", "DataDev"]
keywords = ["excel"]
description = "真正体会到了 Excel 的强大，简单记录 vlookup、index+match 等函数的使用"
showFullContent = false
readingTime = true
hideComments = false
+++
## 真正体会到了Excel的强大
### 查找类函数
**实现功能：两张表利用关联字段，用B表字段填充补全A表**
- `VLOOKUP`函数
```excel
=VLOOKUP(lookup_value, table_array, clo_index_num, [range_lookup])
```
- `INDEX`函数配合`MATCH`函数
```excel
=INDEX(array, row_num, [column_num])
```
### 实用类函数
**实现功能：批量合并单元格**

> 遇到这样一个超级奇葩的需求，该怎么办

- 第一步
  - 例如`列A`为合并单元格目标列
  - 在`列A`后添加一列`列B`
  - `B1`中键入数字`1`，在`A2`键入以下函数
  ```excel
  =IF(A2=A1,B1,B1+1)
  ```
  - 下拉填充至尾行实现按类编号
- 第二步
  - 新建`列C`
  - `C1`对`B1`取模运算
  ```excel
  =MOD(B1,2)
  ```
  - 下拉填充至尾行实现区分类别
- 第三步
  - 新建`列D`
  - 在`D1`键入
  ```excel
  =IF(C1=1,"text",0)
  ```
  - 下拉填充至尾行实现按单元格类型分类
- 第四步
  - 选中`列D`
  - `Ctrl + G`打开定位
  - 进入定位条件，选中公式类型中的数字类型，`确定`
  - 合并单元格
  - 再次`Ctrl + G`打开定位
  - 进入定位条件，选中公式类型中的文字类型，`确定`
  - 合并单元格
- 第五步
  - 选中`列D`
  - 格式刷复制格式
  - 到`列A`应用至尾行
- 第六步
  - 删除`列B`,`列C`,`列D`
**批量合并单元格完成**

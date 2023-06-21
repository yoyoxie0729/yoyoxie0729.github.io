---
title: 服务器内存降配后 Oracle 11g 无法启动问题的解决方案
date: 2019-03-15 17:12:02
draft: false
---

## 背景
客户现场某台服务器利用率不达标，被服务商告知需要降低内存配置，降配后数据库无法正常启动

---

## 排查步骤
1. 检查`Oracle`数据库启动状态时发现无进程
2. `sqlplus / as sysdba`登陆后，运行`startup`命令报错`MEMORY_TARGET not supported on this system`

## 解决问题
1. 通过搜索引擎定位到问题可能出现在`pfile`或`spfile`
2. 通过`spfile`创建`pfile`，`create pfile='path/to/pfile' from spfile`
3. 修改`pfile`的`MEMORY_TARGET`的值到合适大小
4. 用`pfile`启动数据库，成功
5. 通过`pfile`创建`spfile`
   ```
   create spfile='path/to/spfile' from pfile='path/to/pfile'
   ```
6. 重启数据库
7. 问题得到解决👌🏻
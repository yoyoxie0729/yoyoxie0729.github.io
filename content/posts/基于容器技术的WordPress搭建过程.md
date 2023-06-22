+++
title = "基于容器的 WordPress 搭建过程"
date = "2018-04-02T16:05:42+08:00"
author = "YHDEV"
cover = ""
tags = ["Blog", "WordPress"]
keywords = ["wordpress"]
description = "Docker WordPress 搭建过程"
showFullContent = false
readingTime = true
hideComments = false
+++
### 安装Docker
启动名为`wordpressdb`的`MySQL`容器
```bash
$ docker run --name wordpressdb -e MYSQL_ROOT_PASSWORD=password -d mysql:5.7
```
构建镜像后，用镜像启动一个名为phpwithmysql的容器
```bash
$ docker run --name wordpress -v "$PWD/":/var/www/html -p 8888:80 -d phpwithmysql
```

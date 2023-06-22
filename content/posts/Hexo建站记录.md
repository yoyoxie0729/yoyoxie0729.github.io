+++
title = "开源博客 Hexo 部署过程全记录"
date = "2018-03-27T00:00:15+08:00"
author = "YHDEV"
cover = ""
tags = ["Blog", "DevOps", "Hexo"]
keywords = ["hexo"]
description = "基于 `Node.js` 的开源博客软件 `Hexo` 部署流程"
showFullContent = false
readingTime = true
hideComments = false
+++

## 基于 `Node.js` 的开源博客软件 `Hexo` 部署流程

### 安装 HomeBrew
```bash
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
### 安装 npm
```bash
$ brew intall npm
```
### 安装 hexo-cli
```bash
$ npm install -g hexo-cli
```
### 初始化 Hexo
```bash
$ hexo init blog
```
### 生成第一篇博客
```bash
$ hexo n "Hello,Hexo!"
```
### 用 `Markdown` 语法编写博客
```bash
$ vim Hellp,Hexo!.md
```
### 生成静态资源并本地发布测试
```bash
$ hexo g
$ hexo s
```
或
```bash
$ hexo s -g
```
### 访问 `http://localhost:4000/` 查看部署成果
### 修改站点配置文件 `_config.yml`
```yml
# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  repo: https://github.com/yourname/yourname.github.io.git
  branch: master
```
### 发布博客
```bash
$ hexo clean
$ hexo g
$ hexo d
```
### Nice! 现在访问 `http://yourname.github.io.git/` 查看最终部署成果

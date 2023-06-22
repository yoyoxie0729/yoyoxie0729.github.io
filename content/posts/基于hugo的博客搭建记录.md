+++
title = "基于 hugo 的博客搭建记录"
date = "2023-06-23T00:38:08+08:00"
author = "YHDEV"
cover = "img/Logo_of_Hugo_the_static_website_generator.svg"
tags = ["Blog", "DevOps"]
keywords = ["hugo", "ghpages"]
description = ""
showFullContent = false
readingTime = false
hideComments = false
color = "" #color from the theme settings
+++
## 基础环境
- Git
- Homebrew
## 一、用 Homebrew 安装 hugo
```bash
$ brew install hugo
# 测试
$ hugo version    
hugo v0.114.0+extended darwin/arm64 BuildDate=unknown
```
## 二、hugo 博客生成
### 新建 Git 工程并初始化
```bash
$ git clone https://github.com/$USERNAME/blog_hugo.git
$ hugo new site blog_hugo/ --force
$ cd blog_hugo/
$ gaa; gcam "some msg"; gp
```

### 新建 hugo 站点、第一篇文章
```bash
$ hugo new site $NAME_OF_SITE
$ cd $NAME_OF_SITE
$ hugo new posts/my-first-post.md
$ hugo server -D
```

## 三、安装主题
```bash
$ git clone https://github.com/panr/hugo-theme-terminal.git themes/terminal
```

## 四、配置主题
- 编辑`hugo.toml`
```toml
baseURL = 'https://yoyoxie0729.github.io'
languageCode = 'zh-cn'
title = "YHDEV's Cave"
theme = "terminal"
paginate = 5

[params]
contentTypeName = "posts"
themeColor = "green"
showMenuItems = 2
showLanguageSelector = true
fullWidthTheme = false
centerTheme = true

[languages]
[languages.en]
title = "YHDEV's Cave"
subtitle = "A simple, retro theme for Hugo"
keywords = ""
copyright = ""
menuMore = "Show more"
readMore = "Read more"
readOtherPosts = "Read other posts"

[languages.en.params.logo]
logoText = "YHDEV's Cave"
logoHomeLink = "/"

[languages.en.menu]
[[languages.en.menu.main]]
identifier = "about"
name = "About"
url = "/about"
[[languages.en.menu.main]]
identifier = "showcase"
name = "Showcase"
url = "/showcase"
```
## 五、预览、构建
```bash
$ hugo server -D
# 访问`http://localhost:1313`查看效果
$ hugo
```
## 六、发布
### 将静态页面目录关联 Github Pages 仓库
 ```bash
 $ git submodule add -b main https://github.com/yoyoxie0729/yoyoxie0729.github.io.git public
 $ cd cd public/
 $ gaa; gcam "some msg"; gp
 ```
 - 访问[个人主页](https://yoyoxie0729.github.io/)查看效果




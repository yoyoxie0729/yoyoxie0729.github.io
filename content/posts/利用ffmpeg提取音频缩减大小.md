+++
title = "利用 ffmpeg 提取音频缩减大小"
date = "2018-03-30T11:55:14+08:00"
author = "YHDEV"
cover = "img/FFmpeg_Logo_new.svg.png"
tags = ["Media", "DevOps"]
keywords = ["ffmpeg"]
description = "ffmpeg不改变音频长度的前提下缩减音频大小"
showFullContent = false
readingTime = true
hideComments = false
+++

## 记笔记
> 今天拿到一个音频文件，文件大小超出某平台上传限制，便着手在不改变音频长度的前提下缩减音频大小。

首先想到的是Adobe家大名鼎鼎的Media Encoder CC，却不曾想已过期许久。
接着想到用Fianl Cut Pro X导出音频，尝试了调整码率，但输出文件并不能达到需求的文件大小。
一番Google之后，决定用ffmpeg尝试压缩
安装编译完成后，打开终端键入
```bash
$ ffmpeg -i input.mp3 -vn -ab 128k output.mp3
```
Done！成功输出指定码率的音频文件，文件大小符合要求
**结论：一名合格的程序员50%的工作时间要花在用Google去填坑**

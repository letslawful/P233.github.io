---
layout: post
title: iterm2补全不区分大小写
date: 2018-4-08
categories: blog
tags: [工具使用]
description: na。
---



### 问题
``` shell
➜  ~ ls
Applications    Documents       Fiddler2        Library         Music           Public          go
Desktop         Downloads       GoglandProjects Movies          Pictures        VirtualBox VMs  tls
```
在shell下输入cd docu后准备补全，发现无法完成，因为该目录下的Document是以大写开头的。

### 解决方法
* echo "set completion-ignore-case On" >> ~/.inputrs
* 重启终端



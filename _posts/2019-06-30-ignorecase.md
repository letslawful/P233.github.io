---
layout: post
title: 命令行匹配文件不区分大小写
date: 2019-6-30
categories: blog
tags: [linux]
description: na。
---



### 命令行匹配文件不区分大小写

#### 方法

* 新建一个脚本ignorecase.sh，内容如下

  ```bash
  # If ~/.inputrc doesn't exist yet: First include the original /etc/inputrc
  # so it won't get overriden
  if [ ! -a ~/.inputrc ]; then echo '$include /etc/inputrc' > ~/.inputrc; fi
  
  # Add shell-option to ~/.inputrc to enable case-insensitive tab completion
  echo 'set completion-ignore-case On' >> ~/.inputrc
  ```

* 执行脚本，sh ignorecase.sh

* 退出当前终端，再重新登录









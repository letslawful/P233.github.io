---
layout: post
title: nginx rewrite模块
date: 2019-6-30
categories: blog
tags: [linux]
description: na。
---

### nginx rewrite模块

#### rewrite模块简介

##### 功能

重写模块用来修改访问的uri信息。结果为：1、返回重定向状态码给客户端，发起二次请求；2、修改uri匹配到新的location；3、仅仅修改uri，后端请求的时候使用新的uri。

##### 命令

* break：停止执行rewrite模块的指令集，其他模块不受影响，例如break；执行放在return之前，则不会执行return执行；但是不会影响proxy_pass指令的执行。

* return：返回指定状态码和信息。

* ```bash
  return code [text];
  return code URL;
  return URL;
  ```

* if：根据指定的条件确定是否执行指令块中的内容。例如

* ```bash
  判断条件
  1、一个变量名，如果变量 $variable 的值为空字符串或者字符串"0"，则为false
  2、变量与一个字符串的比较 相等为(=) 不相等为(!=) 注意此处不要把相等当做赋值语句啊
  3、变量与一个正则表达式的模式匹配 操作符可以是(~ 区分大小写的正则匹配， ~*不区分大小写的正则匹配， !~ !~*，前面两者的非)
  4、检测文件是否存在 使用 -f(存在) 和 !-f(不存在)
  5、检测路径是否存在 使用 -d(存在) 和 !-d(不存在) 后面判断可以是字符串也可是变量
  6、检测文件、路径、或者链接文件是否存在 使用 -e(存在) 和 !-e(不存在) 后面判断可以是字符串也可是变量
  7、检测文件是否为可执行文件 使用 -x(可执行) 和 !-x(不可执行) 后面判断可以是字符串也可是变量
  set $variable "0"; 
  if ($variable) {
      # 不会执行，因为 "0" 为 false
      break;            
  }
  ```

* rewrite：重写url，语法规则是rewrite regex replacement [flag];替换字符串中带http的重定向会直接返回302；没有带http的重定向只是简单的修改uri。flag的选择有4个break、last、redirect、permanent，具体行为见下文。不带flag的情况下且非http重定向的情况下，会逐个匹配rewrite模块指令。

#### flag

* break：停止处理当前的`ngx_http_rewrite_module`指令集，就像上面说的`break`指令一样;
* last：停止处理当前的`ngx_http_rewrite_module`的指令集，并开始搜索与更改后的`URI`相匹配的`location`;
* redirect：返回302临时重定向。
* permanent：返回301永久重定向。

#### 参考

参考链接https://segmentfault.com/a/1190000008102599

#### 总结

rewrite指令不一定会发起二次请求。

break和last的区别在于last停止匹配之后会查找匹配新uri的location。









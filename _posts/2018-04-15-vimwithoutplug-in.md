---
layout: post
title: vim无插件编程
date: 2018-4-08
categories: blog
tags: [效率提升]
description: na。
---



### 无插件技巧使用
* `:E` 打开文件
* `:ls` 查看当前的所有buffer
* `:buffer {i}` `:bnext` `:bn` `:bprevious` `:bp` `:blast` `:bl` `:bfirst` `:bf` buffer相关的操作
* `:He` `:He!` `ctrl+ijkl` 水平分屏
* `:Ve` `:Ve!` `ctrl+ijkl` 垂直分屏
* `:Te` 新建tab页
* `gt` `gT` `{i}gt` tab间的移动
* `:tabs` `:tabclose {i}` 显示所有tab，关闭指定id的tab
* `:set scb` 设置同步移动
* `:bufdo tab split` 将所有的buffer转成tab形式显示
* `:mksession ~/.mysession.vim` 保存vim信息文件
* `vim -S ~/.mysession.vim` vim启动直接加载文件
* `:source ~/.mysession.vim` 加载vim文件
* `:make` `:cw` 取出make错误的信息
* `:grep -r "init_connection" ./ --include *.{c,h}`
* `:cw` 取出grep的结果
* `ctrl+n` `ctrl+p` 补全和选择补全字段，vim下方可以看到输入提示
* 安装cscope，`brew install cscope` 然后直接使用vim配置文件
* 配色设置，下载相应的配色文件到`~/.vim/colors`目录下，并在vim配置文件中指定color，例如`color mycolor`,monokai\solarized配色方式网上可以下载
* `guu` `Vu` `gUU` `VU`
* v进入选择模式按u转小写，按U转大写
* `ga`查看ascii `g8`查看utf8 `gf`打开光标处所指的文件
* `*` `#`在当前文件中搜索当前光标的单词
* `=`缩进,`v`选择之后输入`=`可以将选中的内容缩进对齐，`gg=G` `G=gg`全文缩进对齐
* `:r!pwd` 读取shell命令相关
* `v` + `y` `p` `[n]dd` `yy`复制粘贴
* `:s/vivian/sky/` 替换当前行第一个 vivian 为 sky 
* `:s/vivian/sky/g` 替换当前行所有 vivian 为 sky 
* `:n，$s/vivian/sky/` 替换第 n 行开始到最后一行中每一行的第一个 vivian 为 sky 
* `:n，$s/vivian/sky/g` 替换第 n 行开始到最后一行中每一行所有 vivian 为 sky ,n 为数字，若 n 为 .，表示从当前行开始到最后一行 
* `:%s/vivian/sky/`（等同于`:g/vivian/s//sky/`） 替换每一行的第一个 vivian 为 sky 
* `:%s/vivian/sky/g`（等同于`:g/vivian/s//sky/g`） 替换每一行中所有 vivian 为 sky 
* 可以使用 # 作为分隔符，此时中间出现的 / 不会作为分隔符 `:s#vivian/#sky/#` 替换当前行第一个 vivian/ 为 sky/ 



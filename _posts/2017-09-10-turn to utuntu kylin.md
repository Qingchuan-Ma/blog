---
layout: post
title:  "运用Jekyll建立博客"
author: "Qingchuan-Ma"
---

# Windows上搭建jekyll环境并建立github网站

## Windows搭建jekyll环境

### *1.安装ruby:*

* 去官网下载[rubyinstall](https://www.ruby-lang.org/zh_cn/downloads/)并安装

### *2.安装rubygem(两种方式)：*
* 可以选择去[官网](https://rubygems.org/pages/download)下载压缩包解压运行* setup.rb*

* 在cmd中输入下面代码(升级)
  >gem update --system

  或者下面代码(更新)
  >gem install rubygems-update

  >update_rubygems

### *3.安装jekyll:*
* 安装完了以后在cmd中运行
  >gem install jekyll

* jekyll使用手册参见[官网](http://jekyll.com.cn/)

## 测试jekyll环境是否搭建成功

在命令行中输入下面代码
>jekyll new blog

>cd blog

>jekyll serve --wathch

第一行建立了一个一个新博客，第二行进入博客目录，第三行在本地搭建了一个服务器，可以在浏览器中输入 http://localhost:4000(127.0.0.1:4000) 进入你所搭建的本地网站。

在Windows上有很多时候会有其他进程占用4000的端口,若没有关闭占用次端口的进程，则会出现 Permission denied 的信息，我们则需要如下做：
* 在命令行中输入
>netstat -aon | findstr "4000"

* 找到占用4000端口的程序进程PID
* 打开任务管理器服务中关闭冲突的进程(停止服务即可)

最终能在本地看到你所建立的新博客则是环境配置成功。


## 建立github网站

---
layout: post
title:  "运用Jekyll建立博客"
author: "Qingchuan-Ma"
category: "Jekyll"
tag: "Config"
---

# Windows 上搭建 jekyll 环境并建立个人网站

## 一. Windows 搭建 jekyll 环境

### *1.安装 ruby :*

* 去官网下载[rubyinstall](https://www.ruby-lang.org/zh_cn/downloads/)并安装

### *2.安装 rubygem (两种方式)：*
* 可以选择去[官网](https://rubygems.org/pages/download)下载压缩包解压运行* setup.rb*

* 在cmd中输入下面代码(升级)
{%highlight ruby%}
gem update --system
{%endhighlight %}

  或者下面代码(更新)
  >gem install rubygems-update

  >update_rubygems

### *3.安装 jekyll :*
* 安装完了以后在cmd中运行
  >gem install jekyll

* jekyll 使用手册参见[官网](http://jekyll.com.cn/)

## 二. 测试jekyll环境是否搭建成功

在命令行中输入下面代码
>jekyll new blog

>cd blog

>jekyll serve --wathch

第一行建立了一个一个新博客，第二行进入博客目录，第三行在本地搭建了一个服务器，可以在浏览器中输入 http://localhost:4000 ( 127.0.0.1:4000 ) 进入你所搭建的本地网站。

在 Windows 上有很多时候会有其他进程占用4000的端口,若没有关闭占用次端口的进程，则会出现 Permission denied 的信息，我们则需要如下做：
* 在命令行中输入
>netstat -aon | findstr "4000"

* 找到占用4000端口的程序进程PID
* 打开任务管理器服务中关闭冲突的进程(停止服务即可)

最终能在本地网站中看到你所建立的新博客则是环境配置成功。


## 三. 建立github网站

建立网站的过程具体详情可以参考 jekyll 的[官方手册](http://jekyll.com.cn/)，原理为 jekyll 编译你的整个文件夹，通过你的YML文件 (语言：YAML) 配置个个网页，配置网页的过程则是利用 Liquid 语言将 YML 文件中的所有配置应用到各个网站，其中 css 和 javascript 可以由你自由编写。

在本地建立成功了网站以后，可以将其挂在 github 服务里利用 github page 发布出去，具体操作如下

* 创建 github 账号登录，然后创建一个名为 blog 的仓库
* 利用 git 命令行或者是 github for desktop 将本地网站 push 到 blog 仓库
* 打开 setting 页面，找到 github pages 选项，将其发布

最终，通过这样我们就可以创建自己的博客了。博客网页可以使用 markdown 语言编写 (文件后缀为md)，也可以使用 textile 语言编写 (文件后缀为textile)，而我没有听说过 textile 语言，通过查询该语言也可以像 markdown 一样用简单的语言将以各自的文本文件转化为 html，而这个转化工具 RedCloth 则正好处于 gem 库，于是在 windows 上我再次利用 cmd 输入 gem install RedCloth， 最终却由于不明原因，没有成功，似乎是因为 windows 上的 rubygem 只能利用 MSYS2 作为他的开发环境，而 MSYS2 安装的 MinGW 又很鸡肋的和原版 MinGW 有冲突，于是，我下决心决定安装一个 Linux 系统，于是有了下一篇博客。

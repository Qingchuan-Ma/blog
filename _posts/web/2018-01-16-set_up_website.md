---
layout: post
title:  "Set up Website"
author: "Qingchuan-Ma"
category: "Web"
tag: "Apache"
---

# 通过 Apache 建立网站和遇到的问题

## 1. 通过阿里云购买服务器并开启端口

端口不是默认就开启的，需要手动开启，在阿里云的控制台上自行开启

## 2. apache的安装和配置

[参考这篇blog](https://qingchuan-ma.github.io/blog/2017-12-01/apache%E7%9A%84%E9%85%8D%E7%BD%AE)

这里我们采用了上文的第一种方法并且以此安装Lamp套组

## 3. lamp的安装和配置

输入以下命令
{%highlight shell%}
sudo tasksel install(remove) lamp-server
{%endhighlight%}
其中会让你设置mysql的密码

## 4. 安装 django 框架
先安装python-mysql，否则出现依赖错误
{%highlight shell%}
pip install python-mysql
pip install django
{%endhighlight%}
同时配置WSGI

安装详情参考[这篇blog](https://qingchuan-ma.github.io/blog/2017-12-03/django%E5%9C%A8apache%E4%B8%8A%E7%9A%84%E9%85%8D%E7%BD%AE)


## 5. 学会使用apache的虚拟主机

虚拟主机和反向代理机制

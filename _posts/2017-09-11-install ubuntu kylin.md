---
layout: post
title:  "安装Windows 8和Ubuntu Kylin双系统"
author: "Qingchuan-Ma"
---

# 安装 Windows 8 和 Ubuntu Kylin 双系统


_*注意：以下操作全部在电脑 legecy 启动下成立。*_

## 一. 准备必要软件硬件

>|Soft/Hardware    |  Download         |
| ------------- | ------     |
| Ubuntu.iso      | [Address](http://cn.ubuntu.com/download/) |
| DiskGenius |[Address](http://www.diskgenius.cn/download.php)|
| ultraiso |    [Address](https://cn.ultraiso.net/xiazai.html)   |
| Easybcd(optional)|[Address](http://www.onlinedown.net/soft/58174.html)|
| U Disk   | none|  

## 二. 刻录 U 盘和分区

利用安装的 ultraiso 打开 Ubuntu.iso 并且 刻录到 U 盘中。
利用安装的 DiskGenius 分出大约 100G 大小的大小空闲区域。
由于我已经是在 linux编辑的这篇博客，已没有图片可供参考。这一大步骤也不是难事。

## 三. U 盘安装

WIndows 设置 U 盘安装，一般是开机时按 F10 或其他按键，最后 U 盘启动开始安装。然后一直按照安装即可，然后在选择安装区域选择其他选型并将上面分出的 100G 的空闲区域分成下面这些区域。

>  | 挂载点 | 分区大小 | 分区目的 |分区类型 |
  |--------|------|--------|-------------|
  |  /    | 10G     |   Ext4 |主分区   |
|/home  | 50G     |   Ext4 |逻辑分区 |
|/usr   | 30G     |   Ext4| 逻辑分区 |
|none   | 8G(与内存一样) |用于交换 |逻辑分区|



以上的所有大小分区仅供参考，具体大小由功能自己确定，在这一页中最后一个选项为安装启动引导启的设备，我选择的是 ubuntu 所在的硬盘，但这样的话在 windows 直接删除 ubuntu 的话会出现电脑无法启动 windows 项，因为这样设置是 ubuntu 带动 windows，我因为不会在删除该系统所以并没有选择 windows 所在的硬盘，如果你需要，请将安装启动引导项的选项中选择 windows 8 所在的硬盘，最后你就安装成功了 ubuntu 和 windows 双系统

## 四. 设置启动项
如果你选择 ubuntu 启动 windows 不必要进行此项步骤即可启动 ubuntu 和 windows，但如果你选择了 windows 启动 ubuntu，开机时不出现 ubuntu 启动项，解决方案为使用 Easybcd 自行设定启动项，具体方案参见此[网站](https://jingyan.baidu.com/article/c35dbcb0f2f0458916fcbc06.html)

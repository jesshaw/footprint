---
title: 如何快速搭建linux运行环境
tags: linux,VirtualBox,VirtualBox image,CentOS
categories: 
  - linux

thumbnail: /gallery/blue-water7.jpg
---

对于程序员来说，很可能用linux作为服务器运行环境，为了提前发现问题不可避免的需要搭建一套linux运行环境，此文给出一个可行、快速且经济的解决方案。

<!-- more -->
## 1 选型

VirtualBox VS VMware
选Oracle的VirtualBox，原因是基本功能都支持且免费。

## 2 安装步骤

### 2.1 下载VirtualBox
打开[virtualbox官网](https://www.virtualbox.org/wiki/Downloads) ，选择windows hosts下载到本地，安装完成进行到下一步。

### 2.2 下载Linux镜像

打开[osboxes官网](https://www.osboxes.org/virtualbox-images/) ,打开CentOS链接，找到linux 32bit下载。也可以下载64bit据自身机器情况而定。

### 2.3 创建虚拟电脑

打开VirtualBox->新建->CentOS->...->使用已有虚拟硬盘->选择已下载的Linux镜像*.vdi文件->..->直到完成。

### 2.4 系统初始化设置

按提示进行系统设置，最后输入osboxes.org作为用户密码，登入Linux系统即完成搭建。

## 3 进入setting设置termial终端打开快捷键为alt+F12

Setthings->Keyboard->add command->Name "Terminal" Command "/usr/bin/gnome-terminal”->Shortcuts->输入alt+F12。






---
layout: post
title: 'Hello World'
subtitle:'first blog'
date: 2017-08-29
categories: 技术
cover: 'http://on2171g4d.bkt.clouddn.com/jekyll-theme-h2o-postcover.jpg'
tags: tag1 tag2 tag3
---
#### 1.安装putty
sudo apt-get intsall putty

#### 2.查看串口设备名字
ls /dev

/dev/ttyUSB0

#### 3.查看设备文件权限

ls -l /dev/ttyUSB0
crw-rw---- 1 root dialout 188, 0  7月 16 11:27 /dev/ttyUSB0

发现root用户和dialout组的用户有读写权

#### 4.那把自己加到dialout组里去吧。

先看看自己在哪些组里面：
  	
$ id -Gn
username adm cdrom sudo dip plugdev lpadmin sambashare

果然不在dialout组里，加进去吧:
  	
$ sudo adduser username dialout    //这里把username换为你自己的用户名

#### 5.注销或重启后检查一次：
$ id -Gn

username adm dialout cdrom sudo dip plugdev lpadmin sambashare

好了，进去了，再用putty连接，搞定。

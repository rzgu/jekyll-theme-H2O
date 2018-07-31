---
layout: post
title: 'Kali更换源与安装vmtools'
subtitle: '使用VMware'
date: 2018-07-31
categories: 技术
cover: 'http://wx4.sinaimg.cn/large/0060OZ27gy1fqlul3wt22j312w0mi0wd.jpg'
tags: Kali VMware
---

2016 年1月，这个时间节点，可以说是我们的一个重要里程碑。我们公开发布了Kali Linux在2016年的第一个发行版—Kali Rolling（Kali linux的即时更新版）。当我们在运行原先的Kali 2.0版本（代号为“sana”）时，Kali会提示是否要进行版本更新。这个版本在如何进行VMware用户工具的安装上，也做出了一个不同以往的改变。截 至2015年9月，VMware已经发出建议，对于使用VMware客户端的用户，都要求用open-vm-tools自带的工具软件包来代替原先的软件包。

打开终端，更换Kali的更新源为国内源，这里选择ustc的源
输入以下命令
```C++
gedit /etc/apt/sources.list
```
更换sources.list里面的源，将官方源注释掉（加井号），加上ustc源
```C++
#ustc source
deb http://mirrors.ustc.edu.cn/kali kali-rolling main non-free contrib
```
更改后的sources.list如下图所示
![](http://wx4.sinaimg.cn/large/0060OZ27gy1ftsugxcub3j30p70ga0u6.jpg)

接着强制更新：
```C++
apt-get update         //获取更新包/更新软件  
apt upgrade             //强制更新  
```
等待更新完成，需要一段时间
安装open-vm-tools：
```C++
apt-get install open-vm-tools-desktop fuse
reboot      //重启
```
然后测试一下从外部复制文本进虚拟机，如果可以复制粘贴，则表明安装成功。

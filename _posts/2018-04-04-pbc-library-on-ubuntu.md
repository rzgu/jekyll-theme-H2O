---
layout: post
title: 'PBC在Ubuntu的安装'
subtitle: ''
date: 2018-04-04
categories: 笔记
cover: 'http://wx1.sinaimg.cn/large/0060OZ27gy1fqli136k8xj30h40h4jra.jpg'
tags: PBC Linux
---


### 1.安装Pbc library依赖的库：

	1.输入以下代码切换root用户

> sudo su

    输入密码，回车确认。
    
    2.M4、flex、bison 其中在ununtu系统terminal中 M4、flex、bison均可以通过apt-get install方式安装。在Linux系统中键入如下命令即可安装相应的包。

> apt-get install M4
    apt-get install flex
    apt-get install bison


​    


### 2.安装GMP库：

	GMP库下载地址如下：https://gmplib.org/ 下载并解压，在terminal里进入解压后的文件夹进行安装，方法如下：

>  make
>     make check
>     make instal

​    


### 3.Pbc library库安装 :

	pbc（The Pairing-Based Cryptography Library）下载地址如下：http://crypto.stanford.edu/pbc/download.html	下载并解压，在terminal里进入解压文件夹安装，方法如下：

>  ./configure 
>     make
>     make install

​    


### 4.验证:

	我进入gmp文件夹下的example目录内，用hess.c文件试了一下，将hess.c编译为test333，并放在当前文件夹内，运行:

​    

> gcc -o test333 hest.c -lpbc -lgmp -I /usr/local/include/pbc
> /usr/local/include/gmp.h


   	然后返回上一级: 


> cd ../


   	运行test333： 
   >  ./example/test333 param/a.param'


  	 如果你看到如下类似输出，恭喜pbc安装成功了:
    ![运行成功](http://wx3.sinaimg.cn/large/0060OZ27gy1fq0ztoqa1cj30kw0g0wm6.jpg)
   	

   

​    



 [参考](http://shield-sky.github.io/2016/04/10/pbc-library-on-ubuntu/)


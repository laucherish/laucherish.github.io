---
layout: post
title:  使用Fiddler对Android模拟器网络请求进行抓包
description: Fiddler是一个很好的网络抓包工具，使用其对Android模拟器的网络请求进行抓包
permalink: /fiddler-http/
categories: [blog, 博客]
tags: [Fiddler, Android, Genymotion, 抓包]
date: 2015-05-19 10:00:00
--- 

## 下载安装Fiddler
下载并安装Fiddler，运行软件，Fiddler默认的代理地址是127.0.0.1，端口为8888。我们此时已经可以对电脑的网络请求进行抓包。但是如果要对Android模拟器的网络请求进行抓包，还需要进行如下设置。

笔者使用的是Genymotion模拟器，Android原生模拟器的设置方法也大体相同。
## 1.打开Settings（设置），点击Wi-Fi。

![设置](/images/2015-05-19-fiddler-http/device-2015-04-27-105348.png)

## 2.长按WiredSSID，选择Modify network（修改网络）

![修改网络](/images/2015-05-19-fiddler-http/device-2015-04-27-105444.png)

## 3.勾上Show advanced options，输入代理服务器地址和端口。

![代理](/images/2015-05-19-fiddler-http/device-2015-04-27-105513.png)

注意：Genymotion模拟器中ip为**10.0.3.2**，Android模拟器中ip为**10.0.2.2**，端口就是Fiddler监听的端口，默认为8888，最后点击Save。

经过以上设置，现在Fiddler就可以抓包到Android模拟器的网络请求了。
使用Android模拟器自带的浏览器打开网页，测试结果如下：

![模拟器打开百度](/images/2015-05-19-fiddler-http/device-2015-04-27-105749.png)

![Fiddler抓包结果](/images/2015-05-19-fiddler-http/QQ截图20150427105719.png)





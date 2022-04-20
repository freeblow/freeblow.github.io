---
layout: post
title: "SSH"
date: 2022-03-30
excerpt: "SSH简介"
tags: [iOS, SSH, OpenSSH, 远程登录]
comments: true
category: "re-ios"
---

# [SSH](https://www.ietf.org/rfc/rfc4251.txt)

* Secure Shell的缩写, 意为"安全壳协议"，一种加密的网路传输协议, 可以在不安全的网络中为网络服务提供安全的网络传输环境. SSH通过在网络中创建安全隧道来实现SSH客户端和服务器之间的连接。SSH最常用的用途是远程登录系统；
* 使用SSH，可以把所有传输的数据进行加密, 以避免“中间人(sniffer即为嗅探器或者各种数据抓包工具)”攻击，能防止DNS欺骗和IP欺骗;
* 关于SSH更详细的介绍能见[WIKIPEDIA SSH](https://zh.wikipedia.org/wiki/Secure_Shell)

#### [OpenSSH](https://www.openssh.com)

* 是SSH协议的开源实现;
* 可以通过SSH的OpenSSH实现，实现让Mac远程登录到对应的iPhone来从终端操纵相对应的iPhone;

#### 使用OpenSSH远程登录(iOS)
* 在越狱后的iPhone上通过Cydia来安装OpenSSH工具;
* 安装的步骤自行查看相应的OpenSSH的软件源中的介绍;

使用步骤

* SSH是通过TCP协议通信，所以需要确保Mac和iPhone在同一个局域网下，例如大家都连着同一个WIFI
	* 在mac终端输入 ssh 用户名@服务器主机地址  
		* 用户名是服务器的用户名;
		* 主体地址可以是主机名或者主机IP地址。 这里的主机是只远程服务器;
		* 比如 ssh root@192.168.19.108
	* iOS的root用户的初始密码是: alpine
* 登录成功后可以使用终端命令来操作iOS系统，即为您的iPhone手机；
* 退出终端命令为 exit;








 

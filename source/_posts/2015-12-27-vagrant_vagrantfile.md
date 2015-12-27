---
layout: post
title: vagrant之vagrantfile配置文件详解
date: 2015-12-27 16:13:20
tags: vagrant
categories: 技术
---

在一些实际使用中、我们需要涉及到vagrant的网络设置、挂载、等信息的设置、这些都要通过修改Vagrantfile来实现、该文件就在创建的开发目录下面，下面就来介绍一些重要的Vagrantfile配置

## box设置
##### 如果启动的时候、直接用的```vagrant init``` 的话、默认名称是base、配置文件如下
	config.vm.box = "名称" 设置vagrant box的名称
##### 可以通过配置文件调用VBoxManage来实现修改如下
	config.vm.provider "virtualbox" do |v|
	  v.customize ["modifyvm", :id, "--name", "astaxie", "--memory", "512"]
	end
这行设置的意思是调用VBoxManage的modifyvm的命令，设置VM的名称为astaxie，内存为512MB。

## 网络设置
##### Vagrant有两种方式来进行网络连接
* host-only(主机模式)：只有宿主机才能访问虚拟机、其他人访问不了
* Bridge(桥接模式)：将虚拟机虚拟成局域网的一台独立的主机、其他人都可访问

##### host-only(主机模式)
	config.vm.network :private_network, ip: "11.11.11.11"
##### Bridge(桥接模式)一、让路由器自定义虚拟机地址
	config.vm.network "public_network", bridge: "en1: Wi-Fi (AirPort)"
##### Bridge(桥接模式)二、固定ip地址、注意网段、
	config.vm.network "public_network", ip: "192.168.0.17"
## hostname设置
##### hostname设置很简单、也很重要、多台虚拟机、只能通过hostname来区分、加入一下配置文件即可
	config.vm.hostname = "hostname"
## 目录挂载
##### vagrant的挂载目录和docker类似、都有一个默认的目录、docker有的时候不能设置、而vagrant修改起来很简单
	config.vm.synced_folder  "/Users/Devel/vagrant", "/vagrant"
第一个参数是主机的目录，第二个参数是虚拟机挂载的目录
## 端口转发
	config.vm.network :forwarded_port, guest: 80, host: 8080
上面这一行配置、类似于docker -p 、能将主机访问宿主机对应端口的请求、转发给虚拟机、上面这一行配置的意思就是、将访问主机8080端口的访问请求转发到到虚拟机的80端口的服务上

##### 好啦、配置文件就讲到这边了。本人也是刚入门、到时候研究深入了、再来补充、
	


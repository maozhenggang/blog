---
layout: post
title: vagrant + coreos入门
date: 2015-12-26 23:28:46
tags: vagrant
categories: 技术
---

Vagrant就是为了方便的实现虚拟化环境而设计的，使用Ruby开发，基于VirtualBox,vmware等虚拟机管理软件的接口，提供了一个可配置、轻量级的便携式虚拟开发环境。使用Vagrant可以很方便的就建立起来一个虚拟环境，而且可以模拟多台虚拟机

## 为什么要使用vagran、场景
* 多平台迁移、基于vagrant的应用和环境可以轻松的在windows、unix、linux等不同平台之间迁移
* 主机和虚拟机之间可以代码共享、主机本地写程序、虚拟机运行、实现团队共享相同的开发环境、避免不同环境导致的bug
* 可打包现有工作环境(包括开发工具，代码库，配置好的服务器等)、方便备份、共享
* 支持市面上比较火的几款虚拟化软件、VirtualBox、VMware、甚至可以将AWS作为虚拟机系统、
* 各种成熟的镜像可供使用、学习成本低

## 准备
* 下载安装[vagrant](https://www.vagrantup.com/downloads.html)、 安装成功后、打开cmd/shell、输入vagrant、有返回表示安装成功
* 下载安装[visualbox](https://www.virtualbox.org/wiki/Downloads)、直接安装即可
* 准备box或者现有镜像、我用的是现有的[vagrant-Coreos](https://github.com/coreos/coreos-vagrant)镜像

## 开始
* 创建一个本地开发环境目录 例如 windows下 `E:\Devel\vagrant` 、mac下`/Users/Devel/vagrant`
* 将vagrant所需box或者镜像、下载到该文件夹、
	* box： `vagrant box add base "远端的box地址或者本地的box文件名"`
	* vagrant镜像：直接 `git clone https://github.com/coreos/coreos-vagrant.git`
* 初始化
	* 镜像初始化：`vagrant init` 、到时候可以到配置文件修改
	* box初始化：`vagrant init "coreos"` 、可以加上初始名称、
* 启动虚拟机  `vagrant up `
* 连接虚拟机  `vagrant ssh `

通过上面操作、我们就可以连接到虚拟出来的coreos中操作了、windows下vagrant ssh连接时、只会显示连接信息、不能直接连接、需要安装ssh客户端

好啦、简单的使用就到这里了、下一篇我会讲到Vagrantfile配置文件详解



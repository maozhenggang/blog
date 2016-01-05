---
layout: post
title: vagrant之常用命令汇总
date: 2015-12-27 16:41:18
tags: vagrant
categories: 技术
---
vagrant常用命令汇总、<!-- more -->

* vagrant 命令
	* vagrant box add： 添加box的操作
	* vagrant init： 初始化box的操作
	* vagrant up： 启动虚拟机的操作
	* vagrant ssh： 登录拟机的操作
	* vagrant box list： 显示当前已经添加的box列表
	* vagrant box remove： 删除相应的box、如 vagrant box remove name virtualbox
	* vagrant destroy： 停止当前正在运行的虚拟机并销毁所有创建的资源
	* vagrant halt： 停止当前正在运行的虚拟机
	* vagrant package： 打包、将当前的运行的虚拟机环境进行打包
	* vagrant plugin： 用于安装卸载插件
	* vagrant reload： 重启虚拟机
	* vagrant suspend：挂起当前虚拟机
	* vagrant resume： 恢复被挂起的状态
	* vagrant ssh-config：输出用于ssh连接的一些信息
	* vagrant status：获取当前虚拟机的状态

基本上常用的就这些、后面接触到会继续补充!




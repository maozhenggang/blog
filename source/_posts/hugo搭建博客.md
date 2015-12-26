title: 使用hugo搭建个人站点
date: 2015-12-26 21:01:23
tags: hugo
categories: 技术
---
Hugo是一个用Go语言编写的静态网站生成器，它使用起来非常简单，相对于Jekyll复杂的安装设置来说，Hugo仅需要一个二进制文件hugo(hugo.exe)即可轻松用于本地调试和生成静态页面，同时hugo的生成速度比hexo、jekyll这些都要快。

##### mac环境安装
	一行命令即可搞定 brew install hugo 

##### windows环境安装

* 下载hugo所需2进制文件，[最新版本](https://github.com/spf13/hugo/releases)即可。我下载的是 hugo_0.15_windows_amd64.zip
* 在本机上新建一个文件夹放置2进制文件、我的路径是 E:\Devel\Hugo\bin
* 将  hugo_0.15_windows_amd64.zip文件解压改名成 hugo.exe 、放到该文件夹下面
* 将 E:\Devel\Hugo\bin 路径加到环境变量中、此时打开cmd窗口、输入hugo、如果有返回、安装成功

##### 基础设置
* 随便建一个目录、比如我的就是```E:\Devel\Hugo\```
* 打开cmd窗口、通过命令、进入该文件夹、输入```hugo new site blog``
* hugo就会在该文件夹下面创建如下目录结构
	* archetypes：网站、个人、图片等信息配置
	* config.toml ：配置文件
	* content ：内容
	* data ： 不清楚干嘛用的、官网貌似没讲
	* layouts :布局文件
	* static :存放一些静态文件
* 创建themes文件夹、进去、[下载皮肤](https://github.com/spf13/hugoThemes), `git clone https://github.com/spf13/hyde.git`
* 回到上层目录、创建关于页面、`hugo new about.md`、about.md 自动生成到了 `content/about.md `
* 创建第一个页面、`hugo new post/first.md`、first.md生成到`content/post/first.md`

###### 运行博客预览
* hugo server --theme=hyde --buildDrafts --watch
	* 使用 --watch 参数可以在修改文章内容时让浏览器自动刷新。
	* 使用 --theme 参数可以指定模版

浏览器里打开： http://localhost:1313 查看

###### 其他资料
* [官方网站](https://gohugo.io/)
* [hugo中文文档](http://www.gohugo.org/)

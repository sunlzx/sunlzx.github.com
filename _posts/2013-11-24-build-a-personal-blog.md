---
layout: post
title: "build a personal blog"
description: ""
category: "blog"
tags: [blog]
---
{% include JB/setup %}

## Jekyll ##

Jekyll官方地址：<http://jekyllrb.com/>


### win7下安装Jekyll遇到的主要问题 ###

win7安装jekyll

Jekyll在window下安装很麻烦，依赖的东西太多，安装方法：[Running Jekyll on Windows](http://www.madhur.co.in/blog/2011/09/01/runningjekyllwindows.html)。

为了安装方法，有人把jekyll相关的依赖打包成立zip包，只有下载后解压就可以运行，文档地址：
[Building portable Jekyll for Windows](http://www.madhur.co.in/blog/2013/07/20/buildportablejekyll.html)
成功下载解压后，启动终端，运行文件夹下的setpath.cmd设置环境变量，设置仅对当前终端有效。

**安装过程运到的问题**

文件内容含有中文字符，导致jekyll serve启动失败。
解决方法：
	修改convertible.rb文件，
	老版本：将
	self.content = File.read(File.join(base, name))
	修改为
	self.content = File.read(File.join(base, name), :encoding => "utf-8")

	新版本（D:\PortableJekyll\ruby\lib\ruby\gems\2.0.0\gems\jekyll-1.3.0\lib\jekyll\convertible.rb）
	将第38行修改为：self.content = File.read_with_options(File.join(base, name), :encoding => "utf-8")




**注意事项**

	* 文件必须是UTF-8无BOM编码的
	* 文件名不能含有中文字符（title可以包含中文）


### jekyll 常用命令　###

usage:<http://jekyllrb.com/docs/usage/>

常用命令

	jekyll build
	jekyll serve
	jekyll serve --watch

## 使用jekyllbootstrap搭建个人博客 ##

http://jekyllbootstrap.com/



## jekyll图片管理 ##
<http://fengaili.com/2013/09/08/jekyll-images/>


[Jekyll QuickStart](http://jekyllbootstrap.com/usage/jekyll-quick-start.html)

[liquid-for-designers](https://github.com/shopify/liquid/wiki/liquid-for-designers)


## Jekyll的中的代码高亮 ##
<http://yansu.org/2013/04/22/highlight-of-jekyll.html>



## 遗留问题 ##

	怎么定制导航栏？

	怎么定制右侧边栏显示？这样的效果：<http://xdutaotao.github.io/blog/2012/09/23/jekyll-and-liquid-related-knowledage/>





## 相关资料 ##

[利用Jekyll搭建个人博客](http://jekyllbootstrap.com/usage/jekyll-quick-start.html)

[利用Jekyll搭建个人博客(中文)](http://www.mceiba.com/develop/jekyll-introduction.html)

[搭建一个免费的，无限流量的Blog----github Pages和Jekyll入门](http://www.ruanyifeng.com/blog/2012/08/blogging_with_jekyll.html)

[Jekyll建站之旅](http://calefy.org/2012/03/03/my-process-of-building-jekyll-blog.html)

[Jekyll-搭建个人博客](http://blog.sxxybbs.com/2013/09/23/Jekyll-build-personal-blog.html)



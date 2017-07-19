<!--
author: imkindu
date: 2017-07-16
title: lsb_release
tags: linux lsb_release
category: command
status: publish
summary: lsb_release
-->

<link href="http://cdn.bootcss.com/highlight.js/8.0/styles/monokai_sublime.min.css" rel="stylesheet">  
<script src="http://cdn.bootcss.com/highlight.js/8.0/highlight.min.js"></script>
<script >hljs.initHighlightingOnLoad();</script>

**<h3 style align='center'>lsb_release</h3>**

　　**LSB**是**Linux Standard Base**的缩写，<strong>lsb_release命令</strong>用来显示LSB和特定版本的相关信息。如果使用该命令时不带参数，则默认加上-v参数。

>- -v 显示版本信息。 
- -i 显示发行版的id。 
- -d 显示该发行版的描述信息。 
- -r 显示当前系统是发行版的具体版本号。 
- -c 发行版代号。 
- -a 显示上面的所有信息。 
- -h 显示帮助信息。

###### 查看所有信息：

		[root@centos6 ~]# lsb_release -a
		LSB Version:	:base-4.0-amd64:base-4.0-noarch:core-4.0-amd64:core-4.0-noarch:graphics-4.0-amd64:graphics-4.0-noarch:printing-4.0-amd64:printing-4.0-noarch
		Distributor ID:	CentOS
		Description:	CentOS release 6.9 (Final)
		Release:	6.9
		Codename:	Final


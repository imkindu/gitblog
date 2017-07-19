<!--
author: imkindu
date: 2017-07-19
title: pwd
tags: shell
category: command
status: publish
summary: pwd（Print working directory）
-->

<link href="http://cdn.bootcss.com/highlight.js/8.0/styles/monokai_sublime.min.css" rel="stylesheet">  
<script src="http://cdn.bootcss.com/highlight.js/8.0/highlight.min.js"></script>
<script >hljs.initHighlightingOnLoad();</script>


　　PWD（print working directory）显示当前shell CWD（current work directory）的绝对路径<br/>
　　Print the name of the current working directory.

##### Options:
		-L	print the value of $PWD if it names the current working directory

		-P	print the physical directory, without any symbolic links
		**显示真实物理链接，对于链接文件，会显示其真实的指向文件**

		By default, `pwd' behaves as if `-L' were specified.
##### 示例
		[imkindu@centos6 ~]$ pwd		#显示当前工作目录
		/home/imkindu

		# -P显示真实物理链接
		[imkindu@centos6 ~]$ ll
		total 40
		drwxr-xr-x. 3 imkindu imkindu 4096 Jul 19 19:49 Desktop
		drwxr-xr-x. 2 imkindu imkindu 4096 Jul 14 10:57 Documents
		drwxr-xr-x. 2 imkindu imkindu 4096 Jul 14 10:57 Downloads
		lrwxrwxrwx. 1 imkindu imkindu   18 Jul 19 19:49 imkindu -> ./Desktop/imkindu/	#imkindu是一个软链接
		drwxr-xr-x. 2 imkindu imkindu 4096 Jul 14 10:57 Music
		drwxr-xr-x. 2 imkindu imkindu 4096 Jul 14 10:57 Pictures
		drwxr-xr-x. 2 imkindu imkindu 4096 Jul 14 10:57 Public
		drwxrwxr-x. 3 imkindu imkindu 4096 Jul 19 19:06 scripts
		drwxr-xr-x. 2 imkindu imkindu 4096 Jul 14 10:57 Templates
		drwxrwxr-x. 2 imkindu imkindu 4096 Jul 19 16:23 test
		drwxr-xr-x. 2 imkindu imkindu 4096 Jul 17 10:55 Videos
		[imkindu@centos6 ~]$ cd imkindu/
		[imkindu@centos6 imkindu]$ pwd					#pwd显示的是当前工作路径
		/home/imkindu/imkindu
		[imkindu@centos6 imkindu]$ pwd -P				#因为imkindu是一个软链接，加上-P会显示真实的地址
		/home/imkindu/Desktop/imkindu

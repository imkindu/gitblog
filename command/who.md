<!--
author: imkindu
date: 2017-07-16
title: who
tags: shell
category: command
status: publish
summary: w、who、who am i、whoami
-->

<link href="http://cdn.bootcss.com/highlight.js/8.0/styles/monokai_sublime.min.css" rel="stylesheet">  
<script src="http://cdn.bootcss.com/highlight.js/8.0/highlight.min.js"></script>
<script >hljs.initHighlightingOnLoad();</script>

**<h3 style align='center'>who、whoami、who am i</h3>**

- w - Show who is logged on and what they are doing.
- who - show who is logged onwhoami - print effective userid
- who am i - When a user logs in as a root across the network, both the command whoami and who am i will show you root. However, when a user abc logs in remotely and runs su – root, 
- whoami will show root whereas who am i will show abc


##### w 显示已经登录的用户及正在进行的操作
		[imkindu@centos6 ~]$ w
		 08:01:48 up 1 day,  3:02,  3 users,  load average: 0.00, 0.00, 0.00
		USER     TTY      FROM              LOGIN@   IDLE   JCPU   PCPU WHAT
		imkindu  pts/0    192.168.56.1     07:59    0.00s  0.13s  0.00s w
		imkindu  tty1     :0               Sun19    2days 48.90s  0.28s pam: gdm-password
		imkindu  pts/2    :0.0             07:59    2.00s  0.01s  0.01s /bin/bash


##### who 显示已经登录的用户名、终端名称、登录时间及登录IP
		[imkindu@centos6 ~]$ who
		imkindu  pts/0        2017-07-18 07:59 (192.168.56.1)
		imkindu  tty1         2017-07-16 19:38 (:0)
		imkindu  pts/2        2017-07-18 07:59 (:0.0)

##### who am i 和 whoami 显示当前用户
>who am i显示的是登录系统的时候的用户名，即使已经切换到其他用户也显示登录时的用户

> whoami 显示的是当前用户的用户名

		[imkindu@centos6 ~]$ who am i
		imkindu  pts/0        2017-07-18 07:59 (192.168.56.1)
		[imkindu@centos6 ~]$ whoami
		imkindu
		[imkindu@centos6 ~]$ su - root
		Password: 
		[root@centos6 ~]# who am i			#登录用户
		imkindu  pts/0        2017-07-18 07:59 (192.168.56.1)
		[root@centos6 ~]# whoami			#实际用户
		root



<!--
author: imkindu
date: 2017-07-16
title: linux 时间
tags: date
category: linux
status: publish
summary: linux分为硬件时间和系统时间。
-->

<link href="http://cdn.bootcss.com/highlight.js/8.0/styles/monokai_sublime.min.css" rel="stylesheet">  
<script src="http://cdn.bootcss.com/highlight.js/8.0/highlight.min.js"></script>
<script >hljs.initHighlightingOnLoad();</script>


**<h3 style align='center'>linux 时间</h3>**


**linux的两种时钟**
	
　- 系统时钟（System Clock） <br/>
　　　　由Linux内核通过cpu的工作频率进行的，即我们所说的系统时间 <br/>
　- 硬件时间（Real Time Clock 简称RTC） <br/>
　　　　主板时间、主板上由电池供电的主板硬件时钟

##### **date**命令是用来显示和设置系统时间与日期的。hwclock、clock设置硬件时间。

#### clock 命令

> linux clock命令用于调整RTC时间

##### 语法

> clock [--adjust][--debug][--directisa][--getepoch][--hctosys][--set --date="<日期时间>"][--setepoch --epoch=< >][--show][--systohc][--test][--utc][--version]

##### 参数说明：
>- --adjust 　第一次使用"--set"或"--systohc"参数设置硬件时钟，会在/etc目录下产生一个名称为adjtime的文件。当再次使用这两个参数调整硬件时钟，此文件便会记录两次调整间之差异，日后执行clock指令加上"--adjust"参数时，程序会自动根 据记录文件的数值差异，计算出平均值，自动调整硬件时钟的时间。
- --debug 　详细显示指令执行过程，便于排错或了解程序执行的情形。
- --directisa 　告诉clock指令不要通过/dev/rtc设备文件，直接对硬件时钟进行存取。这个参数适用于仅有ISA总线结构的老式电脑。
- --getepoch 　把系统核心内的硬件时钟新时代数值，呈现到标准输出设备。
- --hctosys 　**Hardware Clock to System Time**，把系统时间设成和硬件时钟一致。由于这个动作将会造成系统全面更新文件的存取时间，所以最好在系统启动时就执行它。
- --set --date 　设置硬件时钟的日期和时间。
- --setepoch--epoch=<年份> 　设置系统核心之硬件时钟的新时代数值，年份以四位树字表示。
- --show 　读取硬件时钟的时间，并将其呈现至标准输出设备。
- --systohc 　**System Time to Hardware Clock**，将系统时间存回硬件时钟内。
- --test 　仅作测试，并不真的将时间写入硬件时钟或系统时间。
- --utc 　把硬件时钟上的时间时为CUT，有时也称为UTC或UCT。
- --version 　显示版本信息。

###### 查看硬件时间

		[root@centos6 ~]# clock			#查看硬件时间
		Mon 17 Jul 2017 07:39:10 PM CST  -0.735695 seconds
###### 更改硬件时间

		[root@centos6 ~]# clock --set --date "2017-07-17 19:30:15"		#设置硬件时间
		[root@centos6 ~]# clock
		Mon 17 Jul 2017 07:30:22 PM CST  -0.079255 seconds
#### hwclock 命令 （hardware clock）
> hwclock和clock现在是同一个命令，语法相同

		[root@centos6 ~]# ll /sbin/clock 
		lrwxrwxrwx. 1 root root 7 Jul 14 10:41 /sbin/clock -> hwclock

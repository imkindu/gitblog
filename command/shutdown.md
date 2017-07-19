<!--
author: imkindu
date: 2017-07-18
title: shutdown
tags: shutdown 
category: command
status: publish
summary: shutdown命令用来系统关机命令。shutdown指令可以关闭所有程序，并依用户的需要，进行重新开机或关机的动作。 
-->

<link href="http://cdn.bootcss.com/highlight.js/8.0/styles/monokai_sublime.min.css" rel="stylesheet">  
<script src="http://cdn.bootcss.com/highlight.js/8.0/highlight.min.js"></script>
<script >hljs.initHighlightingOnLoad();</script>
<br/>

　　shutdown命令用来系统关机命令。shutdown指令可以关闭所有程序，并依用户的需要，进行重新开机或关机的动作。

　　**经过测试，shutdown关机后进入了单用户模式，并没有真正关机。**

#### 语法
> shutdown [OPTION]...  TIME [MESSAGE]

#### 选项
>- -c：当执行“shutdown -h 11:50”指令时，只要按+键就可以中断关机的指令； 
- -f：重新启动时不执行fsck； 
- -F：重新启动时执行fsck； 
- -h：halt 将系统关机； 
- -k：只是送出信息给所有用户，但不会实际关机； 
- -n：不调用init程序进行关机，而由shutdown自己进行； 
- -r：reboot shutdown之后重新启动； 
- -t<秒数>：送出警告信息和删除信息之间要延迟多少秒。

#### 用法
##### 指定现在关机
		[root@centos6 ~]# shutdown -h now
		
		Broadcast message from imkindu@centos6
			(/dev/pts/0) at 9:09 ...
		
		The system is going down for halt NOW!

##### 指定多久后关机，并发送警告，单位为分钟 minutes
		shutdown +5 "System will shutdown after 5 minutes"

　　**注意：发送警告信息时，必须指定一个时间参数**

##### 指定时间关机，并发送通知
		[root@centos6 ~]# shutdown 9:47 'system will be shutdown'

		Broadcast message from imkindu@centos6
			(/dev/pts/0) at 9:46 ...
		
		The system is going down for maintenance in 1 minute!
		system will be shutdown 


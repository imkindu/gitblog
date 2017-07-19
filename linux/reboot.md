<!--
author: imkindu
date: 2017-07-18
title: linux 关机命令总结
tags: reboot shutdown init
category: linux
status: publish
summary: linux下常用的关机命令有：shutdown、halt、poweroff、init；重启命令有：reboot。下面本文就主要介绍一些常用的关机命令以及各种关机命令之间的区别和具体用法。
-->

<link href="http://cdn.bootcss.com/highlight.js/8.0/styles/monokai_sublime.min.css" rel="stylesheet">  
<script src="http://cdn.bootcss.com/highlight.js/8.0/highlight.min.js"></script>
<script >hljs.initHighlightingOnLoad();</script>
<br/>

　　linux下常用的关机命令有：shutdown、halt、poweroff、init；重启命令有：reboot。下面本文就主要介绍一些常用的关机命令以及各种关机命令之间的区别和具体用法。

　　最重要的还是搞懂**shutdown**的用法，基本都是使用shutdown来关机或者重启的。

------------------------------------------------------------------
#### 关机命令：

　　1、halt   立刻关机 2、poweroff  立刻关机 3、shutdown -h now 立刻关机(root用户使用) 4、shutdown -h 10 10分钟后自动关机 如果是通过shutdown命令设置关机的话，可以用shutdown -c命令取消重启

##### poweroff
> poweroff命令用来关闭计算机操作系统并且**切断系统电源**

##### halt
> halt命令用来关闭正在运行的Linux操作系统。halt命令会先检测系统的runlevel，若runlevel为0或6，则关闭系统，否则即调用shutdown来关闭系统。

##### shutdown -h 
> shutdown命令用来系统关机命令。shutdown指令可以关闭所有程序，并依用户的需要，进行重新开机或关机的动作。 
> -h 将系统关闭

-----------------------------------------------------------


#### 重启命令：

　　1、reboot 2、shutdown -r now 立刻重启(root用户使用) 3、shutdown -r 10 过10分钟自动重启(root用户使用)  4、shutdown -r 20:35 在时间为20:35时候重启(root用户使用) 如果是通过shutdown命令设置重启的话，可以用shutdown -c命令取消重启


##### reboot
> reboot命令用来重新启动正在运行的Linux操作系统。

##### shutdown
> 这一块请查看shutdown的用

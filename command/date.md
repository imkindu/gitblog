<!--
author: imkindu
date: 2017-07-17
title: date
tags: date
category: command
status: publish
summary: date命令是显示或设置系统时间与日期。
-->

<link href="http://cdn.bootcss.com/highlight.js/8.0/styles/monokai_sublime.min.css" rel="stylesheet">  
<script src="http://cdn.bootcss.com/highlight.js/8.0/highlight.min.js"></script>
<script >hljs.initHighlightingOnLoad();</script>


**<h3 style align='center'>date</h3>**

**linux date** 命令可以用来显示或设置系统时间和日期。
其实最重要的还是格式化 +FORMAT 的用法，一定要注意 "+"

<+时间日期格式>：指定显示时使用的日期时间格式。

#### 语法：

> date [-u] [-d datestr] [-s datestr] [--utc] [--universal] [--date=datestr] [--set=datestr] [--help] [--version] [+FORMAT] [MMDDhhmm[[CC]YY][.ss]]

#### 参数说明

>- -d datestr : display显示 datestr 中所设定的时间 (非系统时间)
- --help : 显示辅助讯息
- -s datestr : set将系统时间设为 datestr 中所设定的时间
- -u : 显示目前的格林威治时间
- --version : 显示版本编号

#### 日期格式

> % : 印出 % <br/>
%n : 下一行 <br/>
%t : 跳格<br/>
%H : 小时(00..23)<br/>
%I : 小时(01..12)<br/>
%k : 小时(0..23)<br/>
%l : 小时(1..12)<br/>
%M : 分钟(00..59)<br/>
%p : 显示本地 AM 或 PM<br/>
%r : 直接显示时间 (12 小时制，格式为 hh:mm:ss [AP]M)<br/>
%s : 从 1970 年 1 月 1 日 00:00:00 UTC 到目前为止的秒数<br/>
%S : 秒(00..61)<br/>
%T : 直接显示时间 (24 小时制)<br/>
%X : 相当于 %H:%M:%S<br/>
%Z : 显示时区<br/>
%a : 星期几 (Sun..Sat)<br/>
%A : 星期几 (Sunday..Saturday)<br/>
%b : 月份 (Jan..Dec)<br/>
%B : 月份 (January..December)<br/>
%c : 直接显示日期与时间<br/>
%d : 日 (01..31)<br/>
%D : 直接显示日期 (mm/dd/yy)<br/>
%h : 同 %b<br/>
%j : 一年中的第几天 (001..366)<br/>
%m : 月份 (01..12)<br/>
%U : 一年中的第几周 (00..53) (以 Sunday 为一周的第一天的情形)<br/>
%w : 一周中的第几天 (0..6)<br/>
%W : 一年中的第几周 (00..53) (以 Monday 为一周的第一天的情形)<br/>
%x : 直接显示日期 (mm/dd/yy)<br/>
%y : 年份的最后两位数字 (00.99)<br/>
%Y : 完整年份 (0000..9999)

###### 显示当前时间
		
		[imkindu@centos6 ~]$ date					#显示当前时间
		Mon Jul 17 20:53:29 CST 2017
		[imkindu@centos6 ~]$ date --utc				#显示格林时间，比我们快8个小时
		Mon Jul 17 12:53:33 UTC 2017
		[imkindu@centos6 ~]$ date "+%Y-%m-%d"		#格式化显示时间
		2017-07-17

		[imkindu@centos6 ~]$ date -d "+10 day" "+%Y-%m-%d %a"	#通过-d设置要显示的时间
		2017-07-27 Thu

###### 设置当前时间 -s
		[imkindu@centos6 ~]$ sudo date -s "2017-07-17 21:06:53"
		[imkindu@centos6 ~]$ date
		Mon Jul 17 21:07:00 CST 2017


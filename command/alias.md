<!--
author: imkindu
date: 2017-07-16
title: alias 
tags: alias
category: command
status: publish
summary: alias 命令用来设定指令的别名，在Linux系统经常有一些很长的路径或者命令...
-->

<link href="http://cdn.bootcss.com/highlight.js/8.0/styles/monokai_sublime.min.css" rel="stylesheet">  
<script src="http://cdn.bootcss.com/highlight.js/8.0/highlight.min.js"></script>
<script >hljs.initHighlightingOnLoad();</script>


**<h3 style align='center'>alias 别名</h3>**

### 简介:

　　***alias*** 命令用来设定指令的别名，在Linux系统经常有一些很长的路径或者命令，在使用时，我们可以使用较短的名称来进行简化。在使用alias时，必须使用 `''` 将原来的命令引起来，以防特殊字符导致错误。

　　***alias***命令仅限于当前环境操作，如果退出或者重启等操作，别名将会实现，如果需要永久生效，需要将自定义别名写入配置文件中`/etc/bashrc`  `~/.bashrc`

##### 查看当前环境所有别名

		[imkindu@centos6 scripts]$ alias		#查看当前环境所有别名
		alias l.='ls -d .* --color=auto'
		alias ll='ls -l --color=auto'
		alias ls='ls --color=auto'
		alias vi='vim'
		alias which='alias | /usr/bin/which --tty-only --read-alias --show-dot --show-tilde'

##### **定义别名 alias**

##### 语法

　　***alias 新的命令='旧命令 -选项/参数'***

		[imkindu@centos6 scripts]$ alias imkindu='whoami'		#定义别名
		[imkindu@centos6 scripts]$ alias
		alias imkindu='whoami'
		alias l.='ls -d .* --color=auto'
		alias ll='ls -l --color=auto'
		alias ls='ls --color=auto'
		alias vi='vim'
		alias which='alias | /usr/bin/which --tty-only --read-alias --show-dot --show-tilde'
		[imkindu@centos6 scripts]$ imkindu			#使用别名
		imkindu

##### **取消别名 unalias**

		[imkindu@centos6 scripts]$ unalias imkindu		#取消别名
		[imkindu@centos6 scripts]$ alias
		alias l.='ls -d .* --color=auto'
		alias ll='ls -l --color=auto'
		alias ls='ls --color=auto'
		alias vi='vim'
		alias which='alias | /usr/bin/which --tty-only --read-alias --show-dot --show-tilde'
		[imkindu@centos6 scripts]$ imkindu
		-bash: imkindu: command not found

##### **别名永久生效**

　　linux中一切皆文件，要想任何配置永久生效，都必须写入文件中
　　别名永久生效可以写入全局文件`/etc/bashrc` 或者个人配置文件`~/.bashrc`中

		[imkindu@centos6 scripts]$ cat ~/.bashrc 
		# .bashrc
		# Source global definitions
		if [ -f /etc/bashrc ]; then
			. /etc/bashrc
		fi
		alias wai="whoami"					#将别名写入文件中
		# User specific aliases and functions

　　令修改的配置文件生效：`source filename`

		[imkindu@centos6 scripts]$ source ~/.bashrc 		#令文件生效
		[imkindu@centos6 scripts]$ alias
		alias imkindu='whoami'
		alias l.='ls -d .* --color=auto'
		alias ll='ls -l --color=auto'
		alias ls='ls --color=auto'
		alias vi='vim'
		alias wai='whoami'
		alias which='alias | /usr/bin/which --tty-only --read-alias --show-dot --show-tilde'
		[imkindu@centos6 scripts]$ wai
		imkindu

##### **不使用别名**

		[root@centos6 ~]# alias
		alias cp='cp -i'
		alias l.='ls -d .* --color=auto'
		alias ll='ls -l --color=auto'
		alias ls='ls --color=auto'				#ls是别名
		alias mv='mv -i'
		alias rm='rm -i'
		alias which='alias | /usr/bin/which --tty-only --read-alias --show-dot --show-tilde'
		[root@centos6 ~]# ls
		anaconda-ks.cfg  Documents  install.log         Music     Public     test
		Desktop          Downloads  install.log.syslog  Pictures  Templates  Videos

		[root@centos6 ~]# \ls					#第一种：利用 \ 转义，不使用别名
		anaconda-ks.cfg  Documents  install.log		Music	  Public     test
		Desktop		 Downloads  install.log.syslog	Pictures  Templates  Videos

		[root@centos6 ~]# 'ls'					#第二种：加 '' 单引号不使用别名
		anaconda-ks.cfg  Documents  install.log		Music	  Public     test
		Desktop		 Downloads  install.log.syslog	Pictures  Templates  Videos
		
		[root@centos6 ~]# /bin/uname 			#第三种：使用路径命令，原始命令
		Linux

	
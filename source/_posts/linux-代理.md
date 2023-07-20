---
title: linux-代理
date: 2021-10-26 00:11:10
tags: linux-代理-回顾
---

静态代理
		1.要求被装饰者和装饰者实现同一个接口或者继承同一个类
		2.装饰者中要有被装饰者的引用
		3.对需要加强的方法进行增强
		4.对不需要加强的方法调用原来的方法
	动态代理
		在程序运行的时候,动态的创建一个对象,用这个对象去操作方法方法 
		jdk的中Proxy ,前提:必须实现一个接口

```bash
	Object Proxy.newProxyInstance(ClassLoader 被代理对象的类加载器,Class[] 被代理对象实现的所有接口,InvocationHandler 处理方法);	
		InvocationHandler:接口 只需要重写一个方法
			Object invoke(Object 代理对象,Method 当前执行的方法,Object[] 当前方法执行的时候需要的参数) 
				返回值就是 当前方法执行之后的返回值

昨天的情况:
	对所有的service类中的添加方法进行加强
```
linux:操作系统 OS
首先来了解下unix:
	unix是一个多用户,多任务的操作系统,收费的操作系统.
linux:
	版本:
		内核版本
		发行版本
	centos:开源的免费的os

安装虚拟机
虚拟机:就是一台电脑
通过虚拟机软件可以在自己的电脑在安装几个电脑
常见的虚拟机软件:
	VmWare
	virtualBox:oracle 免费的

linux的目录结构
	home:家.用户的家
		普通用户的家目录文件在home下 例如:一个用户tom 在home就会存在tom的目录
	root:超级管理员root的家
	etc:存放配置文件
	usr:存放共享的资源

linux的命令
	常用的命令
		查看帮助:
			man 命令
			退出帮助目录:   q
		切换目录:cd
			cd 目录
			cd 目录/目录
			cd ..  :上一级目录
			cd / 	:根目录
			cd ~	:回家
		创建目录和删除目录
			mkdir 创建
				mkdir 目录名
				mkdir -p a/b/c
			rmdir 删除
				rmdir 目录名:只能删除一个空目录
			

```bash
	展示目录下文件列表(以后使用ll即可)
		ls
		ls:展示的能看见的文件(和目录)的名称
		ls -a:展示所有的文件的名称
			文件前面有"."代表的是隐藏文件
		ls -l:显示文件的详细信息
			简写的方式: ll(★)
		ll -h:友好的显示
		
	浏览文件
		cat:显示文件的所有内容
			cat 文件名
		more:分页显示
			空格:下一页
			回车:下一行
		less:分页显示
			可以通过PgUp PgDn 翻页查看
		tail(★★)
			查看一个文件的后面的内容
			tail -显示后几行 文件名
			tail -f 文件名 
				动态的查看
				例如:
					tail -f catalina.xxx.log
				通过 ctrl+c 结束滚动查看
	
	文件的操作
		创建一个文件
			touch 文件名		创建一个空白的文件
		复制文件
			cp 文件 目录/文件名
				例如:
					cp 1.txt 2.txt
					cp 1.txt 1/1.txt
		移动文件(重命名)
			mv 文件 目录/文件名
			mv 文件名 新文件名
				
		删除文件 rm
			rm 文件名:带询问删除
			rm -f 文件名:不带询问删除
			rm -r 目录:带询问的递归删除
			rm -rf 目录:不带询问的递归删除(谨慎使用)
			
		tar:打包或解压 一个文件或者目录(★★)
			常用的组合
				-cvf :打包一个文件或者目录
				-zcvf:打包并压缩一个文件或者目录 压缩的格式:gzip
				-xvf:解压或者打开一个tar文件
			格式:
				tar 参数 文件名 要打包|解压的文件目录
			
			例如:
				将当前目录下的所有文件打包成test1.tar
					tar -cvf test1.tar ./*
				将当前目录下的所有文件打包并压缩成test2.tar.gz
					tar -zcvf test2.tar.gz ./*
				将test1.tar解压到当前目录
					tar -xvf test1.tar 
				将test1.tar解压到b目录
					tar -xvf test1.tar -C b
```
其他的常用命令
	grep:查找符合条件的字符串(★)
		grep 字符串 
	pwd:显示当前的工作目录
	wget:下载资料
		wget 资源路径
	
vi和vim编辑器(理解中了解)
	编辑普通文件
	三种模式：命令行、插入、底行模式。
	切换到命令行模式：按Esc键；
	切换到插入模式：按 i 、o、a键；
		i 在当前位置生前插入
		I 在当前行首插入
		a 在当前位置后插入
		A 在当前行尾插入
		o 在当前行之后插入一行
		O 在当前行之前插入一行

	切换到底行模式：按 :（冒号）；

管道 | ★
	重要的一个概念，其作用是将一个命令的输出用作另一个命令的输入
	例如:
		在ifconfig的结果里查找 192.168字符串
		ifconfig | grep 192.168
	以后常用
		查找和java相关的进程
		ps -ef | grep java
		查找和3306相关的信息
		ps -ef | grep 3306
	
			
系统管理命令
	date 显示或设置系统时间
		date  显示当前系统时间
		date -s “2014-01-01 10:10:10“  设置系统时间
				
```bash
clear 清屏
	ctrl+l
	
ps 正在运行的某个进程的状态
	ps –ef  查看所有进程
	★ps –ef | grep ssh 查找某一进程

kill 杀掉某一进程
	kill 2868  杀掉2868编号的进程
	★kill -9 2868  强制杀死进程
```

网络管理
	ifconfig:查看所有的网络设置
		ifconfig 网卡名称 down :禁用网卡
		ifconfig 网卡名称 up :启用网卡
	
```bash
ping:和window中一样
	通过ctrl+c取消
	
netstat 查看网络端口。
	netstat -an | grep 3306 查询3306端口占用情况
```

```bash
了解用户管理
	添加
		useradd 用户名:默认会在home目录下给一个用户创建一个目录
		passwd 用户名: 回车输入密码
	
		useradd 用户名 -d /home/目录:创建一个用户然后在指定该用户的家目录
	
	删除
		userdel 用户名:只是删除用户 但是不删除家目录
		userdel -r 用户名:删除用户连带家目录一起删除
		
	切换用户:
		ssh -l 用户名 -p 22 主机
			例如: ssh -l tom -p 22 192.168.17.131
		su - 用户名
		
了解组管理
	添加
		groupadd 组名
		useradd 用户名 -g 组名
	删除
		groupdel 组名
			注意:
				若组下有用户,删除不了
```
文件的权限:

​	普通文件： 包括文本文件、数据文件、可执行的二进制程序文件等。 
​	目录文件： Linux系统把目录看成是一种特殊的文件，利用它构成文件系统的树型结构。  
​	设备文件： Linux系统把每一个设备都看成是一个文件
​	

```bash
通过ll展示的列表
	以 d 开始的是目录文件
	以 - 开始的是普通文件
	
文件的权限9个字母 三个三个一组
	第一组代表的是当前用户的权限
	第二组代表的是组的权限
	第三组代表的是其他用户的权限
	
	r:读  	4
	w:写	2
	x:执行	1
	
chmod 变更文件或目录的权限。
	chmod 755 a.txt 
	chmod u=rwx,g=rx,o=rx a.txt
	chmod 000 a.txt  / 
	★chmod 777 a.txt
	
了解:chown 变更文件或目录改文件所属用户和组
	chown u1:public a.txt	：变更当前的目录或文件的所属用户和组
	chown -R u1:public dir	：变更目录中的所有的子目录及文件的所属用户和组
	格式:
		chown 用户:组 文件
```


​		
回顾:
​	linux :多用户 多任务的操作系统
​	常用命令:
​		cd 切换目录
​			cd /
​			cd ~
​			cd ..
​		ll 展示列表
​		mkdir [-p] 目录
​		rmdir 目录:删除空目录
​		
​		touch 文件名:创建空白文件
​		cp 文件 目录/文件:复制文件
​		mv 文件 目录:移动文件
​		mv 文件 新文件:文件重命名
​		rm -rf 文件|目录:不询问递归删除
​		

```bash
	tar 打包或者解压
		tar -cvf 文件名称 目录|文件  打包
		tar -zcvf 文件名称 目录|文件  打包并压缩
		tar -xvf 文件名称 解压至当前目录
		tar -xvf 文件名称 -C 目录: 解压至指定目录
		
	grep 查找
	| 管道
	
	设置时间
		date -s "时间":设置时间
		ps -ef :查看所有进程
	
	ifconfig:查看ip地址
```

---
layout: post
title: "Shell脚本：判断文件、文件夹是否存在"
date: 2022-04-20
excerpt: "Shell判断文件、文件夹是否存在"
tags: [iOS, Xcode, Products]
comments: true
category: "mac"
---

#### 语法参数说明
```
-e filename #如果 filename为目录，则为真 
-f filename #如果 filename为常规文件，则为真 
-L filename #如果 filename为符号链接，则为真 
-r filename #如果 filename可读，则为真 
-w filename #如果 filename可写，则为真 
-x filename #如果 filename可执行，则为真 
-s filename #如果文件长度不为0，则为真 
-h filename #如果文件是软链接，则为真

```


#### 判断文件夹是否存在


```
	#如果文件夹不存在，则创建文件夹
	tempPath="/home/parasaga/blank"
	if [ ! -d "$tempPath" ]; then
		mkdir $blankPath #这个块种必须存在一行有效代码，否则报错。需要吧if / fi 代码块注释掉或者删除
	fi


```

#### 判断文件是否存在

```
	#如果文件不存在，则创建文件
	tempFile="/home/parasaga/blank/error.log"
	if [ ! -f "$tempFile" ]; then # 需要注意: 符号"!" 前后的空格;  “-f” 前后的空格;  “$tempFile” 前后的空格
		touch $tempFile
	fi


```









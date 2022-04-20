---
layout: post
title: "Xcode11 以后创建的项目 Products目录没有在项目工程目录中"
date: 2022-03-30
excerpt: "Xcode11 以后创建的项目 Products目录没有在项目工程目录中"
tags: [iOS, Xcode, Products]
comments: true
category: "ios"
---

#### 问题描述
```
Xcode11 以后创建的项目 Products目录没有在项目工程目录中
```


#### 解决方法

1. 打开项目，然后进入到你的项目目录并打开project.pbxproj文件;
2.  搜索productRefGroup关键词;
3.  找到如下的结果:

```
	mainGroup = 33F5229D27339ED90048642D;
	productRefGroup = 33F522A727339ED90048642D /* Products */;
```

4. 将上面 mainGroup 对应的值复制给 productRefGroup 的值 如下：

```
	mainGroup = 33F5229D27339ED90048642D;
	productRefGroup = 33F5229D27339ED90048642D /* Products */
```

5. 按 command+s 保存 project.pbxproj 文件,Xcode将自动刷新;

6. Products 目录就出现了;







---
layout: post
title: "用Application Loader或者Transporter上传AppStore IPA包到AppStore出现问题"
date: 2022-03-30
excerpt: "用Application Loader或者Transporter上传AppStore IPA包到AppStore出现问题"
tags: [iOS, error, Application\ Loader, Transporter, UISceneDelegateClassName, IPA]
comments: true
category: "ios"
---

#### 问题描述
```
The filename 未命名.ipa in the package contains an invalid character(s). The valid characters are:A-Z 
,a-z,0-9,dash,period,underscore,but the name cannot start with a dash,period,or underscore. 
```


#### 解决方法

下述是info.plist中关于 UIApplicationScene 的配置块：

1. 手动改ipa名全为ascii码的字符，不要包含中文字符;
	
2. 在Xcode的Build Setting改Product Name，修改规则见 `(1)` ;



> 注: 推荐方法`（2）`，改完后以后不用每次都改。方法`（1）`只能暂时解决这次的问题，下次打包已然有这个问题;




---
layout: post
title: "SceneDelegate在Info.plist中的配置问题"
date: 2022-03-28
excerpt: "Info.plist configuration \"Default Configuration\" for UIWindowSceneSessionRoleApplication contained UISceneDelegateClassName key, but could not load class with name \"xxxxx.SceneDelegate\" "
tags: [iOS, error, Info.plist, UIWindowSceneSessionRoleApplication, UISceneDelegateClassName, SceneDelegate]
comments: true
category: "ios"
---

#### 问题描述
```
2022-03-28 09:46:21.994603+0800 xxxxx-beta[22774:7018437] [SceneConfiguration] Info.plist configuration "Default Configuration" for UIWindowSceneSessionRoleApplication contained UISceneDelegateClassName key, but could not load class with name "xxxxx.SceneDelegate".
2022-03-28 09:46:21.994931+0800 xxxxx-beta[22774:7018437] [SceneConfiguration] Info.plist configuration "Default Configuration" for UIWindowSceneSessionRoleApplication contained UISceneDelegateClassName key, but could not load class with name "xxxxx.SceneDelegate".
2022-03-28 09:46:21.995058+0800 xxxxx-beta[22774:7018437] [SceneConfiguration] Info.plist configuration "(no name)" for UIWindowSceneSessionRoleApplication contained UISceneDelegateClassName key, but could not load class with name "xxxxx.SceneDelegate".
2022-03-28 09:46:21.995239+0800 xxxxx-beta[22774:7018437] [SceneConfiguration] Info.plist configuration "Default Configuration" for UIWindowSceneSessionRoleApplication contained UISceneDelegateClassName key, but could not load class with name "xxxxx.SceneDelegate".
2022-03-28 09:46:21.998237+0800 xxxxx-beta[22774:7018437] [WindowScene] There is no scene delegate set. A scene delegate class must be specified to use a main storyboard file.
```


#### 解决方法

下述是info.plist中关于 UIApplicationScene 的配置块：

``` xml{13}
<key>UIApplicationSceneManifest</key>
<dict>
    <key>UIApplicationSupportsMultipleScenes</key>
    <false/>
    <key>UISceneConfigurations</key>
    <dict>
        <key>UIWindowSceneSessionRoleApplication</key>
        <array>
            <dict>
                <key>UISceneConfigurationName</key>
                <string>Default Configuration</string>
                <key>UISceneDelegateClassName</key>
                <string>xxxxx.SceneDelegate</string>
                <key>UISceneStoryboardFile</key>
                <string>Main</string>
            </dict>
        </array>
    </dict>
</dict>
```



将上述XML中的 `xxxxx` 改为 `$(PRODUCT_MODULE_NAME)`。 如果失败，改为 `$(PRODUCT_NAME)`.



* 参考链接: [https://github.com/bazelbuild/rules_apple/issues/1016](参考链接: https://github.com/bazelbuild/rules_apple/issues/1016
)



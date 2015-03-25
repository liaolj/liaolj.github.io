---
layout: post
title: "NSLogger guilde"
description: ""
category: 
tags: []
---
{% include JB/setup %}


NSLogger 的使用
===
![image](image/nslogger/logDemoRelease_2.gif)
### 一、 创建新项目logDemo

### 二、 添加NSLogger 相关文件文件

下载[NSLogger](https://github.com/fpillet/NSLogger/tree/master/Client%20Logger/iOS)    
只需要将以下文件添加项目中

LoggerClient.h LoggerClient.m LoggerCommon.h NSLogger.h

### 三、. 添加NSLogger头文件以及配置
##### 在AppDelegate.m 文件添加
* 引用头文件

    #import "LoggerClient.h"

* didFinishLaunchingWithOptions函数中添加 如下代码


    LoggerSetViewerHost(NULL, (CFStringRef)@"127.0.0.1", (UInt32)50000);


##### 在ViewController.m 文件添加
* 引用头文件

    #import "LoggerClient.h"
    
* 在 viewDidLoad 函数下添加

    LogMessage(@"net", 1, @"This is for net tag");
    LogMessage(@"audio", 1, @"This is for audio tag");


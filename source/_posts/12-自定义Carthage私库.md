---
title: 12.自定义Carthage私库
date: 2019-02-16 11:17:41
tags: [Carthage]
---
> 本文介绍如何创建一个自己的Carthage仓库

<!--more-->
与cocoapods不同的地方是, Carthage最后使用的是framework，所依赖的仓库根目录下面必须存在一个xcode framework工程。


### 1.创建一个framework工程
### 2.这个工程依赖的其他工程
所以依赖的工程，必须直接或者间接的存在framework。

- 直接依赖framework
- 存在framework工程(包括：是一个Carthage私库)


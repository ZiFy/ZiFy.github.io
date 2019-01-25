---
title: Fastlane打包iOS常见问题
date: 2019-01-25 10:27:44
tags:
---

# 1.打包
在iOS工程根目录下有个fastlane文件夹，注意 Appfile、 Fastfile、Matchfile

![](目录结构.png)

- Appfile :App信息
- Fastfile :脚本命令
- Matchfile :Match配置

 

# 2.常见问题-证书

## 证书不存在

操作步骤：

1. fastlane match nuke  ：移除失效证书
2. fastlane match development  ：注册证书
 

# 3.常见问题-二次认证
appleid开启二次认证后，需要每次都输入6位验证码

通过配置

- FASTLANE_APPLE_APPLICATION_SPECIFIC_PASSWORD
- FASTLANE_PASSWORD
- MATCH_PASSWORD
- FASTLANE_SESSION

## session失效
fastlane spaceauth -u your@appid.com 重新生成


# 4.常见问题-latest\_testflight\_build\_number
### 问题描述：
![](latest_testflight_build_number.png)

### 问题原因分析: 
一个未发布的app，没有发一个ipa到appstoreconnect的时候，latest\_testflight\_build\_number命令找不到一个版本，接口返回报错。

### 解决方法：
只要appstoreconnect上面有一个版本，就不会报错，解决方法很简单，第一次使用的时候，注销掉latest\_testflight\_build\_number代码，使用配置好的buildnumber即可。

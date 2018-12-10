---
title: sonarQube 分析Objective-C
date: 2018-12-03 18:01:35
tags: [sonarQube, Objective-C]
categories: [iOS]
---
> 使用sonarQube分析Objective-C

<!-- more -->

# sonarQube 分析Objective-C
## 安装
### 安装homebrew
```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
### 安装mysql
```
brew install mysql
```
#### mysql 配置教程:
https://www.jianshu.com/p/4cb5ef29a099

### 安装Java
安装java ：
http://www.oracle.com/technetwork/java/javase/downloads/index.html

### 安装sonarQube
```
brew install sonarqube
```
也可以自己到官网下载http://www.sonarqube.org/downloads/

解压后移到/usr/local 
我的目录 
```
/usr/local/sonarqube-6.7.5
```
### 安装xcpretty
```
gem install xcpretty
```
### 安装OCLint
```
brew tap oclint/formulae
brew install oclint
```
### 安装sonar-scanner
```
brew install sonar-scanner
```
### 安装gcovr
```
brew install gcovr
```
### 安装sonar-objective-c-plugin
配置
sonarqube的配置文件conf/sonar.properties


配置sonar连接mysql
// 注： 我配置mysql重启服务，链接不上。

```
// 配置sonar连接mysql
sonar.jdbc.url=jdbc:mysql://localhost:3306/sonar?useUnicode=true&characterEncoding=utf8&rewriteBatchedStatements=true&useConfigs=maxPerformance&useSSL=false
sonar.jdbc.username=root
sonar.jdbc.password=root

// 其他
sonar.sorceEncoding=UTF-8
sonar.login=admin
sonar.password=admin

运行
支持的命令有： start/restart/stop/status
sudo /usr/local/sonar/bin/macosx-universal-64/sonar.sh start
```

## 其他
### 安装sonarQube汉化包
https://github.com/SonarQubeCommunity/sonar-l10n-zh/releases/latest
找到jar包，添加到extensions/plugins

我用的sonarQube6.5对应汉化包1.17

添加完成后，需要重启服务才能生效。

```
sonar restart
```

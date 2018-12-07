---
title: 我的Hexo使用教程
---
使用Hexo搭建博客

## Quick Start

### Create a new post

``` bash
$ hexo new "My New Post"
```

More info: [Writing](https://hexo.io/docs/writing.html)

### Run server

``` bash
$ hexo server
简写
$ hexo s
```

More info: [Server](https://hexo.io/docs/server.html)

### Generate static files

``` bash
$ hexo generate
简写
$ hexo g
```
或者

More info: [Generating](https://hexo.io/docs/generating.html)

### Deploy to remote sites

``` bash
$ hexo deploy
简写
$ hexo d

```
### clean
小心使用清理命令，会把post目录下面的文件都清理掉

```
hexo clean
```

More info: [Deployment](https://hexo.io/docs/deployment.html)

### 快捷命令：




测试：
```
hexo g && hexo s
```

发布：

```
hexo g && hexo d
```
## 安装主题

资源网站 https://hexo.io/themes/

### 下载主题
下载主题到themes 目录下。有2种主流方式。

#### git clone
可以直接 clone 到 themes 目录下，优点是如果对主题有调整需求可以同时提交到 git 控制中。

``` bash
$ git clone https://github.com/olOwOlo/hugo-theme-even themes/even
```
#### git submodule
也可以添加到 git 的 submodule 中，优点是后面讲到用 travis 自动部署时比较方便。如果需要对主题做更改，最好 fork 主题再做改动。

``` bash
$ git submodule add https://github.com/olOwOlo/hugo-theme-even.git themes/even

git submodule add https://github.com/ZiFy/hexo-theme-next.git themes/next
```

### 配置安装
到根目录下找到配置文件_config.yml -> theme: landscape

theme: 主题key
landscape: 对应themes目录下的文件夹名


## 使用travis 自动部署



## THANKS
[hexo从零开始到搭建完整](https://www.cnblogs.com/visugar/p/6821777.html)

[5分钟 搭建免费个人博客](https://www.jianshu.com/p/4eaddcbe4d12)
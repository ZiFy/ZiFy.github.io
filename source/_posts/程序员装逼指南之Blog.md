---
title: 程序员装逼指南之Blog
tags: [Hexo]
categories: [Hexo]
author: Zify
comments: true
date: 2018-12-05 15:19:00

---
## GitHub Pages

[GitHub Pages](https://pages.github.com/)

## hexo

### 教程

### 以下几点特别说明一下
#### 使用hexo deploy发布

```
# _config.yml
deploy:
  type: git
  repo: https://github.com/ZiFy/ZiFy.github.io.git
  branch: master
  message: "hexo自动发布" 
```
特别提醒：
这个命令会把你的文件都删了，只保留发布的文件。
所以，请一定要选择另一个分支开发，这样才能把markdown文件保留下来。

```
一键发布测试
$ hexo g&&hexo s
一键发布命令
$ hexo g&&hexo d
```

#### 使用CI自动发布


#### markdown支持本地图片
[使用hexo-asset-image](https://blog.csdn.net/sugar_rainbow/article/details/57415705)




## Next


next 是一款了不起的hexo主题，支持很多功能。最重要是风格适合程序员。 [你是我的眼，眼里只有黑白色]

[hexo-theme-next](https://theme-next.org/docs/theme-settings/)

![hexo-theme-next-github](./hexo-theme-next-github.png)

### 可以添加的功能
[Next第三方服务集成](http://theme-next.iissnan.com/third-party-services.html#comment-system)

#### 评论 Gitalk

[github OAuth Apps](https://github.com/settings/developers)

[Annie主题使用Gitalk](https://sariay.github.io/2018/11/18/Annie%E4%B8%BB%E9%A2%98%E4%BD%BF%E7%94%A8Gitalk/)

```
# /theme/next/_config.yml
gitalk:
  enable: true
  github_id: Zify # Github repo   owner
  repo: blog_comment_repo # Repository name to store issues.
  client_id: c30a8xxxx # Github Application Client ID
  client_secret: 916ce8fxx # Github Application Client Secret
  admin_user: Zify # GitHub repo owner and collaborators, only these guys can initialize github issues
  distraction_free_mode: true # Facebook-like distraction free mode
```

##### 未找到相关的 Issues 进行评论
使用自己的账号登录一下，打开页面就会自动初始化。
![gitalk-comment](gitalk-comment.png)

#### Baidu analytics
https://tongji.baidu.com/

#### google analytics
https://analytics.google.com/

#### 使用busuanzi统计阅读次数
```
busuanzi_count:
  enable: true
  total_visitors: true
  total_visitors_icon: user
  total_views: true
  total_views_icon: eye
  post_views: true
  post_views_icon: eye
```
#### RSS

```
$ npm install --save hexo-generator-feed
```
[next配置RSS](https://www.jianshu.com/p/264024768d03)

#### 标签页面，分类页面
[hexo 创建文章、标签、分类](https://blog.csdn.net/qq_32337109/article/details/78755662)

#### 页面-阅读排行
[hexo page 阅读排行](https://hoxis.github.io/hexo-next-read-rank.html)

#### next自定义样式
[hexo-theme-next主题设置](https://www.jianshu.com/p/37769040891f)

[Hexo-NexT配置超炫网页效果](https://www.jianshu.com/p/9f0e90cc32c2)

## hexo-admin发布平台 
（不重要，hexo3.8, hexo-admin2.3.0下存在bug）

[hexo-admin](https://jaredforsyth.com/hexo-admin/)

[那个人的hexo-admin教程](https://albenw.github.io/posts/4ffa5bc6/)

```
npm install --save hexo-admin
hexo server -d
open http://localhost:4000/admin/
```

### SEO优化
[Hexo博客Next主题SEO优化方法](https://hoxis.github.io/Hexo+Next%20SEO%E4%BC%98%E5%8C%96.html)

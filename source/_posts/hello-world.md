---
title: Hello World to Hexo
date: 2020-09-11 20:26:00
author: zhangyuanes
categories: 博客搭建
tags:
  - Hexo
  - Gitpage
---

## 说在前面

我的blog很大程度上不算blog，算是个整合贴。我的blog的流程一般是这样的：

遇到一个实际问题，或者从完全不了解到初步入门，我会保留自己在解决这个问题的浏览器历史搜索记录（请务必科学上网）、大致流程、特殊问题和解决方案。

一般不再书写别人已经写作的内容，仅仅贴上链接。虽然不排除链接实效的情况，但是一般来说链接是稳定的。万一实在链接失效，也可以搜索关键词找寻更新的教程。在此不再赘述。

## [使用Github Pages和Hexo构建个人博客][gitpage_hexo]

此项目是基于gitpage的托管，在本地nodejs平台渲染hexo项目生成的静态网站。

静态博客文档的书写一方面是记录了博主的工作，另一方面在线分享也节省了有同样问题或者想要了解、从事某方面研究的人的调研时间，一举两得。

感谢所有愿意分享的博主，你们的无私让整个社区更加美好。

### [Valine无后端评论系统][Valine]

这是静态网站中不那么静态的部分——评论系统。

后台存储使用的是LeanCloud。详细配置文档中有细致说明。

## [使用jekyll构建gitpage静态网页][gitpage_jekyll]

这是另一种实现静态网站的方案，但是jekyll是基于ruby的，对于windows用户可能不是那么友好，所以推荐使用前面的方案。

## [Ubuntu安装Node环境][installNode]

windows下直接安装就OK。这里采用了NVM的Node版本管理来做安装,并使用国内镜像。

### [NVM github][NVM github]

## 仓库主题下载使用

[仓库地址][repo],请参照 readme运行，参照 themes\hexo-theme-matery\README_CN.md 中说明配置详细主题信息.

根据自己需求进行自定义修改和美化的blinkfox的hexo主题。

### 准备工作

安装NodeJS（Windows，Linux，MacOS均可）。

### Fork仓库后使用git克隆项目

点击fork按钮fork到自己的账号下，这样你的配置就可以保存下来了。

```
git clone https://github.com/zhangyuanes/blinkTheme.git
```

###  进入项目文件夹，安装依赖包

```
cd blinkTheme
npm install
```

###  清理并生成渲染

```
npm run clean
npm run build
```

###  本地预览

```bash
npm run server
```

访问`http://localhost:4000`即可看到页面。

###  使用hexo-admin做后台dashboard

预先配置有hexo-admin，在url结尾加入`/admin`即可进入管理页面，可以在线md交互预览编辑。用户名和密码我配置的为：yanbo，你可以修改配置文件来自定义，相关配置在`_config.yml`中:

```yml
# hexo-admin authentification
# 在本地浏览的时候在url之后加上admin即可访问
# 这里的password是密码经过sha256加密
admin:
  username: yanbo
  password_hash: $2a$10$SD3chEWmZ4/qWCOOvmVv3ut5/lKgPqDx5YBLwtZHt07/XzcG4TEAK
  secret: yanbo
  deployCommand: 'hexo-deploy.bat'
```

###  推送到github.io

如果你没有设置这个gitpage仓库，[参考这里](https://zhangyuanes.github.io/2020/09/11/hello-world/).

需要预先设置项目根目录下的`_config.yml`中的部署deploy配置：

```
# Deployment
deploy:
  type: git
  repo: https://github.com/********/********.github.io.git
  branch: master
```

预览渲染没有问题可以使用命令推送到gitpage，推从到github.io仓库中，使用命令：

```bash
npm run deploy
```

当显示成功后刷新仓库，就可以访问到对应的页面了，页面地址为 `https://YourGithubName.github.io`。

### 编写你的文章

清除`source/_posts`下全部文章页（但请至少保留一个md文件用于生成页面，否则build会失败），完成`_config.yml`中其他个性化配置后重新清理并生成渲染，预览后推送即可。

`_config.yml`已经添加很多中文注释，如果需要请按照注释修改即可。

本项目代码唯一需要用户单独存档的仅仅为`source/_posts`下的原始md文章页面以及对应的配图。

配图建议使用图床，这样就不用担心相对引用，相关文章[参考这里](https://zhangyuanes.github.io/2021/01/19/ji-lu/bo-ke-da-jian/tu-chuang-da-jian/)。本仓库的配图还是比较大的，后续会逐渐修改为图床链接。

补：如果不是图床的图片，配图请放在`source/medias`中，如果需要分类请在此文件夹下新建文件夹放置即可，在页面中引用地址为：`/medias/******.jpg`。

md文章的编写如果不清楚可以先参考我的md，里面基本内容包括：header和正文。

header需要用三个连接号显式表示出来，字段和含义如下 ： `title` 文章标题, `date` 时间, `author` 作者, `categories` 分类,`tags` 文章标签。

header写完后就是正文，直接兼容全部的md语法，自由书写即可。

```md
---
title: Hello World to Hexo
date: 2020-09-11 20:26:00
author: zhangyuanes
categories: 博客搭建
tags:
  - Hexo
  - Gitpage
---

<你的文章内容>

```

### 如有其他问题请提交issue或发邮件询问。


[gitpage_hexo]:https://developer.aliyun.com/article/387750
[Valine]:https://valine.js.org/
[gitpage_jekyll]:https://sspai.com/post/54608
[installNode]:https://mupceet.com/2020/02/the-best-way-to-install-nodejs/
[NVM github]:https://github.com/nvm-sh/nvm#installing-and-updating
[repo]:https://github.com/zhangyuanes/blinkTheme
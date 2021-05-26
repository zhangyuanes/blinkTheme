# blinkfox Theme fix to myself

[![Build Status](https://secure.travis-ci.org/blinkfox/blinkfox.github.io.svg)](https://travis-ci.org/blinkfox/blinkfox.github.io) [![HitCount](http://hits.dwyl.io/blinkfox/blinkfox.github.io.svg)](http://hits.dwyl.io/blinkfox/blinkfox.github.io) [![GitHub license](https://img.shields.io/github/license/blinkfox/blinkfox.github.io.svg)](https://github.com/blinkfox/blinkfox.github.io/blob/hexo/LICENSE) [![GitHub forks](https://img.shields.io/github/forks/blinkfox/blinkfox.github.io.svg)](https://github.com/blinkfox/blinkfox.github.io/network) [![GitHub stars](https://img.shields.io/github/stars/blinkfox/blinkfox.github.io.svg)](https://github.com/blinkfox/blinkfox.github.io/stargazers)

根据自己需求进行自定义修改和美化的blinkfox的hexo主题。

> 我的 [personal blog](https://zhangyuanes.github.io/) ，可以点击查看预览。

## How to Use

安装NodeJS（Windows，Linux，MacOS均可）。

使用git克隆项目

```
git clone https://github.com/zhangyuanes/blinkTheme.git
```

进入项目文件夹，安装依赖包

```
npm install
```

清理并生成渲染

```
npm run clean
npm run build
```

本地预览

```bash
npm run server
```
访问`http://localhost:4000`即可看到页面。预先配置有hexo-admin，在url结尾加入`/admin`即可进入管理页面，可以在线md交互预览编辑。

预览渲染没有问题可以使用命令推送到gitpage远程仓库：需要预先设置`_config.yml`中的部署配置

如果你没有设置这个gitpage仓库，[参考这里](https://zhangyuanes.github.io/2020/09/11/hello-world/)

```
# Deployment
deploy:
  type: git
  repo: https://github.com/********/********.github.io.git
  branch: master
```

清除`source/_posts`下全部文章页（但请至少保留一个md文件用于生成页面，否则build会失败），完成`_config.yml`中其他个性化配置后重新清理并生成渲染，预览后推送即可。

本项目代码唯一需要用户单独存档的仅仅为`source/_posts`下的原始md文章页面以及对应的配图，配图建议使用图床，这样就不用担心相对引用，相关文章[参考这里](https://zhangyuanes.github.io/2021/01/19/ji-lu/bo-ke-da-jian/tu-chuang-da-jian/)。本仓库的配图还是比较大的，后续会逐渐修改为图床链接。

补：如果不是图床的图片，配图请放在`source/medias`中，如果需要分类请在此文件夹下新建文件夹放置即可，在页面中引用地址为：`/medias/******.jpg`。

## License

[Apache License 2.0](http://www.apache.org/licenses/LICENSE-2.0)

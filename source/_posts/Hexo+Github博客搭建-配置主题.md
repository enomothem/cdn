---
title: Hexo+Github搭建博客-配置主题
tags: 个人博客搭建
author: Enomothem
abbrlink: '5165'
date: 2020-12-10 16:48:06
---

# [Hexo+Github Page博客搭建-配置主题]()

#### ※搭建博客系列目录

1. [准备环境](https://enomothem.cn/posts/1722.html)
2. [Hexo部署](https://enomothem.cn/posts/204c.html)
3. [Github部署](https://enomothem.cn/posts/c7f.html)
4. 绑定域名
5. <font color='grenn'>更换主题☚</font>
6. 配置主题
7. 发布文章
8. Picgo+Typora写文章
9. Typora配置
10. 换电脑后，重新安装环境
11. 更新主题





### 声明：关于一些描述的约定

>  为了方便描述，我们约定以下名称，更容易表述。

以下```博客文件夹```表示放关于博客相关东西的文件夹，包括用到的软件

以下```Hexo文件夹```表示Hexo初始化（执行hexo init的那个）的文件夹，一般命名为blog

以下`主题文件夹`表示`Hexo文件夹`下的`themes`下的你所用的主题文件夹

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201213124132419.png)





> 由于每个主题的配置不一样，具体还要看主题文档。这里只做简单配置，还有一些实用的配置，具体我会持续更新。

> 本配置就以我的主题`hexo-theme-matery`为例。

> 其更多的还需要自己去感受，一般配置文件里都会做出解释，可以根据自己的需求去变更。

## Ax 基础配置

### a 修改主题配置

打开`Hexo文件夹`下的`主题文件夹`，配置`_config.yml`

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201213172803225.png)

修改为自己的联系地址，如果没有的空着就行了

```yml
# The configurations of the second line of home banner
# icon/button will not show up if you leave the corresponding socialLink empty
# 首页 banner 中的第二行个人信息配置，留空即不启用
socialLink:
  github:  https://github.com/enomothem
  email: enomothem@outlook.com
  facebook: # https://www.facebook.com/xxx
  twitter: # https://twitter.com/xxx
  qq: 251051821
  weibo: # https://weibo.com/xxx
  zhihu: # https://www.zhihu.com/xxx
  rss: true # true、false
```

根据代码我们可以知道打赏的图片路径

```yml
# 是否激活文章末尾的打赏功能，默认激活（你替换为的你自己的微信、支付宝二维码图片、或者使用网络图片也可以）.
reward:
  enable: true
  title: 你的赏识是我前进的动力
  wechat: /medias/reward/wechat.png
  alipay: /medias/reward/alipay.jpg
```

打开`主题文件夹`下的`source/medias/reward/`

把自己的微信，支付宝图片替换已有的，文件名不变。

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201213173501301.png)
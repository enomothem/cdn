---
title: Hexo+Github搭建博客-绑定域名
tags: 个人博客搭建
author: Enomothem
abbrlink: f480
date: 2020-12-13 14:48:06
---

# [Hexo+Github Page博客搭建-绑定域名](https://enomothem.cn/posts/1722.html)

#### ※搭建博客系列目录

1. [准备环境](https://enomothem.cn/posts/1722.html)
2. [Hexo部署](https://enomothem.cn/posts/204c.html)
3. [Github部署](https://enomothem.cn/posts/c7f.html)
4. <font color='grenn'>绑定域名☚</font>
5. 更换主题
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

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201213124132419.png)





> 这一步主要是为了把github的地址换成自己的域名，那样更方便记忆。不需要也行哦。

## Ax 注册域名

> ~~注册~~购买域名，直接买三年更划算哦，首年有优惠。

- Godaddy：https://sg.godaddy.com/zh   最大
- Gandi：https://v4.gandi.net/                台湾的
- Hover：https://www.hover.com/           快
- namesilo：https://www.namesilo.com/  便宜
- Namecheap：https://www.sandbox.namecheap.com/  后缀多且便宜
- 万网：https://wanwang.aliyun.com/ 国内
- 网易：https://domain.163yun.com/  国内
- 腾讯：https://dnspod.cloud.tencent.com/  国内



## Bx 域名解析

登入你买域名的网站，然后找到域名控制台。

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201213155909599.png)

#### a 增加记录

记录值填你博客的地址，打开CMD，ping <yourname>.github.io

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201213160523269.png)

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201213160409331.png)

## Cx 域名绑定

#### a 增加文件

在`Hexo文件夹`下的 source 目录下新建一个 CNAME 文件，里面写入自己的域名，然后保存。

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201213160910264.png)

#### b 绑定为Https

打开GitHub，进入博客仓库 => `Settings` => `Github pages`

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201213161246983.png)

## Dx 验证

打开浏览器，输入你的域名

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201213161949505.png)

nice！

<font color='orange'>╰(\*°▽°\*)╯💥💥💥💥</font>


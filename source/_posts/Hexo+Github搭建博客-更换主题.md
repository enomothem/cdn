---
title: Hexo+Github搭建博客-更换主题
tags: 个人博客搭建
author: Enomothem
abbrlink: '3903'
date: 2020-12-13 15:48:06
---

# [Hexo+Github Page博客搭建-更换主题](https://enomothem.cn/posts/1722.html)

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

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201213124132419.png)



> Hexo默认部署的主题是`landscape`，我使用的是`hexo-theme-matery`，之前使用过`Next`的也不错



## Ax 下载主题

进入Hexo网站挑选自己满意的主题：https://hexo.io/themes/

下载到`Hexo文件夹`下的`themes`下，方式有两种

#### a 方式一

直接下载到本地，把文件Copy进去。

#### b 方式二

进入themes文件夹中右键打开git bash：

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201213165129098.png)

先复制主题的下载路径，在bash中输入：

``` bash
$ git clone 图上复制的地址
```

就会发现在themes文件夹下面多出了你下载的主题：

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201213165344199.png)

## Bx 切换主题

进入`Hexo文件夹`，配置`_config.yml`

```yml
# Extensions
## Plugins: https://hexo.io/plugins/
## Themes: https://github.com/blinkfox/hexo-theme-matery
theme: hexo-theme-matery   ## 你的主题名
```

## Cx 验证

三条命令

```bash
$ hexo clean
$ hexo generate
$ hexo deploy
```

到浏览器输入你的博客域名查看是否成功。

当然，更新会有些慢，我们可以先到本地测试。

```bash
$ hexo cl
$ hexo g
$ hexo server
```

测试成功后再部署到GitHub。




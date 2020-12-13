---
title: Hexo+Github搭建博客-Hexo部署
tags: 个人博客搭建
author: Enomothem
abbrlink: 204c
date: 2020-12-13 10:48:06
---

# [Hexo+Github Page博客搭建-Hexo部署](https://enomothem.cn/posts/204c.html)

### ※搭建博客系列目录

1. 准备环境
2. <font color='grenn'>Hexo部署☚</font>
3. Github部署
4. 绑定域名 
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



## Ax 部署Hexo到本地

> 这一步，就是将Hexo的博客文件下载到本地。

### a 创建博客文件夹

进入`博客文件夹`创建一个blog的文件夹（以后都称之为`Hexo文件夹`），进入之后右键打开git bash.

> 这一步最好像我在准备环境里说的那样，博客的东西都放在一个大的文件夹下。这个文件夹也是。

### b 部署

```hexo init```

- node_modules：是依赖包
- public：存放的是生成的页面
- scaffolds：命令生成文章等的模板
- source：用命令创建的各种文章
- themes：主题
- _config.yml：整个博客的配置
- db.json：source解析所得到的
- package.json：项目所需模块项目的配置信息


















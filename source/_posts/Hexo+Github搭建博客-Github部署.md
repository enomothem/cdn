---
title: Hexo+Github搭建博客-Github部署
tags: 个人博客搭建
author: Enomothem
abbrlink: c7f
date: 2020-12-13 12:48:06
---

# [Hexo+Github Page博客搭建-Github部署](https://enomothem.cn/posts/c7f.html)

### ※搭建博客系列目录

1. [准备环境](https://enomothem.cn/posts/1722.html)
2. [Hexo部署](https://enomothem.cn/posts/204c.html)
3. <font color='grenn'>Github部署☚</font>
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





## Ax 准备

> 看这篇文章请不要在GitHub翻译成中文，以下都是以英文方式描述。

- 注册Github
- 创建一个库

### a 注册

打开Github官方网站：https://github.com/

右上角的```Sign in```，然后点击```Create an acount```

分别是用户名、注册邮箱（后面需要用到）、密码。



### b 创建库

登入Github后，右上角的加号

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201213005618942.png)

在这里面填写<yourname>.github.io，其它默认就好，然后拉到最下面```Create repository```

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201213010151007.png)

<yourname>表示你注册时的用户名。

好，这一步完成。



## Bx 配置Git用户名和邮箱

在桌面右键，打开git bash，输入以下两条命令。

#### a 配置用户名

```$ git config --global user.name "这里填你注册时的用户名"```

#### b 配置邮箱

```$ git config --global user.email "这里填你注册时的邮箱"```

#### c 验证

查看文件：```C:/Users/[username]/.gitconfig```

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201213011548694.png)



## Cx Hexo本地静态部署到Github Pages上

### a Hexo本地静态测试

首先测试本地静态，打开`Hexo文件夹`，右键打开Git bash。

``` bash
$ hexo g && hexo s
```

在浏览器中访问给出的地址

> <font color='red'>！如果server运行失败，安装hexo-server</font>

```bash
$ npm i hexo-server
```

> <font color='red'>！如果出现端口冲突，则运行下面命令更改一个端口。</font>

``` bash
$ bash hexo s -p "这里填写一个更大的，以防冲突"
```

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201213124908587.png)

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201213125224884.png)

> 这里我是更换主题之后的，第一次应该是默认的主题。

这里就会看到Hexo的初始页面，在git bash中按`Ctrl + C` 结束

### b 发布到Github Pages

♘ 首先安装`deploy`部署插件，在`Hexo文件夹`中打开git bash

```bash
$ npm install hexo-deployer-git --save
```

♘ 本地关联Github，输入命令：

```bash
$ ssh-keygen -t rsa -C "你的邮箱地址"
```

一直回车就生成了一个密钥。找到这个密钥并输出：

```bash
$ cd ~/ .ssh
$ cat id_rsa.pub
```

把输出的密钥先复制；

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201213131618161.png)

进入Github => 登入后，右上角的头像，点击`Setting` => 左侧找到`SSH and GPG keys`

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201213130711577.png)

点击`New SSH key`，title随便填写，key复制刚才生成的。

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201213130905068.png)

完成后，回到在`Hexo文件夹`路径下的`git bash`，验证：

```bash
$ ssh -T git@github.com
```

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201213131148711.png)

看到Hi，就成功了。

> 马上就要成功了，先稳一手，稍微的修改一下自己的博客。

☣ 进入到`Hexo文件夹`，最好先安装一个Notepad++软件，非常的不错，打开配置文件`_config.yml`

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201213132452215.png)

``` yml
# Site
title: 字星河     # 博客名
subtitle: Enomothem  # 子标题
description: 真正的改变只能发生在原则层面 # 描述、个性签名
keywords: 
author: Enomothem # 文章作者名
language: zh-CN
timezone:
```

☣ 看到最底部

```yml
# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  repository: git@github.com:enomothem/enomothem.github.io.git
  branch: master
```

这里把我的enomothem替换成你的github名字，两个都要。

**☛ 最后一步，上传到GitHub**

> 以后每次发文章都会使用到这三条命令，这是你的老朋友哦。

心情好的时候，欸，我打全：

```bash
$ hexo clean
$ hexo generate
$ hexo deploy
```

诶，我又不想打全了，可以这样偷懒：

```bash
$ hexo cl && hexo g && hexo d
```

服气。

### c 验证

- 在浏览器中输入`http://<你github的用户名>.github.io`
- 回车
- <font color='grenn'>欸，成功了，有没有。完美！</font> 💖💖💖

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201213134349915.png)
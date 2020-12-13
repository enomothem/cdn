---
title: Mysql数据库之连接图形化
tags: Mysql
author: Enomothem
abbrlink: '3012'
date: 2020-12-09 12:50:06
---

# Mysql数据库之连接图形化

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/210652-1494421612860b.jpg)

[toc]

## Ax 准备

- Navicat for MySQL 12

  下载地址：https://www.52pojie.cn/thread-952490-1-1.html    // windows

  下载地址：https://www.52pojie.cn/thread-957406-1-1.html    // mac

- Navicat 15

	下载地址：http://www.navicat.com.cn/download/navicat-premium  // 免费14天



## Bx 安装

> 安装都默认就行，路径改一下。

![Enomothem](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201211102719945.png)

安装完成后打开。

## Cx 连接

### a 11 版本使用

**新建一个连接，然后连接名(随意),root的密码**

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201210114215698.png)

> <font color='orange'>注意：</font><font color='red'>如果出现报错，使用CMD登入Mysql输入下面代码。</font>


```c
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '123456';
FLUSH PRIVILEGES;
```

### b 15版本使用

**新建一个连接，然后连接，输入root密码**

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201211104651747.png)

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201211105627171.png)

## Dx 参考

[1] https://www.cnblogs.com/Kathrine/p/12844846.html#4646661
---
title: Mysql数据库之彻底删除
tags: Mysql
author: Enomothem
abbrlink: 1adb
date: 2020-12-09 12:48:06
---

# Mysql数据库之彻底卸载

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/t0197520a0763752dbb.jpg)

## Xa 场景

> 有时候在卸载mysql后，再次安装总会出错，这时我们就需要彻底的把它删除，干干净净的。

#### Menu 目录

- 软件卸载
- 隐藏文件
- 删注册表

## Xb 方法

#### Ax 软件卸载

1. **快捷键```Ctrl + R```打开运行**

2. **输入```control```打开控制台**

3. **点击卸载程序**

   ![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201209235001737.png)

4. **搜索mysql，卸载**

   ![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201209235042761.png)

#### Bx 隐藏文件

1. 打开隐藏文件夹

   ![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201209235217352.png)

2. 删除隐藏目录下的MySQL

   ```C:\ProgramData\MySQL```

#### Cx 删注册表

1. **快捷键```Ctrl + R```打开运行**

2. 输入```regedit```打开注册表

3. 删除以下注册表，如果没有查到的就不用管

   ```html
   HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Eventlog\Application\MySQL
   HKEY_LOCAL_MACHINE\SYSTEM\ControlSet002\Services\Eventlog\Application\MySQL
   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Eventlog\Application\MySQL
   ```

## Xc 参考

[1] https://www.cnblogs.com/hskw/p/9298108.html
[2] https://www.jb51.net/article/52806.htm
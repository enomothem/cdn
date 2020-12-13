---
title: Mysql数据库之安装
tags: Mysql
abbrlink: '579'
date: 2020-12-09 12:48:06
---



# Mysql数据库之安装

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/t0148bbf85c878da0b8.jpg)

## Ax Introduction 介绍

MySQL是世界上最受欢迎的开源数据库。无论您是快速增长的Web资产，技术ISV还是大型企业，MySQL都能经济高效地帮助您交付高性能，可扩展的数据库应用程序。



## Bx Installation 安装

#### a 下载

https://dev.mysql.com/downloads/

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201209230859167.png)

上面那个是web版本，所以我们选择下面的。

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201209231255940.png)

#### b 安装

> 以下没有提到的全默认。

1. Choosing Setup Type 选择```Custom```
2. Select Products and Features 选择 ```MySQL Server -> MySQL Server 8.0 -> MySQL Server 8.0.18-X64```点击绿色移动到右边 Next

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201209232022372.png)
3. Accounts and Roles 输入你的Root密码两次，```Next```
4. Windows Service 步骤可以更改MySQL的服务名，取消开机自启（下面的勾勾取消）
5. Apply Configuration 最后一步，```Excute```=>```Finish```

#### C 环境变量

我的电脑 =>属性 =>高级系统设置 =>环境变量=>系统环境变量

找到Path，编辑，新建，添加下面这个（如果不是默认的以你安装的路径为准）

```C:\Program Files\MySQL\MySQL Server 8.0\bin```



## Cx Verification 验证

#### a 打开CMD,开启服务

```net start MySQLIk```

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201209233406604.png)

#### b 连接数据库

```mysql -uroot -p```

![](https://gitee.com/enomothem/myblogphoto/raw/master/img/image-20201209233644081.png)


## Dx References 参考

[1] https://www.mysql.com/products/

[2] https://www.cnblogs.com/xiaokang01/p/12092160.html
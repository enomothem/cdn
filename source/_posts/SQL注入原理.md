---
title: SQL注入原理
author: 云歌
tags: Web漏洞
abbrlink: d23e
date: 2019-06-14 10:29:33
---

<h2>SQL注入漏洞（SQL injection）</h2>

#### 仅供学习交流，谨记国家网络安全法。

## Ax_概述

---



<font face="黑体" color=#ADFF2F size=5 face="楷书">为了更好的研究SQL注入，必须深入每种数据库的SQL语法及特性。</font>

<font color=red size=6>!!! 是Web层面最高危的漏洞之一。</font>

在2005年前后，SQL漏洞随处可见，用户在搜索时，输入一个单引号就可以检测出这种漏洞。

2008年-2010年期间，SQL注入漏洞连续3年在OWASP年度十大漏洞排行中排名第一。

### 定义：

```
绕过程序限制，使用户输入的数据带入数据库执行，利用数据库的特殊性获取更多的信息或者更大的权限。
```



### 原理：

> **SQL注入形成的原因就是：用户输入的数据被SQL解释器执行。**

在一个表单中：

账号：                    密码：             

输入用户名“ `or 1=1-- ” ,密码随意，也可不填，点击登入，发现可以正常登入，这是为什么呢？

> select count(*) from admin where username='admin' and password='password'

在数据库中，存在admin用户，并且密码为password，所以此时返回结果为“1”。显然，1大于0，所以通过验证，用户可以成功登陆。

> select count(*) from admin where username='' or 1=1--' and password=''

终于找到问题的根源了，SQL语句的本义是：

> username=‘账户’  and  password=‘密码’

而现在变为：

> username=‘账户’ or 1=1--’ and password=‘’

此时的password被注释！，而username=‘账户’ or 1=1  这句话永远为真，最终执行相对于：

> select count（*）from admin          //查询admin表所有数据条数

很显然，条数大于1，验证通过，这就是一次简单的SQL注入，虽然简单，但是危害很大。可以对专门的靶场进行试验。

利用以下语句可以直接把admin表直接删除，危害极大，请勿随意对网站进行测试，仅供学习交流

> `or 1=1; drop table admin --

PS1:在SQL注入前，要判断该数据库类型。

### 注入漏洞分类

> 明白了概念，对注入的作用是事半功倍滴效果呀！
>
> 常见的SQL注入类型有**数字型和字符型**。也有更细的分类，不管分类如何，攻击者的目的只有一点--->**绕过程序限制**，使用户输入的数据带入数据库执行，利用数据库的特殊性获取更多的信息或者更大的权限。

#### 数字型注入

​	当输入的参数为整型时，则可以认为是数字型注入。

比如：ID、年龄、页码等等。

假设URL为http://www.xxx.com/test.php?id=8 

可以猜测SQL语句为：

```mysql
select * from table where id=8
```

测试步骤

①HTTP://www.xxx.com/test.php?id=8'

使页面报错，无法从数据库获取数据，使页面出现异常。

②HTTP://www.xxx.com/test.php?id=8 and 1=1

语句执行正常，返回数据与原始数据无任何差异。

③HTTP://www.xxx.com/test.php?id=8 and 1=2

语句执行正常，但无法查询出数据，因为“and 1=2”始终为假。返回数据与原始请求有差异。

以上三个步骤全部满足则程序可能存在SQL注入漏洞。

1. 数据型注入最多出现在ASP、PHP等弱语言中。 #弱类型语言会自动推导变量类型。

#### 字符型注入

当输入的参数为字符串时，称为字符型。字符型一般需要单引号来闭合。

- 数字型
  ```mysql
  select * from table where id = 8
  ```
  
- 字符型

  ```mysql
  select * from table where username='admin'
  ```

字符型的关键在于：如何闭合SQL语句以及注释多余的代码。

当查询字符串时，SQL代码如下

```mysql
select * from table where username ='admin'
```

①输入“admin and 1=1”,无法进行注入。被数据库当作字符串查询

```mysql
select * from table where username ='admin and 1=1'
```

②输入“admin' and 1=1 --”,继续注入。

```mysql
select * from table where username ='admin' and 1=1 --'
```

③闭合单引号及注释多余代码。例如update语句：

```mysql
update Person set username='username',set password='password' where id=1
```

在username处或password处插入" '+(select @@version)+' ",最终执行SQL语句：

```mysql
update person set username='username',set password=''+(select @@version)+''where id=1
```

利用两次单引号闭合才完成SQL注入。

SQL Server 连接符为“+”

Oracle连接符为“||”

而Mysql连接符为空格

④例如Insert语句，对title字段注入：

```mysql
Insert into users(username,password,title) values('username','password','title')
```

对title字段注入，和Update一样。

```mysql
Insert into users(username,password,title) values('username','password',''+(select @@version)+'')
```



### SQL注入分类

- POST注入：注入字段在POST数据中；
- Cookie注入：注入字段在Cookie数据中；
- 延时注入：使用数据库延时特性注入；
- 搜索注入：注入处为搜索的地点；
- base64注入：注入字符串需要经过base64加密；

#### 常见数据库注入

- 查询数据
- 读写文件
- 执行命令

## Bx_目标

---



- 执行数据库语句
- 获取数据库信息
- 利用数据库信息
- 登入后台
- 获取权限，shell

## Cx_方法

---



## Yx_附：术语

- SQL  Structured Query Language 结构化查询语言
- SQL injection SQL注入

## Zx_附：参考文献

[1]《安全测试》

[2]《Web 安全深度剖析》 张炳帅
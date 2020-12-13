---
title: PHP-常量
tags: PHP
abbrlink: 52cc
date: 2019-06-26 13:10:13
---

# 常量
### 1.自定义常量
	当一个数据在脚本执行的周期内不发生变化，可以将这个数据保存在常量中。

> 	<?php  <br>
> 	header('content-type:text/html; charset=utf-8');  <br>
> 	define('NMAE','节课',true);  <br>
> 	echo NAME,'<>';      <br>
> 	echo name,'<>';

==注：常量名默认区分大小写。==
ture：表示不区分大小写。

**定义常量可以用特殊字符，**但是调用的时候必须通过'constant'调用****



<html>
    <p>常量一旦定义，就不能重新定义，可以在定义常量的时候先通过define函数来判断常量是否被定义。
</html>

### 2.预定义常量
    PHP_VERSION:php的版本
        
    PHP_OS:当前运行php的操作系统。
### 3.魔术常量

echo    ——LINE——,'<br>';    输入当前行号
echo    __FILE__,'<br>';    当前文件的完整路径和文件夹
echo    __DIR__,'<br>';     返回文件所在的绝对路径但是没有文件自身的名字。

还可以用const来声明常量。

#### 显示所有的常量

var dump(get_defined-constants(true));
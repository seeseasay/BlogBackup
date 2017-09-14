---
title: Java漫游记(一)
date: 2016 20:09:42
tags: JavaSe
---

通往另外一个世界的Java之路，记录整个学习过程，将之前的知识进行总结


参考书籍与视频

- Java语言程序设计
- java编程思想
- Core Java
- Google
- 各机构....的视频

操作系统：linux和Windows

# Java概述

    学习目标

- 区分API、IDE、JDK
- 编写一个简单的Java程序
- CMD命令
- 在控制台输出结果
- 创建、编译和运行Java程序
- GUI图形输出对话框和显示输出结果
- 关键字

> API：Application Programma Interface 包括为开发Java
程序而预定义的类和接口。

> IDE：集成开发环境，编辑、编译、链接、调试等都集成在一个图形用户界面中

> JDK: 由一套独立程序构成的集合，每个程序都是从命令行调用，用于开发和测试Java程序

1.CMD命令（在linux为终端terminal操作方式不同）

- dir（ls）：列出当前目录下的文件和文件夹
- md：创建目录
- rd：删除目录
- cd：进入指定目录
- cd..退回到上级目录
- cd /：退回到根目录
- del：删除文件
- exit：退出cmd

2.第一个Java程序
> 在控制台显示”Hello World“

````public class HelloWorld{
    //公共的 静态的 无返回值 main方法  数组
    public static void main(String[] agrs){
        System.out.println("HelloWorld");
    }
}
````

编译命令：

`javac HelloWorld.Java`

`Java HelloWorld`

输出结果

> HelloWorld

![Java程序编译过程](http://link)

如果没有语法错误，编译器就会生成一个扩展名为.class的字节码文件。
Java字节码可以在不同的硬件平台和操作系统上运行。执行Java程序就是运行程序的字节码
可以在任何一个装有JVM的平台上运行字节码，解释字节码。

**执行这个文件**

![执行过程](http://link)

3.关键字

> java语言的基本组成
- 关键字
- 标识符
- 注释
- 常量和变量
- 运算符
- 语句
- 函数
- 数组

4.标识符

标识符概念：
> Java语言中，对于变量，常量，函数，语句块也有名字，标识符是用来给类、对象、方法、变量、接口和自定义数据类型命名的。
标识符组成
> 由数字，字母和下划线_，美元符号$和人命币符号￥组成，在Java中是区分大小写的，并且首字母不能是数字。，Java关键字不能作为标识符。,尽量不要用字符$。。

命名约定

- 类和接口名，每个首字母大写，含有大小写。如：HelloWorld。
- 方法名 ,首字母小写，尽量少用下划线，如：myWorld。
- 常量名，基本数据类型的常量名使用全部大写字母，
- 变量名，可大小写混写，首字母小写，字间分隔符用字的首字母大写。

# 基本程序设计

    学习目标

- 编写Java程序完成简单的计算
- 从控制台读取输入
- 变量
- 数据类型
- Java的文档管理、程序设计和命名习惯
- 区分语法错误、运行时错误、逻辑错误和调试错误。

## 编写简单的程序

一个简单的计算圆面积问题，如何编写程序解决？

1）圆面积计算

> 面积 = π × 半径 × 半径

2）写入半径

3）显示面积

````public class Area {

    public static void main(String[] agrs){
        //1.声明数据类型，写入圆的半径
        double r ;
        double S;
        //给半径赋值
        r = 20;
        //2.圆面积的计算
        S = r*r*3.14159;
        //3.显示结果
        System.out.println("面积="+ S);
    }

}
````

加号（+）有两种意义：一种是用作加法，另一种是做字符串的连接。如果两个操作数都是字符串
，字符串连接符就把两个字符连接起来。

### 从控制台读取输入

> 为了使用不同的半径，需要修改源代码，避免这种不方便，可以使用Scanner类从控制台输入

Java中使用System.out来表示输出，而使用System.in来表示输入。。

`Scanner input = new Scanner (System.in);`

![Scanner对象的方法](http://link)


````//导入包
import java.util.Scanner;

public class Area {

    public static void main(String[] agrs){
        Scanner input = new Scanner(System.in);
        System.out.println("请输入数据：");

        //1.声明数据类型，写入圆的半径
        double r  = input.nextDouble();
        //给半径赋值

        //2.圆面积的计算
        double S = r*r*3.14159;
        //3.显示结果

        System.out.print("面积="+ S);
    }

}
````

## 数据类型

> Java基本类型共有八种，基本数据类型可以分为三类，字符型`char`,
布尔类型`boolean`以及数值类型`byte`、`short`、`int`、`long`、
`float`、`double`。

- 四种类型的整数：`byte`、`short`、`int`、`folat`。
- 两种类型的浮点数：`float`、`double`。double类型是float类型的两倍。double又称为双精度，float为单精度。通常使用double类型，因为他更精确。


| 类型        | 存储大小        | 范围  |
| ------------- |:-------------:| -----:|
| byte      | 8位   |最大存储数据255，范围： -128～127 |
| short     | 16位  |最大存储数据2^16,范围：-32768~32767 |
| int       | 32位  |最大存储数据2^32-1,范围：-2147483648～21474836487 |
| long      | 64位  |最大存储数据2^64-1，范围：-2^63~2^63|
| float     | 32位  |数据范围在3.4e-45~1.4e38，直接赋值时必须在数字后加上f或F。     |
| double    | 64位  |数据范围在4.9e-324~1.8e308，赋值时可以加d或D也可以不加 |
|boolean    | |只有true和false|
|char|16位 |存储Unicode码，用单引号赋值|

> Java决定了每种简单类型的大小。这些大小并不随着机器结构的变化而变化。这种大小的不可更改正是Java程序具有很强移植能力的原因之一。。

- 基本类型byte 二进制位数：Byte.SIZE最小值：Byte.MIN_VALUE最大值：Byte.MAX_VALUE
- 基本类型short二进制位数：Short.SIZE最小值：Short.MIN_VALUE最大值：Short.MAX_VALUE
- 基本类型char二进制位数：Character.SIZE最小值：Character.MIN_VALUE-最大值：Character.MAX_VALUE
- 基本类型double 二进制位数：Double.SIZE最小值：Double.MIN_VALUE最大值：Double.MAX_VALUE



## 变量

> 变量用于表示特定数据的类型。使用变量：通过告诉编译器变量的名字及其他可以存储
的数据类型来声明该变量，变量声明，告知编译器根据数据类型为变量分配合适的存储空间，，

语法：`dataByte varibleName`

例如：`int count；`
如果几个变量为同一中类型，允许一起声明它们，
`dataByte varible1，varible2，varible3...`
`int i,j,k;`

变量通常有初始值，可以穿一步完成变量的声明和初始化

`int count = 1；`

char数据类型

`char letter = 'A';`
`char numCahr = '8';`

<font color = red> 提示:</font>在赋值给变量之前，必须声明变量，方法中声明的变量在使用之前必须赋值，
在使用时，使用一步完成变量的声明和赋值，



## 数据类型转换

- 向上转型：将一个小范围数据的变量转换为大范围数据的变量（可自动完成）
- 向下转型：把大范围类型的变量转换为小范围类型的变量（必须要显示转换，强转）

如：int（1.2），double（1/2）
打印并比较：

```System.out.print((double)1/2);
System.out.print(1/2);
```

<font color=red>注意：</font>类型转换不改变被转换的变量

```double d = 4.5
int i = (int)d;

```

```int i = 1;
byte b = i;
```

编译时出错，必须进行强转，然而，只要整数直接是在目标变量允许的范围内，那么整数直接赋值给
short或byte类型变量时，就不需要显示的类型转换。

char类型的准换

> char型的数据可以转成任意一种数值类型，反之也可以。

```char ch = (char)65.23;
System.out.print(ch);
```

```int i =(int)'A';
System.out.print(i);
```



## 运算符





> 数值数据类型的运算符包括标准的算术运算符：加号+、减号-、乘号×、
除号/和求余号%





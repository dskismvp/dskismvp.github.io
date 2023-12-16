### 《JAVA开发基础》



#### 第一章 JAVA概述和环境配置

##### 1.1 JAVA概述

> JAVA起源于爪哇岛，1995年sun公司发布，1996年上市，2009年被Oracle【甲骨文】收购。语言前身oak语言。



##### 1.2 JAVA的三个领域

|        | 版本     | 领域范围              |
| ------ | -------- | --------------------- |
| JAVASE | 标准版本 | 桌面级别开发  CS      |
| JAVAEE | 企业版本 | 企业级别开发  BS      |
| JAVAME | 微小版本 | 手机级别开发   嵌入式 |



##### 1.3 适合做什么

```
1. BS架构系统 ： 百度  商务网站  企业网站
2. CS架构系统 ： 银行网站 超市 游戏 
```



##### 1.4 优势和劣势

优点：

```
1. 跨平台  【操作系统不限制】  
2. 面向对象，简单易学
3. 安全性高  
4. 健壮，鲁棒性
5. 多线程 
6. 高并发
```

缺点：

```
1. 不适合图像研发
2. 运行速度慢
```



##### 1.5 JAVA的版本

```
1.2  里程碑  分领域
1.5  语法改变
1.8  新增内容 
...
1.20 
```

术语：

```
jdk	java开发工具包
jre java运行环境
jvm java虚拟机
api java第三方接口
```

检查安装版本

开始菜单，cmd启动DOS

```sh
java -version
```

![](img\suc.PNG)

##### 1.6 开发环境

```
记事本
Eclipse  MyEclipse
Idea
VS code
....
```



##### 1.7 运行机制【重点】

> JAVA半编译半解释型

编译型：  源程序需要完整编译过程，通过编译才能运行 java、 C

解释型:     源程序不需要完整编译，逐条解释逐条运行  js

![](img\2.PNG)

新建文本文件，HelloWorld.java ,编写第一个JAVA源程序

```java
//这是一个JAVA类
public class HelloWorld {
    //JAVA主方法，程序入口
	public static void main(String[] args){		
        //打印
		System.out.println("欢迎学习JAVA");
	}
}
```

另存为所有文件

编译程序：

1.配置环境变量

```sh
#找到安装目录
C:\Program Files\Java\jdk1.8.0_121\bin

#系统 高级系统设置  环境变量
path 编辑  ;C:\Program Files\Java\jdk1.8.0_121\bin

#确定
```

2.java编译程序

进入磁盘

```
E:
```

切换路径

```
cd 文件夹
cd .. 
```

查看内容

```
dir
```

编译java文件

```sh
javac XX.java
```

生成同名.class文件

3.运行

```
java XX
```



##### 1.8 开发工具Eclipse

###### 1.8.1 创建工作区间

![](img\3.PNG)

###### 1.8.2 创建项目

```
new > project > java project > 输入项目名【避开汉字 数字不开头】 > 完成创建
```



###### 1.8.3 创建包和源代码

```
包：文件夹作用
new > package 
命名规范：
字母 数字 _ $ 构成
数字不能开头
不能关键字
小写
使用.间隔包

根包:  网站后缀.公司名.项目名.功能模块
```

![](img\4.PNG)

创建JAVA类

```
new > class > HelloWorld
```



##### 1.9 注释和快捷键

###### 1.9.1 注释

```java
1. 单行注释   // 
2. 多行注释  /*   */
3. 文档注释  标记： 作者 时间 用途 版本

/**
 * 
 * @author Diana Yu
 * @version 1.0
 * 2023-8-21
 * 第一个JAVA程序
 */
```

###### 1.9.2 快捷键

```
ctrl + /  单行注释快捷键

alt + /   联想键
		  main  alt+/  主方法，程序运行入口
		  syso  alt+/  输出语句

Ctrl + F11  运行程序
```



##### 1.10  第一个JAVA源程序解析

```java
//这是一个JAVA类
public class HelloWorld {
    //JAVA主方法，程序入口
	public static void main(String[] args){		
        //打印
		System.out.println("欢迎学习JAVA");
	}
}
```

类讲解：

```
public 公开的 权限 
class  定义类的关键字，类是JAVA最小组成单元，程序一个个类构成的
HelloWorld 类名

类名命名规范：
字母 数字 _ $ 构成
数字不能开头
不能是关键字
避开汉字，首字母大写，复合单词每个首字母大写 
见名知义

注意： 源程序多个类构成，但是只能一个类添加public，要求该类和文件名完全一致

语句块: 
{  内容的开始

}  内容的结束 
```

主方法的讲解：

```java
public static void main(String[] args){	
}

static 静态的
void 空的 
main 方法名 固定的
    
主方法： 程序的入口，运行的起始点，每个项目至少一个主方法，主方法定义在主类
```

输出语句

```java
System.out.println(); //输出并换行

System.out.print(); //打印输出不换行

注意： 
    1.打印数字直接写入，包括计算
    2.每条语句结束 ; 
	3.字符串 原样输出  " "
```

JAVA中的+

```
1. 计算加法  左右两侧都是数字 
2. 粘贴拼接  左右两侧只要一侧是"" 
```

示例代码：

```java
public class Test01 {
	//程序入口
	public static void main(String[] args) {
		//变量定义
		int a = 50;
		//打印数字
		System.out.println(a);
		System.out.println(20);
		System.out.println(a + 20); //30
		System.out.println(3.1415926);
		
		//字符串 原样输出
		System.out.println("于老师真漂亮");
		System.out.println("  *");
		System.out.println(" ***");
		System.out.println("*****");
		
		//+粘贴
		System.out.println("10" + 20);//1020
		System.out.println(a + "20");//1020
		System.out.println("10" + "20");//1020
		
		//思考,提示 程序从左到右 从上到下
		System.out.println(a + 20 + ""); // "30"
		System.out.println(a + "" + 20); //"1020"
		System.out.println("" + a + 20);//"1020"
		System.out.println(a + 20);//30\
		
		
	} 
}
```



#### 第二章 JAVA基本语法

```
语句块{
		
		变量和常量
		数据类型
		运算符
		表达式
		语句
}
```

##### 2.1 变量和常量

> 存储数值的介质，载体。

###### 1.变量 

> 可变的量，存储可变的值，动态使用，动态改变

定义方式

定义一个变量

```java
数据类型 变量名 [ = 值 ] ;
```

定义多个变量

```
数据类型 变量名1 [ = 值 ] ,变量名2 [ = 值 ] ... ;
```



注意：

```
1. 数据类型指的是变量存储的值的类型： 整型 int  浮点型  double

2. 变量名
字母 数字 _ $ 构成
数字不能开头
不能是关键字
避开汉字，单个单词小写，a  复合单词 驼峰式  xXXX  stuNo 
见名知义

```

示例代码1：

```java
public class TestVar {
	public static void main(String[] args) {
		//定义变量
		int age = 30;		
		//定义变量 学生学号
		int stuNo = 110110;		
		//打印年龄
		System.out.println(stuNo + "的年龄为：" + age);
				
	}
}
```

示例代码2:

```java
public class TestVar2 {
	public static void main(String[] args) {
		// 练习： 定义两个变量 25 40
		// 打印两个变量的和
		//int a = 25;
		// 定义变量先不赋值
		//int b;
		
		//一次性定义两个变量
		int a = 25 , b ;
		// 赋值 =
		b = 40;
		// 修改
		b = 80;
		// 定义和变量
		int sum = a + b;
		System.out.println("变量之和：" + sum);
	}
}
```

练习： 定义一个变量代表年份，赋值为365，打印一年多少天，两年多少天

注意：

1. = 赋值 从右向左
2. 多次赋值取最后一次
3. 变量只能声明一次，多次赋值

```java
int y = 365;
//变量不能重复声明定义
//int y = 366;
//重复修改值
y = 366;
```

###### 2.常量  

> 存储JAVA中不能修改的值，圆周率3.1415926   月份定12月   DOC 

定义语法规则

```java
final 数据类型 常量名 [ = 值 ] ;
```

命名规范

```
字母 数字 _ $ 构成
数字不能开头
不能是关键字
避开汉字，全部大写
见名知义
```

示例代码：

```java
public class TestFinal2 {
	public static void main(String[] args) {
		//半径
		int r = 3;
		//圆周率
		final double PI = 3.1415926;
		
		//面积
		double s = PI * r * r ;
		//周长
		double c = 2 * PI * r;
		//输出
		System.out.println("圆面积为：" + s);
		System.out.println("圆周长为：" + c);
	}
}
```



##### 2.2  关键字

> JAVA中特有的单词，特殊用法

![](img\5.PNG)

注意：三个特殊用法，没在关键字列表

true   真的

false  假的   

null   空的

##### 2.3  空格 逗号 分号

空格： 分隔，增强代码的可读性

逗号： 一次性定义多个变量 , 

分号： ; 语句结束必须分号



#####  2.4 数据类型

> 决定变量的值的类型以及内存空间的大小。

重点知识点【重点】

```
JAVA数据类型

		基本数据类型 
					4种8个
					整数型 4个  byte  short  int  long
					浮点型 2个  float double
					字符型 1个  char
					布尔型 1个  boolean
		引用数据类型 5种
					数组  类  接口 枚举 注解
```

计算机的内存：

二进制   0  1 两个取值

每8个位一组    每个位 bit  比特位    1字节=8bit

1024字节 = 1K

1024k = 1M

1024M = 1G

1024G = 1T

.....

| 符号位      | 数值位 | 数值位 | 数值位 | 数值位 | 数值位 | 数值位 | 数值位 |
| ----------- | ------ | ------ | ------ | ------ | ------ | ------ | ------ |
| 0正的 1负的 | 0      | 0      | 0      | 0      | 0      | 0      | 1      |

```
0000 0000  0
0000 0001  1
0000 0010  2
0000 0011  3
0000 0100  4
0000 0101  5
0000 0110  6
...
```



###### 2.4.1 整型【重点】

> 存储的数值必须是整数

| 数据类型 | 含义   | 内存大小【字节】 | 内存大小【位数】 | 值范围         |
| -------- | ------ | ---------------- | ---------------- | -------------- |
| byte     | 字节型 | 1                | 8                | -128 ~ 127     |
| short    | 短整型 | 2                | 16               | -32768 ~32767  |
| int      | 整型   | 4                | 32               | -2^31 ~ 2^31-1 |
| long     | 长整型 | 8                | 64               | -2^63 ~ 2^63-1 |

注意： JAVA中默认整数数值都是整型，长整型特殊标记加L或l

示例代码：

```java
public class TestType01 {
	public static void main(String[] args) {
		//字节型
		byte b = 127;
		b = -128;
		//b = 128;
		//不能存储小数
		//b = 3.13;
		
		//短整型
		short s = 32767;
		s = -32768;
		
		//整型
		int i = 2147483647;
		i = -2147483648;
		//i = 2147483648;
		
		//长整型
		long l = 2147483648l;
		
		//手机号
		long tel = 13610943167L;
		
		//字符串【了解】
		String name = "Diana";
		
	}
}
```

练习：

```
1. 定义两个整数代表矩形的宽高，计算并打印矩形的周长和面积
2. 定义两个整数型变量，使用第三变量完成两个变量的交换并输出交换后结果【重点】
3. 使用变量和数据类型完成以下内容定义
	学生编号 赋值为 1001
	学生姓名 赋值为 Jack
	学生成绩 赋值为 85
	学生电话 赋值为 17856382465
	学生年龄 赋值为 20
	学生年级 固定常量 2014
	
	打印学生信息
```

###### 2.4.2 浮点型【重点】

> 存储的数值是小数。

| 数据类型 | 含义       | 内存大小【字节】 | 内存大小【位数】 | 值范围 IEEE |
| -------- | ---------- | ---------------- | ---------------- | ----------- |
| float    | 单精度浮点 | 4                | 32               | 大于long    |
| double   | 双精度浮点 | 8                | 64               | 大于float   |

数值型空间大小排序：

byte < short <int <long<float <double

注意：

```
1. 单双精度和小数点后几位没有关系  10  9.9   9.99999999
2. JAVA中所有的小数默认为double类型，因此float类型数值一定添加F或f，double型可以加d或D或不加
```

示例代码：

```java
public class TestFD {
	public static void main(String[] args) {
		//定义单精度浮点
		float f = 3.14F;
		//改值
		f = 3.5f;
		//双精度
		double d = 88.888;
		d = 66.66D;
		
		//思考
		long l = 10;
		d = 20;
		System.out.println(f + d);
	}
}
```

###### 2.4.3 数据类型转换

byte < short <int <long<float <double

```
自动转换 整数变小数
		大类型 =  小类型
强制转换 
		整数之间： 二进制，砍掉位数
		整数小数： 砍掉小数位
		
		小类型 = (小类型)大类型 
```

示例代码：

```java
public class TestConvert {
	public static void main(String[] args) {
		byte b = 20;
		//自动转换
		int i = b;
		//自动转换
		long l = 10;
		//自动转换
		float f = 3 ;
		//自动转换
		double d = f;
		//将整数转化为小数
		System.out.println(f);//3.0
		//强制转换
		float f2 = (float)3.14;
		//强制转换
		//取整
		int a = (int)10.88;
		System.out.println(a);
	}
}
```

练习：

```java
1.定义小数 3.1445926，经过JAVA代码处理，打印这个数的保留的两位结果【不考虑四舍五入】
double f = 9.43456456;
//强转
//f = (int)(f * 100) / 100.0;
System.out.println(d3);		
```



###### 2.4.4 进制【了解】

```
二进制  0 1
十进制  0 ~ 9
八进制  0 ~ 7  以0开头的
十六进制 
	   0~9    以0x开头
	   A-F    
```

示例代码：

```java
public class TestJZ {
	public static void main(String[] args) {
		int a = 071; 
		// 71 = 1*1+ 7*10=71
		// 071 = 1*8^0 + 7*8^1= 57
		
		a = 0xFF;
		// FF = 15*16^0+15*16^1 = 255
		System.out.println(a);
	}
}
```

###### 2.4.5 字符型

> 文字和符号的总称。 不是字符串，字符串是原样出现，字符是符号。 
>
> 字符串  " "
>
> 字符 ' ' : 使用单引号括起来的一个符号【汉字  字母  数字  标点符号 】



定义格式

```java
char 字符变量 = 'A';
```

char无符号，不分正负

| 数据类型 | 含义   | 内存大小【字节】 | 内存大小【位数】 | 值范围  |
| -------- | ------ | ---------------- | ---------------- | ------- |
| char     | 字符型 | 2                | 16               | 0~65535 |

JAVA的编码机制：

```
UTF-8    unicode 全球资源编码  UTF-16 UTF-32 UTF-64，和AscII前128一致的
ASCII    128位 【字母 数字 个别符号】
GBK      汉字编码
GB2312   汉字编码
```

常用编码：

```
A-Z   65-90 
a-z   97-122
0-9   48-57
```

```java
public class TestChar2 {
	public static void main(String[] args) {
		//定义一个字符
		char ch = '于';
		//自动转换
		int i = ch;		
		char ch2 = 99;
		System.out.println(i);
		System.out.println(ch2);
	}
}
```

总结：

```
byte < short(char) < int < long < float < double

char可以和数值型做类型转换，char类型做运算的时候，自动转化为数字，不是拼接
```

```java
public class TestChar3 {
	public static void main(String[] args) {
		System.out.println("2" + 3); //23
		System.out.println('2' + 3);//53
		System.out.println(2 + 3); // 5
		
		System.out.println("a" + 2);//a2
		System.out.println('a' + 2);//99
        
	}
}

```

随机数：

[a,b]随机数公式 

```
(int)((b - a + 1) * Math.random() + a)

(char)((b - a + 1) * Math.random() + a)
```

转义符号：

```
 \ 
 \'
 \\
 \n 换行
 \t 制表位  tab
```

示例代码：

```java
public class TestChar4 {
	public static void main(String[] args) {
		//转义
		char c = '\'';
		c = '\\';
		String path = "C:\\Users\\Administrator\\Desktop\\PPT";
		System.out.println(c);
		
		//打印星星 \n换行
		System.out.println("  *\n ***\n*****");
		//System.out.println(" ***");
		//System.out.println("*****");
		
		//\t制表位
		System.out.println("姓名:\t" + "diana");
		System.out.println("年龄:\t" + 20);
		System.out.println("所在班级:\t" + 2302);
	}
}
```

###### 2.4.6 布尔型

> 逻辑型，真假判断类型，值只有两个： true 真  false 假

定义语法

```java
boolean  变量名 = true/false;  
```

| 数据类型 | 含义   | 内存大小       | 位数 | 值范围   |
| -------- | ------ | -------------- | ---- | -------- |
| boolean  | 布尔型 | 1bit 1个比特位 | 1    | 0 真 1假 |

注意： 只有布尔型和其他数据类型不能类型转换。



> 基本数据类型总结
>
> 4种8个
>
> byte short int long   1 2 4 8
>
> float double  4 8
>
> char  2
>
> boolean 1bit



练习：

```
1. 定义一个三位整数，比如123 ，输出该三位数每个位置上数字之和  6 
     234   输出 9

2. 定义一个变量，存储1-16的随机数

3. 定义一个客户类Customer，使用多种数据类型定义客户信息
   客户编号 【整型】
   客户姓名 【字符串】
   客户性别【字符型】
   客户是否是VIP 【布尔型】
   客户折扣信息 dis 【浮点型】

   打印信息，使用\t制表位


```





##### 2.5 运算符

5种运算符

```
()
算术运算符 
比较运算符【关系运算符】
逻辑运算符【位运算】
条件运算符【三目运算符】
赋值运算符
```

JAVA运算的规则：

```java
1. 变量做运算，结果不能低于int类型

		byte b1 = 1, b2 = 2;	
		byte b3 = (byte)(b1 + b2) ;		
		System.out.println(b3);

2. 变量运算中，结果取出现过的最高数据类型 
    	System.out.println(5.0 * 2);
		System.out.println(5 / 2);
		System.out.println(5.0 / 2);
```



###### 2.5.1 算术运算符 

| 运算符 | 含义       | 注意                                                         |
| ------ | ---------- | ------------------------------------------------------------ |
| +      | 加法 拼接  | 全数字加法，有一侧字符串拼接                                 |
| -      | 减法  负号 | 5 - 2     -8                                                 |
| *      | 乘法       |                                                              |
| /      | 除法       | 两侧整数，向下取整，两侧有一侧小数，获得小数                 |
| %      | 取余数     | 除不尽剩下的   10%3==1  6 %7 == 6  <br />整除： 能除尽，余数为0 <br />奇数 偶数   a % 2 != 0   a % 2 == 0<br />a是b的倍数   a%b结果为0 |
| ++     | 自加  多1  | a++  ++a  等价于 a=a+1                                       |
| --     | 自减  少1  | a-- --a  等价于 a=a-1                                        |



敲7游戏

```
7的倍数，包含7 敲
a % 7 为0
a % 10 为7
a / 10 为7
```

示例代码:

```java
public class TestCompute2 {
	
	public static void main(String[] args) {
		int a = 10;		
		//自加1
		//a = a + 1;
		a ++;
		++ a;
		System.out.println(a);
	}

}
```

重点： ++ -- 前置和后置的区别

```
前置 ++a  --a
后置 a++  a--

执行自加自减时候没有其他运算，二者相同
当执行自加自减时候，还有其他运算

前置： 先执行自加自减 再执行其他运算
后置： 先执行其他运算，再自加自减


```

示例代码：

```java
public class TestCompute2 {
	
	public static void main(String[] args) {
		int a = 10;
		int b ;
		//自加1
		//a = a + 1;
		//a ++;
		//++ a;
		
        //后置
		//b = a ++ ; //b=a  a++
		//前置
		b = ++a; //++a b=a
		System.out.println(a + "," + b);
	}
}
```

练习：

```java
public class TestCompute3 {
	
	public static void main(String[] args) {
		int a = 3;
		
		System.out.println(a++);//3
		System.out.println(a);//4 
		System.out.println(++a);//5
        a = 10;
        a = a ++ + ++a ;
		System.out.println(a); //22
	}
}
```



###### 2.5.2 比较运算符

> 关系运算符，变量的值做比较，运算结果是布尔类型。

| 运算符 | 含义     | 注意     |
| ------ | -------- | -------- |
| >      |          |          |
| <      |          |          |
| >=     | 大于等于 | 不能分开 |
| <=     |          |          |
| ==     | 等于     | a==b     |
| !=     | 不等于   |          |

示例代码：

```java
public class TestCompute4 {
	
	public static void main(String[] args) {
		int a = 1;
		
		//表达式1 a是奇数
		System.out.println(a % 2 != 0);
		
		//表达式2 3的倍数
		System.out.println(a % 3 == 0);
		
		//自加
		System.out.println(a ++ == 1);//true a=2
		System.out.println(a);//2
		
		System.out.println(a >= 5);//false
		System.out.println(++ a <= 3);//true
	}
}
```

###### 2.5.3 逻辑运算符

> 多个表达式，共同作用，同时满足【与】，满足一个【或】，非
>
> 逻辑运算的操作数是布尔类型 

与    同真则真，一假则假

或    一真则真，同假则为

非   真变假，假变真

| 运算符        | 含义                    | 注意                                  |
| ------------- | ----------------------- | ------------------------------------- |
| && 【重点】   | 短路与，同真则真        |                                       |
| &             | 逻辑与 ，同真则真       | 两个操作数是布尔类型 true & false     |
|               | 按位与[同1则1 有0则0]   | 两个操作数不是布尔类型  2 & 3 <br />  |
| \|\| 【重点】 | 短路或                  |                                       |
| \|            | 逻辑或                  |                                       |
|               | 按位或                  | 两个操作数不是布尔类型  2 \| 3 <br /> |
| !   【重点】  | 非                      |                                       |
| ^             | 按位异或【相同0 不同1】 | 2^3 是1                               |
| >>            | 右移                    | 右移n位相当于除以2的n次幂             |
| <<            | 左移                    | 左移n位相当于乘以2的n次幂             |

重点：

```
短路与 &&  逻辑与 &
短路与： 左侧操作数为假，右侧会被短路，右侧不执行
逻辑与： 左右操作数必须执行

短路或 ||  逻辑或 |
短路或： 左侧操作数为真，右侧会被短路，右侧不执行
逻辑或： 左右操作数必须执行
```

示例代码

```java
public class TestCompute6 {
	
	public static void main(String[] args) {
		//System.out.println(true & false);
		//System.out.println(true && true);		
		int a = 1,b = 1;
		System.out.println(a ++ == 1 && -- b == 1);//false		
		int day = 2;
		//day 1-7之间
		System.out.println(day >= 1 && day <= 7);
        //非
        System.out.println(!(5 > 3));
	}
}
```

```java
public class TestCompute7 {	
	public static void main(String[] args) {	
		int a = 1,b = 1;		
		boolean boo = ++ a == 1 & b ++ == 1;
		
		System.out.println(a + "," + b);
		System.out.println(boo);		
	}
}
```

算术 比较 逻辑综合

```java
public class TestCompute7 {	
	public static void main(String[] args) {
		int a = 1,b = 1,c = 1;		
		//boolean boo = ++ a == 1 & b ++ == 1;
		boolean boo = a ++ == 1 && b ++ == 1 || --c == 1;
		System.out.println(a + "," + b + "," + c); // 2 2 1
		System.out.println(boo); // true
		
		boolean boo2 = a ++ == 2 || ++ b == 2 && c ++ == 2;
		
		System.out.println(a + "," + b + "," + c); // 3 2 1
		System.out.println(boo2);
	}
}
```



了解:

```java
public class TestCompute8 {
	
	public static void main(String[] args) {
	
		
		//& 逻辑与
		System.out.println(true & false);
		
		//位运算
		// 0000 0010
		// 0000 0011
		// 0000 0010
		System.out.println(2 & 3);
		
		// 0000 0010
		// 0000 0011
		// 0000 0011
		System.out.println(2 | 3);
		// 0000 0010
		// 0000 0011
		// 0000 0001
		System.out.println(2 ^ 3);
		//次幂
		System.out.println(Math.pow(2, 3));
		
		
		//2 -> 16
		
		//0000 0010
		//左移
		System.out.println(2 << 3);
		//右移
		System.out.println(32 >> 2); // 32 / 4
	}
}
```



###### 2.5.4 条件运算符

> 三目运算符【三个操作数】，按照条件判断来获得结果

语法规则：

? :

```
结果 =  操作数1 ? 操作数2 : 操作数3 ;
```

使用：

```
操作数1的结果，必须布尔类型，
操作数1 真 结果是操作数2
操作数1 假 结果是操作数3

操作数1 是条件判断，结果是布尔型
操作数2 3 最终结果取值
结果数据类型取出现的最高类型
```

示例代码

```java
public class TestCompute10 {
	
	public static void main(String[] args) {
		//三个变量的最大值
		int a = 15 , b = 82 , c = 552;
		
		//打印a和b最大值
		//int max = a > b ? a : b;		
		//max = max > c ? max : c;
		
		int max = (a > b ? a : b ) > c ? (a > b ? a : b ) : c;
		
		System.out.println("max=" + max);	
	}
}

```



###### 2.5.5 赋值运算符

> 从右向左执行，将值赋给变量  a = 10   
>
> 除了自加自减后置以外，赋值运算最后的

| 运算符 | 含义                      | 注意 |
| ------ | ------------------------- | ---- |
| =      |                           |      |
| +=     | a += 10    >   a = a + 10 |      |
| -=     |                           |      |
| *=     |                           |      |
| /=     |                           |      |
| %=     |                           |      |

注意： +=语法格式简化，可以完成内部类型转换。



总结：

```
()

负号 非  ++ --前置

算术  + - * / % ++ --

比较 > < >= <= == !=

逻辑 && || 

条件 ? :

赋值 = += -= ...
```



##### 2.6 控制台接收

> 程序不定死变量数值，动态接收。

```java
//JAVA中类 Scanner 扫描类

//1. 创建Scanner对象
Scanner mi = new Scanner(System.in);

//2. 引入所在包
import java.util.Scanner;   ctrl+shift+o
    
//3.动态接收
    //接收整数
    int age = mi.nextInt();
	//接收小数
	double s = mi.nextDouble();
	//接收字符串
	String name = mi.next();
    

```

示例代码

```java
import java.util.Scanner;
public class TestScanner {
	public static void main(String[] args) {
		//创建打印机
		Scanner mi = new Scanner(System.in);
		
		//接收字符串
		System.out.println("请输入姓名");
		String name = mi.next();
		
		System.out.println("请输入年龄");
		//接收整数
		int age = mi.nextInt();
		
		System.out.println(name + "你好,您" + (age >= 18 ? "成年" : "未成年"));
		
		//接收小数
		//System.out.println("请输入成绩");
		//double s = mi.nextDouble();
		
		mi.close();
	}
}

```



练习：

```
1. 控制台接收一个整数代表年份 ，判断该年份平年 闰年  

	闰年： 年份能被4整除且不能被100整除 或者直接整除400
	
2. 控制台接收三个变量 a b c  三角形三边
   判断能否构成三角形 任意两边之和大于第三边
   
3. 
	定义变量 顾客姓名 String  是否是vip boolean  折扣 double
	
	控制台接收消费金额double
	
	根据顾客的VIP情况打印实际金额
```



##### 2.7 语句

```
顺序语句 : 程序从上往下，从左往右
分支语句 : 程序根据某种条件有选择的执行代码  if-else  switch
循环语句 : 程序根据某个条件反复执行代码  for  while  do-while 

```



###### 2.7.1 分支语句

###### if-else结构

语法1 ：【一条分支】

```java
if(判断条件布尔值){
	//条件为真，执行语句
}
```

语法2 ：【两条分支】

```java
if(判断条件布尔值){
	//条件为真，执行语句
}else{
	//不满足条件执行
}
```

示例代码：

```java
package com.cl.demo;

import java.util.Scanner;

public class TestIf_2 {
	public static void main(String[] args) {		
		//1. 创建Scanner对象
		Scanner mi = new Scanner(System.in);		    
		//2.动态接收
		System.out.println("请输入三个变量:");
		int a = mi.nextInt();
		int b = mi.nextInt();
		int c = mi.nextInt();
		
		//思路1
//		if(a > b && a > c) {
//			System.out.println("最大值:" + a);
//		}
//		if(b > a && b > c) {
//			System.out.println("最大值:" + b);
//		}
//		if(c > a && c > b) {
//			System.out.println("最大值:" + c);
//		}
		
		//思路2
		int max = 0;
		if(a >= b) {
			max = a;
		}else {
			max = b;
		}
		
		if(c > max) {
			max = c;
		}
		
		System.out.println("最大值:" + max);
		
	}
}

```



思考： 控制台接收三个变量，按照从小到大输出三个值  a b c 

```java
package com.cl.demo;

import java.util.Scanner;

public class TestIf_3 {
	public static void main(String[] args) {		
		//1. 创建Scanner对象
		Scanner mi = new Scanner(System.in);		    
		//2.动态接收
		System.out.println("请输入三个变量:");
		int a = mi.nextInt(); //52
		int b = mi.nextInt(); //34
		int c = mi.nextInt();//28
		//思路1
		// a < b < c
		// a < c < b
		// b < a < c
		// b < c < a
		// c < a < b
		// c < b < a
		
		//按照从小到大输出三个值
		//思路2 比较交换思想 【重点】
		if(a > b) {
			int temp = a;
			a = b;
			b = temp;
		}
		if(a > c) {
			int temp = a;
			a = c;
			c = temp;
		}
		if(b > c) {
			int temp = b;
			b = c;
			c = temp;
		}
		System.out.println(a + "<" + b + "<" + c);
		
		
		//思路3 最大值 最小值思想
		int max = (a > b ? a : b ) > c ?  (a > b ? a : b ) : c;		
		int min = (a < b ? a : b ) < c ?  (a < b ? a : b ) : c;
		
		int mid = 0;
		if(a != max && a != min) {
			mid = a;
		}
		if(b != max && b != min) {
			mid = b;
		}
		if(c != max && c != min) {
			mid = c;
		}
		System.out.println(min + "<" + mid + "<" + max);
	}
}

```



语法3 ：【多条分支】

```java
if(判断条件布尔值){
	//条件为真，执行语句
}
else if(判断条件2){
    //条件2为真，执行语句
}
else if(判断条件3){
    //条件3为真，执行语句
}
//...
else{
	//不满足条件执行
}
```

注意：

```
1. 多条分支的多个条件并列关系，条件不能存在包含
2. 多条分支只能n选1执行【走分支1，不会走分支2； 走分支2，肯定不满足分支1】
```

示例代码

```java
package com.cl.demo;

import java.util.Scanner;

public class TestIf_4 {
	public static void main(String[] args) {		
		//1. 创建Scanner对象
		Scanner mi = new Scanner(System.in);		    
		//2.动态接收
		System.out.println("请输入星期几:");
		int day = mi.nextInt(); 
		
		//思路1
		if(day >= 1 &&  day <= 5) {
			System.out.println("好好上课");
		}else if(day == 6) {
			System.out.println("打游戏");
		}else if(day == 7) {
			System.out.println("睡觉休息");
		}else {
			System.out.println("非法日期");
		}		
		//思路2 嵌套思维
		if(day < 1 || day > 7) {
			System.out.println("非法日期");
		}else {
			if(day >= 1 &&  day <= 5) {
				System.out.println("好好上课");
			}else if(day == 6) {
				System.out.println("打游戏");
			}else {
				System.out.println("睡觉休息");
			}
		}

	}
}

```

练习：

```java
1. 控制台接收数字，打印5 6整除情况

25 只能被5整除
36 只能被6整除
30 同时整除
13 都不能

public class TestIf_5 {
	public static void main(String[] args) {		
		//1. 创建Scanner对象
		Scanner mi = new Scanner(System.in);		    
		//2.动态接收
		System.out.println("请输入变量:");
		int a = mi.nextInt(); 
		
		//思路1
		if(a % 5 == 0 && a % 6 != 0) {
			System.out.println("能被5整除");
		}else if(a % 6 == 0 && a % 5 != 0) {
			System.out.println("能被6整除");
		}else if(a % 5 == 0 && a % 6 == 0) {
			System.out.println("同时整除");
		}else {
			System.out.println("都不能整除");
		}
		
		//思路2
		if(a % 5 == 0 && a % 6 == 0) {
			System.out.println("同时整除");
		}else if(a % 5 == 0) {
			System.out.println("能被5整除");
		}else if(a % 6 == 0) {
			System.out.println("能被6整除");
		}else {
			System.out.println("都不能整除");
		}
	}
}

```

练习： 控制台接收年份，月份，打印该年该月份天数

//闰年
boolean boo = year % 4 == 0 && year % 100 != 0 || year % 400 == 0;  

```
1 3 5 7 8 10 12  31天
4 6 9 11 30天
2
	闰年 29
	平年 28
```

```java
package com.cl.demo;

import java.util.Scanner;

public class TestIf_6 {
	public static void main(String[] args) {
		// 1. 创建Scanner对象
		Scanner mi = new Scanner(System.in);
		// 2.动态接收
		System.out.println("请输入年份");
		int y = mi.nextInt();

		System.out.println("请输入月份");
		int m = mi.nextInt();

//		if(m < 1 || m > 12) {
//			System.out.println("非法月份");
//		}else {
//			//合法
//			if(m == 4 || m == 6 || m == 9 || m == 11) {
//				System.out.println("30天");
//			}else if(m == 2) {
//				if( y % 4 == 0 && y % 100 != 0 || y % 400 == 0) {
//					System.out.println("29天");
//				}else {
//					System.out.println("28天");
//				}
//			}else {
//				System.out.println("31天");
//			}
//		}

		boolean boo = false; //不是闰年
		if (y % 4 == 0 && y % 100 != 0 || y % 400 == 0) {
			boo = true;//是闰年
		}

		if (m == 1 || m == 3 || m == 5 || m == 7 || m == 8 || m == 10 || m == 12) {
			System.out.println("31天");
		} else if (m == 4 || m == 6 || m == 9 || m == 11) {
			System.out.println("30天");
		} else if (m == 2 && boo) {
			System.out.println("29天");
		} else if (m == 2 && !boo) {
			System.out.println("28天");
		} else {
			System.out.println("非法");
		}
	}
}
```



###### switch结构

语法

```java
switch(变量/表达式){
	case 值1 : {满足和值1相等; }
    case 值2 : {满足和值2相等; break;}
    case 值3 : {满足和值3相等; break;}
    ....
    default:  {都不满足执行}  
}
```



注意：

```
1. switch() 里只能是变量、表达式不能是条件
数据类型限制： byte short int char enum[jdk5+] String[jdk7+] 

2. case 值不允许重复，case的值类型必须是byte short int char enum[jdk5+] String[jdk7+] 

3. switch变量和case值匹配，匹配上执行哪个case

4. 执行完case，有break跳出switch结束，没有break，继续向下执行

5. default没有任何匹配值
```

示例代码

```java
public class TestSwitch {
	public static void main(String[] args) {
		String light = "green";
		switch (light) {
			case "green": {
				System.out.println("绿灯行");				
			}
			case "red": {
				System.out.println("红灯停");
				break;
			}
			case "yellow": {
				System.out.println("黄灯缓行");
				break;
			}
			default :{System.out.println("灯坏了");}
		}
	}
}
```

练习：

```
控制台接收学生分数【1-100】，输出等级【switch】
90-100 A
80-89 B
70-79 C
60-69 D
60以下 E
```



###### 2.7.2  循环语句

> 程序反复运行的时候，循环语法。

循环分类

```
for
while
do-while
```

构成部分

```
初始值    循环最开始条件设置
循环条件  满足循环执行条件
循环体    反复执行的代码
迭代      循环变更
```



###### for循环

语法

```java
for(初始值 ;  循环条件 ; 迭代){
	循环体;		
}
```

执行顺序：

```
1. 初始值
2. 循环条件
3. 满足条件，执行循环体
4. 迭代
5. 循环条件，满足条件，3
6. 循环不满足，跳出
```

示例代码：

```java
public class TestFor1 {
	public static void main(String[] args) {
		
//		for(int i = 1; i <= 5; i ++) {
//			System.out.println("王某跑第" + i + "圈");
//		}
//		
		//打印1-100
//		for(int i = 1; i <= 100; i ++) {
//			System.out.println(i);
//		}
		//打印1-100内所有的奇数
		
//		for(int i = 1; i <= 100; i += 2) {
//			System.out.println(i);
//		}
		
		for(int i = 1; i <= 100; i ++) {
			if(i % 2 != 0) {
				System.out.println(i);
			}
		}
	}
}
```

###### 求和问题

```java
/**
 * 打印1-100和
 * @author Administrator
 *
 */
public class TestFor2 {
	public static void main(String[] args) {
		//和变量
//		int sum = 0;
//		for (int i = 1 ; i <= 100; i++) {
//			sum += i;
//		}	
//		System.out.println("sum=" + sum);
		
		//1-100偶数和
		
//		int sum = 0;
//		for (int i = 2; i <= 100; i+= 2) {
//			sum += i;
//		}
//		System.out.println(sum);
		
		
		//10! = 1 * 2 * 3 ...  * 10
		int sum = 1;
		
		for (int i = 1; i <= 10; i++) {
			sum *= i;
		}
		System.out.println(sum);
	}
}
```



###### 计数问题

```java
//打印1-100 打印3倍数且个数6  打印个数
public class TestFor4 {
	public static void main(String[] args) {
		int count = 0;
		for (int i = 1; i <= 100; i++) {
			//条件筛选
			if(i % 3 == 0 && i % 10 == 6) {
				//计数变量增加
				count ++;
				System.out.println(i);
			}
		}
		System.out.println(count);		
	}
}

```

练习：

```java
//统计1900-2023年之间打印闰年 ，闰年个数
public class TestFor5 {
	public static void main(String[] args) {
		int count = 0;
		//统计1900-2023年之间打印闰年 ，闰年个数
		for (int i = 1900; i <= 2023; i++) {
			if(i % 4 == 0 && i % 100 != 0 || i % 400 == 0 ) {
				count ++;
				System.out.print(i + "\t");
                //判断是否是4的倍数
				if(count % 4 == 0) {
					System.out.println();
				}
			}
		}
		System.out.println("count=" + count);
	}
}

```

###### 多层循环

> 循环体又是循环。

###### 图形问题



```java
*
**
***

public class TestFor_7 {
	public static void main(String[] args) {
		//行
		for (int i = 1; i <= 4; i++) {
			//列
			for (int j = 1; j <= i; j++) {
				System.out.print("*");
			}
			System.out.println();
		}
	}
}
```

练习：

```java
public class TestFor_8 {
	public static void main(String[] args) {
		//行
		for (int i = 1; i <= 4; i++) {
			//列
			for (int j = 1; j <= 2 * i - 1; j++) {
				System.out.print("*");
			}
			System.out.println();
		}
	}
}
```

金字塔

```java
public class TestFor_9 {
	public static void main(String[] args) {
		//行
		for (int i = 1; i <= 4; i++) {
			//列			
			//空格
			for (int k = 1; k <= 4 - i; k++) {
				System.out.print(" ");
			}
			//星星
			for (int j = 1; j <= 2 * i - 1; j++) {
				System.out.print("*");
			}
			System.out.println();
		}	
	}
}
```

###### 逻辑问题

```java
// 打印1-1000的完数
//完数 ： 数字因子【能被其整除】之和，不包括自己， 因子和=自己
// 6  1+2+3 == 6

// 1. 找每个数字的因子 
// 2. 求和问题

public class TestWan {	
	public static void main(String[] args) {
		//当前数字
		for (int i = 1; i <= 1000; i++) {
			//和
			int sum = 0;
			//找因子
			for (int j = 1; j < i; j++) {
				if(i % j == 0) {
					//求和
					sum += j;
				}
			}
			//判断
			if(sum == i) {
				System.out.println(i);
			}
		}
	}
}
```

【重点】练习： 打印10-100之间的素数【质数】，找因子个数2个  1 本身

```java
package com.cl.demo;

public class TestSuShu {
	
	public static void main(String[] args) {
//		//当前数字
//		for (int i = 10; i <= 100; i++) {
//			//统计个数
//			int count = 0;
//			//找因子
//			for (int j = 1; j <= i; j++) {
//				if(i % j == 0) {
//					//多一个
//					count++;
//				}
//			}
//			//判断
//			if(count == 2) {
//				System.out.println(i);
//			}
//		}
		
		//当前数字
		for (int i = 10; i <= 100; i++) {
			//boolean标记
			boolean f = true;
			//找因子
			for (int j = 2; j < i; j++) {
				if(i % j == 0) {
					//找到因子,修改标记
					f = false;
				}
			}
			//标记没变
			if(f) {
				System.out.println(i);
			}		
		}
	}
}
```

 

###### while循环

语法

```java
初始值;
while(循环条件){
    循环体;
    迭代;
}
```

示例代码

```java
//使用while循环求1-100的和
public class TestWhile1 {
	public static void main(String[] args) {
		//初始值
		int i = 1,sum = 0;
		//判断循环条件
		while(i <= 100) {
			//循环体
			sum += i ;
			//迭代
			i ++;
		}
		System.out.println("sum=" + sum);
	}	
}
```

```java
//使用while打印4个随机小写字母 
public class TestWhile2 {
	public static void main(String[] args) {
		int i = 0;
		while(i < 4) {
			char c = (char)((122 - 97 + 1) * Math.random() + 97);
			System.out.print(c);
			i ++;
		}
	}	
}

```

```java
//使用while打印4个随机字母 【不分大小写】 65-90  97 - 122
public class TestWhile3 {
	public static void main(String[] args) {
		int i = 0;
		while(i < 4) {
			char c = (char)((122 - 65 + 1) * Math.random() + 65);
			if(c >= 91 && c <= 96) {
				continue;
			}else {
				System.out.print(c);
				i ++;
			}
		}
	}	
}
```

###### while死循环

```java
for(;;){
	
}

while(true){
	
}
```

注意： 死循环，一定跳出条件

```java
public class TestWhile4 {
	public static void main(String[] args) {
		int count = 0;
		while(true) {
			char c = (char)((122 - 65 + 1) * Math.random() + 65);
			if(c >= 97 && c <= 122 || c >= 65 && c <= 90) {
				count ++;
				System.out.print(c);
				if(count == 4) {
					break;
				}
			}		
		}
	}	
}
```

###### 循环条件未知，外部条件决定

```java
public class TestWhile5 {
	public static void main(String[] args) {
		System.out.println("--------欢迎进入CS GO游戏世界-----------");
		System.out.println("是否确认开始 Y");
		Scanner sc = new Scanner(System.in);
		//初始值
		String oo = sc.next();
		//循环条件
		while(oo.equals("Y") || oo.equals("y")) {
			//循环体
			System.out.println("游戏进行中.....");			
			System.out.println("bulalalalalal ");			
			System.out.println("Game over");
			
			//迭代
			System.out.println("是否继续下一轮 Y 继续 / 按其他键退出");
			oo = sc.next();
		}
		System.out.println("再见~~~~~");
	}	
}

```

练习：

```java
//控制台接收学生的成绩，按0退出，打印以上成绩中最高分max，总分sum 和平均分avg
public class TestWhile6 {
	public static void main(String[] args) {
		
		System.out.println("请输入分数");
		Scanner sc = new Scanner(System.in);
		//初始值
		int s = sc.nextInt();
		//循环条件
		int sum = 0,max = 0;
		double count = 0;
		while(s != 0) {
			//循环体
			sum += s;
			count ++;
			//最大值
			if(max < s) {
				max = s;
			}
            //迭代
			System.out.println("请输入分数");
			s = sc.nextInt();
		}
		System.out.println(sum);
		System.out.println(sum / count);
		System.out.println(max);
	}	
}

```

###### 菜单程序

```java
package com.cl.demo;

import java.util.Scanner;

public class TestWhile7 {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		System.out.println("欢迎使用长亮科技ATM");
		String name = "于女士";
		double balance = 2000;
		while(true) {
			System.out.println("1-存钱");
			System.out.println("2-取钱");
			System.out.println("3-查询余额");
			System.out.println("4-转账");
			System.out.println("5-修改密码");
			System.out.println("6-退出");
			System.out.println("请输入选项");
			int i = sc.nextInt();
			if(i == 1) {
				System.out.println("存入金额");
				int money = sc.nextInt();
				if(money >= 100 && money % 100 == 0) {
					balance += money;
					System.out.println("存钱成功");
				}else {
					System.out.println("金额有误");
				}
			}else if(i == 2) {
				System.out.println("取款金额");
				int money = sc.nextInt();
				if(balance >= money) {
					balance -= money;
					System.out.println("取款成功");
				}else {
					System.out.println("余额不足");
				}
			}else if(i == 3) {
				System.out.println(name + "您好，卡内余额:" + balance);
			}else if(i == 4) {
				
			}else if(i == 5) {
				
			}else if(i == 6) {
				System.out.println("谢谢使用");
				break;
			}else {
				System.out.println("非法操作");
			}
		}	
	}
}
```

###### do-while循环

语法

```java
初始值;
do{
	循环体;
	迭代;
}while(循环条件);
```

注意：

```
1. do{} 定义的变量，while条件不能使用
2. do-while循环比其他两种循环多执行一次，不管是否满足条件
```

示例代码

```java
public class TestDo {
	public static void main(String[] args) {
		//1-10的累乘 
		
		int i = 1,mul = 1;
		do {
			mul *= i;
			i ++;
		}while(i <= 10);
		
		System.out.println(mul);
	}
}
```



练习：

```java
a
bb
ccc
dddd
eeeee
public class TestDemo {
	public static void main(String[] args) {
		// 'a' + 1
		for (int i = 1; i <= 5; i++) {
			for (int j = 1; j <= i; j++) {
				System.out.print((char)('a' - 1 + i));
			}
			System.out.println();
		}		
	}
}
控制台接收数字 猜数游戏
系统 50-100随机数字 85

猜大 提示大了 90  50-89
猜小 提示小了 60  61-100

直到猜中为止
    
public class TestDemo2 {
	public static void main(String[] args) {
		int start = 50, end = 100;
		Scanner s = new Scanner(System.in);
		System.out.println("输入数字:[" + start + "~" + end + "]");
		int d = s.nextInt();
		//目标
		int f = (int) ((50 * Math.random()) + 50);//85
		int count = 0;
		while (true) {
			count ++;
			if(f == d) {
				System.out.println("猜中");
				break;
			}else if(d < f) {
				//猜小了 60 
				System.out.println("猜小了");
				start = d + 1;
			}else {
				System.out.println("猜大了");
				end = d - 1;
			}
			System.out.println("输入数字:[" + start + "~" + end + "]");
			d = s.nextInt();
		}
		System.out.println("您用了" + count + "次猜中");
	}
}
    
    
```

###### 总结三种循环

```
for循环语法清晰，简单明了，如果循环的次数固定的，首选for。  执行次数 0次或n次

while 循环次数无法固定，先判断条件，执行  ， 执行次数 0次或n次

do-while 循环次数无法固定,先执行后判断 ，执行次数 1次或n次
```



###### 2.7.3 循环跳出

|                 | 含义                         | 注意事项             |
| --------------- | ---------------------------- | -------------------- |
| continue        | 略过本次循环，执行下一次循环 | 整个循环没有结束     |
| break           | 跳出循环【当前一层】         | 只能跳出一层         |
| break 标签 ;    | 跳出任意一层循环             | 跳出指定标签对应循环 |
| return          | 跳出方法                     | 方法外侧             |
| System.exit(0); | 退出虚拟机                   | 程序终止             |

示例代码

```java
public class TestContinue {
	public static void main(String[] args) {
		for (int i = 1; i <= 10; i++) {
			if(i == 5) {
				//continue;
				break;
			}
				
			System.out.println(i);			
		}
		//....
	}
}
public class TestBreak {
	public static void main(String[] args) {
		p:
		for (int i = 1; i <= 3; i++) {
			for (int j = 1; j <= 3; j++) {
				if(i == 2) {
					//break p;					
					return;
				}
				System.out.println(i + "," + j);
			}
		}
		System.out.println("跳出来了");
	}
}
```

练习：使用java实现， a*b=2048,打印a+b的和最小的a，b变量值 32 64

```java
public class Test2048 {
	public static void main(String[] args) {
		int a = 0, b = 0;
		ok:
		for (a = 1; a <= 2048; a++) {
			for (b = 1; b <= 2048; b++) {
				if(a * b == 2048 && a > b) {
					break ok;
				}
			}
		}
		System.out.println(a + "," + b);
	}
}
```



##### 2.8 数组

> 数组是JAVA的引用数据类型【复杂类型】。
>
> 数组是一组相同数据类型的数据存储。



###### 2.8.1 数组的优势

```
1. 数组的元素相同的数据类型，方便管理
2. 数组元素在内存中连续的存储空间
3. 有下标 ，从0开始
```



###### 2.8.2 数组的特点

```
1. 数组的元素存储在"堆"中【基本数据类型存栈里】
2. 数组元素内存连续的 ， 【变量不连续的】
3. 数组有下标【0开始】
4. 数组的元素默认值【变量没有】
5. 数组的引用存储的是堆元素首地址 【变量直接存值】
```

###### 2.8.3 内存分配

```java
public class TestArray {
	public static void main(String[] args) {
		int a = 10 , b = 20;
		System.out.println(a);
		
		int [] c = {12,45,33,89,56};
        //数组的地址
        System.out.println(c);
        //数组地址找第一个元素
		System.out.println(c[0]);
	}
}
```

![]()![6](img\6.PNG)

###### 2.8.4 数组基本使用

```
1. 声明数组
2. 创建数组
3. 赋值使用
```

###### 1.声明数组

```java
数据类型 [] 数组名 ; //推荐

数据类型 数组名[] ;
```

注意：

1. 数组的数据类型不局限于基本类型
2. 数组名命名【小写 驼峰】 



###### 2.创建数组

[开辟内存:重点]

```java
//1.写法1
数组名 = new 数据类型[大小]; 
//声明创建的数组类型一致
//[]必须给大小

//2.写法2
数据类型[] 数组名 = {元素1,元素2...}; 
//声明创建必须连写
//创建数组同时赋值 

//3.写法3
数组名 = new 数据类型[]{元素1,元素2...}; 
//声明创建分开
//创建数组同时赋值 
//[] 不能写
```

示例代码

```java
public class TestArray2 {
	public static void main(String[] args) {
		//声明
		int [] a;		
		//double d [];	
		//char [] c;		
		//String [] s;		
		//Student[] stu;
		//创建
		a = new int[4];
		//打印地址
		System.out.println(a);
		//元素的值【循环输出】
		System.out.println(a[0]);
		System.out.println(a[1]);
		System.out.println(a[2]);
		System.out.println(a[3]);
	}
}
class Student{	
}
```

练习：

```java
public class TestArray3 {
	public static void main(String[] args) {
		int [] a = new int[5];
		System.out.println(a);
		
		
		for (int i = 0; i < 5; i++) {
			System.out.println(a[i]);
		}
	}
}
```

![](img\7.PNG)

###### 3.赋值和输出

```java

1. new 在堆中开辟新内存
2. 数组元素在堆开辟内存有默认值
   整型 默认值 0
   浮点 默认值 0.0
   字符型 默认值 \u0000 
   布尔型 默认值 false
   引用型 默认值 null
3.数组的大小

数组名.length
数组下标取值范围： [0,a.length-1]

4.
数组元素获取
a[下标]
//赋值
a[下标] = 值;

```

练习：

```java
package com.cl.demo;
/**
 * 创建一个数组
 * 存储6个随机
 *  大写字符 65-90
 * @author Administrator
 *
 */
public class TestArray4 {
	public static void main(String[] args) {
		char[] c = new char[6];
		
		for (int i = 0; i < c.length; i++) {
			//赋值
			c[i] = (char)((90 - 65 + 1) * Math.random() + 65);
		}
		
		//打印输出
		for (int i = 0; i < c.length; i++) {
			System.out.print(c[i]);
		}
	}
}
```

其他两种创建

```java
public class TestArray5 {
	public static void main(String[] args) {
		//定义一个数组，A-E
		char [] c = {'A','B','C','D','E'}; ;
		
		//不能分开
		//c = {'A','B','C','D','E'};
		
		int [] a = {2,0,4,8};
		
		//自动转换
		double [] d = {1,2,3,4 };
		
		for (int i = 0; i < d.length; i++) {
			System.out.println(d[i]);
		}
	}
}
public class TestArray6 {
	public static void main(String[] args) {
		int[] a ;
		
		//注意：[]不写
		a = new int[] {1,2,3,4};
	}
}
```

练习：

```java
//1.控制台接收五个学生的成绩，求出五个学生总分  平均值  打印五个分数
public class TestArray7 {
	public static void main(String[] args) {
		
		double[] a = new double[5];
		Scanner sc = new Scanner(System.in);
		System.out.println("请输入五个成绩");
		double sum = 0;
		for (int i = 0; i < a.length; i++) {
			a[i] = sc.nextInt();
			sum += a[i];
		}
		double avg = sum / a.length;
		System.out.println(sum);
		System.out.println(avg);
	}
}
//2.数组元素是 12 45 56 88 93 五个成绩，打印及格学生个数 【60+】

public class TestArray8 {
	public static void main(String[] args) {
		//int[] a = {12,45,56,88,93};
		int[] a;
		a = new int[]{12,45,56,88,93};
		
		int count = 0;
		for (int i = 0; i < a.length; i++) {
			if(a[i] >= 60) {
				count ++;
			}
		}
		System.out.println(count);
	}
}
```



###### 2.8.5  数组应用

```
1. 打印数组,数组遍历
2. 动态赋值
3. 求和 平均值
4. 最大值 最小值
5. 重复【去重，找重复】
6. 计数，个数
7. 排序【重点】 冒泡 选择 插入 希尔 堆 归并 
8. 查找【重点】 线性查找 二分查找
9. 数组大小，数组传值
10.数组复制合并

```

###### 数组遍历

增强for循环的语法，jdk5+

```java
for(数据类型 迭代变量 : 数组名){
	//打印迭代变量
}
```

示例代码

```java
public class TestApplication1 {
	public static void main(String[] args) {
		int[] a = {12,56,33,89,68,25,12};
		
		//1 通过下标
		for (int i = 0; i < a.length; i++) {
			System.out.print(a[i] + "\t");
		}
		System.out.println();
		System.out.println("--------------------------------------------------------");
		System.out.println();
		//2 增强for循环 foreach ，专用于数组【集合】遍历 jdk5+
		//for(数据类型 迭代变量 : 数组名){    	
			//打印迭代变量	
	    //}
		for(int i : a) {
			System.out.print(i + "\t");
		}
		System.out.println();
		System.out.println("--------------------------------------------------------");
		System.out.println();
		//3 以字符串形式输出 ctrl+shift+o
		System.out.println(Arrays.toString(a));
		System.out.println();
		System.out.println("--------------------------------------------------------");
		System.out.println();
		//4 jdk8+ Stream 【推荐,现在了解】
		//Arrays.stream(a).distinct().sorted().forEach(System.out::println);
	}
}

```

###### 动态赋值

> 数组元素的值后续动态给的
>
> 随机数生成赋值给数组
>
> 控制台接收赋值给数组
>
> 

示例代码

```java
		//控制台接收
		double[] a = new double[5];
		Scanner sc = new Scanner(System.in);
		System.out.println("请输入五个成绩");
		double sum = 0;
		for (int i = 0; i < a.length; i++) {
			a[i] = sc.nextInt();
			sum += a[i];
		}
		//随机
		char[] c = new char[6];
		
		for (int i = 0; i < c.length; i++) {
			//赋值
			c[i] = (char)((90 - 65 + 1) * Math.random() + 65);
		}
```

###### 求和，平均值

```java
public class TestArray7 {
	public static void main(String[] args) {
		
		double[] a = new double[5];
		Scanner sc = new Scanner(System.in);
		System.out.println("请输入五个成绩");
		double sum = 0;
		for (int i = 0; i < a.length; i++) {
			a[i] = sc.nextInt();
			sum += a[i];
		}
		double avg = sum / a.length;
		System.out.println(sum);
		System.out.println(avg);
	}
}
```

###### 最值

```java
//打印最高分  第几位同学
//打印最低分  第几位同学
public class TestApplication2 {
	public static void main(String[] args) {
		
		double[] a = new double[5];
		Scanner sc = new Scanner(System.in);
		System.out.println("请输入五个成绩");
		double sum = 0;
		double max = 0,min = Integer.MAX_VALUE;
		int index1 = 0,index2 = 0;
		for (int i = 0; i < a.length; i++) {
			a[i] = sc.nextInt();
			sum += a[i];
			if(max < a[i]) {
				max = a[i];
				index1 = i;
			}
			if(min > a[i]) {
				min = a[i];
				index2 = i;
			}
		}
		double avg = sum / a.length;
		System.out.println("总分" + sum);
		System.out.println("平均分" + avg);
		System.out.println("最高分:" + max + "是第" + (index1+ 1 )+ "个同学");
		System.out.println("最低分:" +min + "是第" + (index2 + 1)+ "个同学");
	}
}
```

练习：

```
1. 一直数组元素为a = {12,56,78,35,89,30,66} ,将数组元素逆置，输出

元素本质改变，不是倒着输出 
打印a = {66,30,89,35,78,56,12}

提示： 首尾交换

2.控制台接收五个评委分数，有一个评委0分，选手直接淘汰
  最终成绩 ： 去掉最高最低分后的平均分
  
3. 彩票【选做】
   生成1个1-16随机蓝色球
   生成6个1-33随机红色球【去重】
```

###### 数组元素重复

```java
//1. 去掉重复
public class TestArray01 {
	public static void main(String[] args) {
		System.out.println("......欢迎来到彩票站....");
		int blue = (int)(16 * Math.random() + 1);
		int[] reds = new int[6];
		
		for (int i = 0; i < reds.length; i++) {
			//i当前生成
			reds[i] = (int)(33 * Math.random() + 1);
			//找重复元素
			for (int j = 0; j <= i - 1; j++) {
				if(reds[i] == reds[j]) {
					//去掉重复
					i --;
					//退出寻找
					break;
				}
			}
		}
		System.out.println(blue);
		System.out.println(Arrays.toString(reds));
	}
}
//2. 获取重复
// int[] a = {12,56,12,88,50,6,36}组中出现次数最多的元素以及次数【同样第一次出现】

//循环遍历比较
//元素个数
//个数最大值
public class TestArray2 {
	public static void main(String[] args) {
		int[] a = {12,12,12,50,12,88,50,50,2,6,36,50};
		int max = 0 ,index = -1;
		for (int i = 0; i < a.length; i++) {
			int count = 1;
			for (int j = i + 1; j < a.length; j++) {
				if(a[i] == a[j]) {
					count ++;
				}
			}
			if(max < count) {
				max = count;
				index = i;
			}
			
		}
		System.out.println(a[index] + "," + max);
	}
}
//3 元素去除重复【重点】
// {12,56,12,88,50,6,36} -> {12,56,88,50,6,36}

//java数组不能改变大小，这个两个数组

//数组转成集合 List/Set集合去重
//Stream
```



###### 计数问题

```java
// {12,56,0,88,50,0,36} ; 去除数组中为0的元素

// 1 统计0个数
// 2 新建数组 个数去除0
// 3 遍历数组，存入不为0

public class TestArray4 {
	public static void main(String[] args) {
		// {12,56,0,88,50,0,36} ; 去除数组中为0的元素
		int [] a = {12,56,0,88,50,0,36} ; 
		// 1 统计0个数
		int count = 0;
		for (int i = 0; i < a.length; i++) {
			if(a[i] == 0) {
				count ++;
			}
		}
		// 2 新建数组 个数去除0
		int [] b = new int[a.length - count];
		// 3 遍历数组，存入不为0
		int index = 0;
		for (int i = 0; i < a.length; i++) {
			if(a[i] != 0) {
				b[index++] = a[i];
			}		
		}
		System.out.println(Arrays.toString(b));
	}
}

```



###### 排序

> 经典算法，将数组的元素变成从小到大【升序】，从大到小排列【降序】

```
常用排序算法：
冒泡排序
选择排序
快速排序
插入排序
希尔排序
堆排序
归并排序
桶排序
```

冒泡排序：

> 【下沉法】将一组数据数据挨着的两两比较，将大的下沉，小的上浮完成交换，直到最大的沉到最下面，完成一次冒泡，后续将其余的数字按照规则依次进行...

N个数，最多冒 N-1 泡



排序过程：

![](img\8.PNG)

分析：

```
1 比较  3次
2 比较  2次
3 比较  1次
i 比较  a.length - i
```

代码：

```java
//冒泡的次数
for(int i = 1; i < a.length ; i ++){
	//比较和交换
    for(int j = 0; j < a.length - i ; j ++){
        if(a[j] > a[j + 1]){
            int temp = a[j];
            a[j] = a[j + 1];
            a[j + 1] = temp;
        }
    }
}
```



选择排序

> 将数组每个位置上的数据与其他的位置比较，如果其他位置比该位置元素小，交换，每次确定一个位置，完成一次交换排序....



排序过程

![](img\9.PNG)



代码实现

```java
public class TestXuan {
	public static void main(String[] args) {
		int [] a = {12,45,33,89,47,83,66};
		//次数
		for(int i = 0; i < a.length ; i ++){
			//比较和交换
		    for(int j = i + 1; j < a.length ; j ++){
		        if(a[i] > a[j]){
		            int temp = a[i];
		            a[i] = a[j];
		            a[j] = temp;
		        }
		    }
		}
		System.out.println(Arrays.toString(a));
	}
}
```

API排序：

```java
Arrays.sort(数组);
```



###### 查找

> 从数组中查询某元素，查找。

```
常用查找算法：

线性查找法

折半查找法【二分查询】
```



线性查找法

> 将目标元素与数组中每个元素依次比较，当全部查询后没有，真的没有，发现匹配，有该元素。

代码实现

```java
public class TestZhao {
	public static void main(String[] args) {
		int [] a = {12,45,33,89,47,83,66};			
		Scanner sc = new Scanner(System.in);
		System.out.println("请输入目标元素");
		int target = sc.nextInt();
		
		boolean boo = true;
		for (int i = 0; i < a.length; i++) {
			if(target == a[i]) {
				System.out.println("包含");
				boo = false;
			}
		}
		if(boo) {
			System.out.println("不包含");
		}		
	}
}

```



二分查找法

> 前提条件： 先排序，每次获取一组数据中间位置元素和目标比较
>
> 相同 ： 找到该元素
>
> 大了 ： 需要缩小范围，中间位置后半部分，折中....
>
> 小了 ：..... 



![](img\10.PNG)



代码实现

```java
public class TestZhao2 {
	public static void main(String[] args) {
		int [] a = {12,45,33,89,47,83,66};			
		Scanner sc = new Scanner(System.in);
		//先排序
		Arrays.sort(a);
		System.out.println("请输入目标元素");
		int target = sc.nextInt();
		int s = 0, e = a.length - 1;
		boolean flag = true;
		while(s <= e) {
			int m = (s + e) / 2;
			if(a[m] == target) {
				flag = false;
				System.out.println("包含");
				break;
			}else if(a[m] > target) {
				e = m - 1;
			}else {
				s = m + 1;
			}
		}
		if(flag) {
			System.out.println("没有该元素");
		}
	}
}
```

API的查找

```java
public class TestZhao3 {
	public static void main(String[] args) {
		int [] a = {12,45,33,89,47,83,66};			
		Scanner sc = new Scanner(System.in);
		//先排序
		Arrays.sort(a);
		System.out.println("请输入目标元素");
		int target = sc.nextInt();
		//二分查询方法
		int index = Arrays.binarySearch(a, target);
		if(index > 0) {
			System.out.println("包含");
		}else {
			System.out.println("不包含");
		}
	}
}
```



###### 数组大小

> 数组的大小不能改变，定义后，定长的。

```java
public class TestArray1 {
	public static void main(String[] args) {
		int [] a = {1,2,3,4};
		System.out.println(Arrays.toString(a));
		System.out.println(a);
		
		a = new int[]{1,2,3,4,5};
		System.out.println(Arrays.toString(a));
		System.out.println(a);
		
	}
}

```

![](img\11.PNG)

###### 数组赋值

```java
int [] a = {1,2,3,4};
int [] b = a;
b[1] = 88;

System.out.println(Arrays.toString(a)); // 1 88 3 4
System.out.println(Arrays.toString(b)); // 1 88 3 4
```

![](img\12.PNG)

> 总结： 数组之间赋值的地址，不是数值。



###### 数组复制

> 数组元素的拷贝。

```java
public class TestArray2 {
	public static void main(String[] args) {
		int [] a = {12,56,34,88};
		int [] b = {34,78,46,99,7};

		//将a和b数组合并到c数组中

		//数组思想
		//重复个数 count
		//创建数组a.length + b.length -count
		int[] c = new int[a.length + b.length];
		
//		for (int i = 0; i < a.length; i++) {
//			c[i] = a[i];
//		}
//		
//		for (int i = 0; i < b.length; i++) {
//			 c[a.length + i] = b[i];
//		}
		
		//方法调用完成
		// a 源数组  0 从什么位置  c 目标数组  0 目标什么位置  a.length 复制的长度
		System.arraycopy(a, 0, c, 0, a.length);
		System.arraycopy(b, 0, c, a.length, b.length);
		
		//集合[了解] TreeSet 自动去重且排序  
		TreeSet<Integer> t = new TreeSet<Integer>();
		for (int i = 0; i < a.length; i++) {
			t.add(a[i]);
		}
		for (int i = 0; i < b.length; i++) {
			t.add(b[i]);
		}
		
		System.out.println(t);
	}
}

```

> 总结： 数组复制System.arraycopy(源数组, 起始下标, 目标数组, 起始下标, 复制长度);



###### 2.8.6  二维数组

> 数组的元素是一个个一维数组。



声明语法

```
数据类型 [][] 数组名 ;
数据类型 数组名 [][] ;
数据类型 []数组名[] ;
```

创建语法

```java
数据类型 [][] 数组名 = new 数据类型[必须给][];

数据类型 [][] 数组名 = {{1,3},{4},{1,4,5,6},{3,4,5}};

第一个[] 二维数组长度
第二个[] 每个一维数组的元素个数
```

![](img\13.PNG)

二维数组的遍历

```java
public class TestArray4 {
	public static void main(String[] args) {
		int a[][] = {{1,3,5},{1,4,9},{3,4,5}};
		for (int i = 0; i < a.length; i++) {
			for (int j = 0; j < a[i].length; j++) {
				System.out.print(a[i][j] + "\t");
			}
			System.out.println();
		}
	}
}
```

练习：

```java
//定义一个3*3矩阵，求两条对角线元素之和
public class TestArray5 {
	public static void main(String[] args) {
		int a[][] = {{1,2,3},{4,5,6},{7,8,9}};
		int sum = 0;
		for (int i = 0; i < a.length; i++) {
			for (int j = 0; j < a[i].length; j++) {
				System.out.print(a[i][j] + "\t");
				if(i == j || i + j == a.length - 1)
					sum += a[i][j];
			}
			System.out.println();
		}
		
		System.out.println("sum=" + sum);
	}
}
```

###### 2.8.7 三维数组

```java
int[][][] a;

a 地址
a[0] = new int[3][];
a[0][0] = new int[4];
a[0][0][0] = 10;
```



#### 第三章 JAVA面向对象基础

> 面向对象语言：java，c#,  c++, python语言
>
> ​						   按事物各个方向分类，按照类别处理问题
>
> 面向过程语言：C语言
>
> ​							按事物的发展过程依次完成代码



需求：朱鑫宇超市买辣条  超市系统      

面向过程： 登录 >  购买 > 结算  > 打折 > 退出

面向对象： 超市系统后台  顾客类   商品类 



#### 3.1 面向对象语言优势

```
对同一套系统有不同的设计
最大的优点是"重用代码" 【避免代码冗余】
利于系统建模
更接近于真实世界
```



#### 3.2 面向对象核心词

```
OOA  面向对象分析  object oriented analysis
OOD  面向对象设计  object oriented design
OOP  面向对象编程  object oriented programming
```

#### 3.3 类和对象

```
类 ： 一类事物统称，对象的蓝图，抽象概念

对象： 实际存在的个体，具体概念

文具盒  文具
西瓜    水果
草     植物
芹菜   蔬菜
元昊   学生

类是同类型对象的抽象说法，对象是类的具体一个个例
类不占用内存，对象开辟内存
```

#### 3.4 类和对象的构成【重点】

```
属性  一类事物【某对象】的特征，特点，属性信息 【数据体现】 学生 ： 学号 姓名 性别 年龄 班级

方法  一类事物【某对象】的行为，动作，能力 【动作体现】 学生： 学习 休息 吃饭  睡觉 
```

嫌疑犯

具体是谁： 对象

人物画像： 类

```
属性： 女的  170  粉色衣服 黑色  不带眼镜 .....
方法： 喝水 行走/跑  擅长射击  
```



#### 3.5 类的声明

```java
//和文件名相同的类，public 公开类，主类
public class 类名 {
	
}
//同一个包可以访问
class 类名{
    
}
```

> 类名规范：首字母大写，数字 _ $ 字母 ，数字不能开头，不能关键字



#### 3.6  属性的声明

```java
控制权限  数据类型  属性名 [=初始值] ;
```

控制权限  public 

数据类型 ： 基本 + 引用

属性名 ： 同变量 【小写或驼峰】

初始值： 可给，可不给，不给默认的【int  0   double 0.0  String  null  数组 null  ....】

```java
public class Student {
	
	//学号
	public int sNo;
	//姓名
	public String name;
	//班级
	public int sClass;
	//三门分数
	public double[] score;
	//学生的宠物
	public Animal a;
}

```

思考：

```
无序数组，先去掉重复，按照出现次数从高到低排序
int[] a = {12,56,12,80,12,67,56};
a = {12,56,80,67}
```



#### 3.7  方法的声明定义

语法【重点】

```java
控制权限 [修饰符] 返回类型 方法名(形参类型 形参变量...){
	方法体;
	[return xx;]
}
```

```java
public static void main(String[] args) {
		
}
```

讲解：

```
控制权限 ： 
		public 公开
		缺省   同包友好
		private 私有的 
		protected 保护的
		
修饰符 ： 可有可无，当加了static ，可以被main直接调用

返回类型：
		空返回，方法执行完，不要返回任何结果  void
        有返回，声明返回类型 int、double ，String，数组，类 ....
        一旦设定返回类型，方法最后必须有return ，只能返回一个值，必须对应匹配类型
        
方法名 ：  小写、驼峰
参数：
		有参数
			形参  形式变量，方法声明定义的时候
			实参  实际数值，方法调用的时候
			(形参类型 形参变量名, 形参类型 形参变量名2...) 每个变量都必须指定类型
			实参将值赋给形参变量（=赋值关系）
			个数，类型匹配...
		无参数
```

```java
package com.cl.oop;
/**
 * 
 * @author Diana Yu
 * @version 1.0
 *     学生类
 * 2023-9-5 
 *
 */
class Animal{
    
}
public class Student {
	
	//学号
	public int sNo;
	//姓名
	public static String name;
	//班级
	public int sClass;
	//三门分数
	public static double[] score ;
	//学生的宠物
	public Animal a;
	
	
	/**
	 * 学生吃饭： 无参数 无返回
	 */
	public static void eat() {
		System.out.println(name + "吃午饭");
	}
	
	
	/**
	 * 学生睡觉 ： 返回学生睡眠时间
	 * @param args
	 */
	public static int sleep() {
		System.out.println("学生要注意睡眠....");
		return 8;
	}
	
	/**
	 * 学生总分： 返回该学生的三门成绩总分
	 * @param args
	 */
	public static double getSum() {
		double sum = 0;
		for (int i = 0; i < score.length; i++) {
			sum += score[i];
		}
		return sum;
	}
	
	/**
	 * 方法：根据传入的星期判断需要做什么  有参数有返回
	 *  day形参
	 */
	public static String thing(int day) {
		if(day>= 1 && day<=5) {
			return "上课";
		}else if(day== 6) {
			return "游戏";
		}else if(day == 7) {
			return "睡觉";
		}else {
			return "无效";
		}
	}
	
	public static void sum2(int a,int b) {
		System.out.println(a + b);
	}
	
	/**
	 * 学生计算三个变量的和，并返回结果
	 * @param args
	 */
	
	public static int sum3(int a,int b,int c) {
		return a + b + c;
	}
	
	public static void main(String[] args) {
		eat();
		//调用并打印结果
		System.out.println("推荐睡眠时间:" + sleep());
		//调用 3 实参
		System.out.println(thing(6));
	}
}

```

总结：

```java
无参数  无返回  public void 方法名(){} 

无参数  有返回  public 返回类型 方法名(){return xx;}

有参数  无返回  public void 方法名(形参){ }

有参数  有返回  public 返回类型 方法名(形参) {return xx;}
```



#### 3.8  对象的创建

> 类是一类事物的归纳总结，抽象的概念，不是实际存在的个体，类中属性和方法需要对象才能使用的。

##### 3.8.1 对象创建【重点】

```java
类 对象名 = new 类();
```

##### 3.8.2  属性调用

```java
//给属性赋值
对象名.属性名 = 值;

//获取属性值
System.out.println(zxy.name);
```

##### 3.8.3  内存分配

> 对象内存的开辟是在 "堆"中 ，当对象创建后，在堆里创建该类的所有属性开辟空间，每个属性都有默认值，
>
> int  0  double 0.0  引用 null  char \u0000 boolean false

![](img\14.PNG)

示例代码

```java
public class TestStudent {
	public static void main(String[] args) {
		//创建学生类个体
		Student zxy = new Student();
		zxy.sNo = 110;
		zxy.name = "朱鑫宇";
		zxy.sClass = 2302;
		zxy.score = new double[] {89,75,62};
		//地址
		System.out.println(zxy);
		System.out.println(zxy.name);
		//System.out.println(zxy.a);
		
		//方法
		zxy.eat();
		//s接收返回
		double s = zxy.getSum();
		System.out.println(s);
	}
}

```



```java
圆类 Circle
常量 PI
变量 半径r

方法：
周长
面积


创建某圆对象  设置r = 3 调用周长方法 

public class Circle {

	//属性
	public final double PI = 3.14;
	public int r ;
	
	//方法
	public double getC() {
		return 2 * PI * r;
	}
	
	public double getS() {
		return PI * r * r;
	}
}


public class TestCircle {
	public static void main(String[] args) {
		//创建圆
		Circle c1 = new Circle();
		c1.r = 3;
		
		System.out.println("圆的周长:" + c1.getC());
		System.out.println("圆的面积:" + c1.getS());
		
		
		Circle c2 = new Circle();
		c2.r = 5;
		
		System.out.println("圆的周长:" + c2.getC());
		System.out.println("圆的面积:" + c2.getS());
	}
}
```

练习：

```java
计算器类 Computer
完成两个整数【传参】的 加减乘除【四个方法】

创建计算器对象，测试计算器

package com.cl.oop;

public class Computer {
	
	/**
	 * 加法
	 */
	public int add(int a,int b) {
		return a + b;
	}
	//重载方法
//	public int add(int a,int b,int c) {
//		return a + b + c;
//	}
	//可变长参数
//	public int add(int ...a) {
//		//a数组
//	}
	
	/**
	 * 减法
	 */
	public int sub(int a,int b) {
		return a > b ? a - b : b - a;
	}
	
	
	/**
	 * 乘法
	 */
	public int mul(int a,int b) {
		return a * b ;
	}
	
	/**
	 * 除法
	 */
	public double div(int a,int b) {
		if(b == 0) {
			return 0;
		}else {
			return a * 1.0 / b;
		}
	}
}

```

##### 3.8.4 变量的划分

> 变量分成两种： 全局变量【属性】，局部变量。

|          | 全局变量                   | 局部变量            |
| -------- | -------------------------- | ------------------- |
| 位置     | 类里方法外                 | 方法里，形参变量    |
| 默认值   | 有                         | 没有                |
| 控制权限 | 必须加权限                 | 不能加权限          |
| 内存     | 堆                         | 栈                  |
| 生命周期 | 对象创建出现，对象销毁消失 | 所在方法{开始 }结束 |
| 使用范围 | 整个类                     | 所在{ }             |

全局变量和局部变量重名： 局部将全局变量覆盖，当获取全局变量时，使用

```java
this.全局变量
```



#### 3.9  方法的调用

```
1.对象.方法();

2.类中两个方法互相调用 

3.递归调用
```



##### 3.9.1 对象调用方法

```java
对象名.方法名();

1 调用方法的时候，方法声明了形参，一定传递实参  形参变量 = 实参 
2 调用方法，程序自动跳到声明位置执行，执行完，回原调用位置继续...
3 调用方法检查返回值，方法有返回值，调用位置一定接收或打印返回结果
					空返回值，直接调用
					
Computer c = new Computer();
int s = c.add(1, 2);
System.out.println(s);
c.test(1, 4);
System.out.println("变量和:" + c.add(1, 2));
```

##### 3.9.2 类中方法互相调用

```java
一个类的中两个方法 a()  b() 互相调用

public void a(){
	//直接调用
    //this.b();
    b();
}

调用原则： 
    1. a()方法调用b，b方法中不能调用a()方法
    2. a()方法调用b() ,一定先执行b()方法，b执行结束，回到a继续
public class Kid {
	
	public void play() {
		eat();
		System.out.println("玩游戏");
	}
	
	public void eat() {
		System.out.println("吃饭");
	}
	
	public void study() {
		play();
		System.out.println("学习");
	}
	
	public static void main(String[] args) {
		Kid k = new Kid();
		k.study();
	}
}
吃饭
玩游戏
学习
```

示例代码

```java
public class TestMethod1 {
	
	public void a() {
		c();
		System.out.println("a");
		
	}
	
	public int b() {
		System.out.println("b");
		return 2;
	}
	
	public void c() {
		System.out.println("c" + b());
	}
	
	public static void main(String[] args) {
		new TestMethod1().a();
		//b
		//c2
		//a
	}
}
```



练习：

```java
ScoreCalc

属性：
java
html
db

三个方法
计算三门分数和 sum
计算三门分数平均值 avg
打印总分 平均分

测试类分数自定义，调用打印方法


public class ScoreCalc {
	public double java;
	public double html;
	public double db;
	
	/**
	 * 求和
	 * @return 和
	 */
	public double sum() {
		double s = java + html + db;
		return s;
	}
	
	/**
	 * 
	 * @return 平均值
	 */
	public double avg() {
		double avg = sum() / 3 ;		
		return avg;
	}
	
	public void print() {
		System.out.println("和为:" + sum() + "，平均分:" + avg());
	}
	
}
```

##### 3.9.3 方法递归

> 方法自己调用自己。一定要有终止调用条件，否则是死递归。

```java
// 设计一个方法，传入变量n，返回n!

package com.cl.oop;

public class TestMethod2 {
	/**
	 * 
	 * @param n  谁的阶乘
	 * @return  结果
	 */
//	public static double getJc(int n) {
//		double mul = 1;
//		for (int i = 1; i <= n; i++) {
//			mul *= i;
//		}
//		return mul;
//	}
	/**
	 * 1! = 1
	 * 2! = 1! * 2
	 * 3! = 2! * 3
	 * n! = (n - 1) ! * n
	 * @param n
	 * @return
	 */
	public static double getJc(int n) {
		if(n == 1) {
			return 1;
		}
		return getJc(n - 1) * n;
	}
	
	public static void main(String[] args) {
		System.out.println(getJc(5));
	}
}

```

#### 3.10 类图的构建

> 面向对象设计中，将类使用类图呈现。

![](img\15.PNG)

示例图:

![](img\16.PNG)



#### 3.11对象和数组

###### 3.11.1 对象的属性是数组

学生的三门成绩

```java
public class Student {
	
	public String name;
	//数组,学生的三门成绩
	public double[] scores;
	
	//toString
}

```

创建学生对象

```java
public class TestStudent {
	public static void main(String[] args) {
		Student s = new Student();
		//System.out.println(s.name);
		//System.out.println(s.scores);
		
		s.scores = new double[3];
		//System.out.println(s.scores);
		s.scores[0] = 100;
		s.scores[1] = 90;
		s.scores[2] = 80;
		//System.out.println(s.scores[0]);
		
		//学生成绩遍历
//		for (int i = 0; i < s.scores.length; i++) {
//			System.out.println(s.scores[i]);
//		}
		
//		for (double a : s.scores) {
//			System.out.println(a);
//		}
		
		System.out.println(Arrays.toString(s.scores));
	}
}
```

![](img\18.PNG)

练习： 打印该学生的成绩最大值（学生的成绩可以控制台接收）

```java
		//最大值
		double max = 0;
		//一个学生，三个成绩，三个成绩最大值
		for (int i = 0; i < s.scores.length; i++) {
			if(max < s.scores[i]) {
				max = s.scores[i];
			}
		}
		System.out.println("最高分:" + max);
```

###### 3.11.2 数组的类型是对象

> 数组的数据类型是类【对象】。代表有多个对象。

声明语法：

```
类 [] 数组名 = new 类[大小];
```

例如：

```java

public class Teacher {
	
	public String name;
	public String subject;
	public double mark;
	@Override
	public String toString() {
		return "Teacher [name=" + name + ", subject=" + subject + ", mark=" + mark + "]";
	}
	
	
}
```

多个老师,老师数组

```java
Teacher [] t = new Teacher[3];

t[0] = new Teacher();
t[1] = new Teacher();
t[2] = new Teacher();

t[0].name = "于老师";
t[0].subject = "JAVA";
t[0].mark = 90;
```

![](img\19.PNG)

教师系统类

```java
public class TeacherSys {

	// 系统包含多个老师
	public Teacher[] teachers;

	/**
	 * 构建老师
	 */
	public void init() {
		// 创建老师数组
		teachers = new Teacher[3];
		// 创建一个老师对象
		teachers[0] = new Teacher();
		teachers[0].name = "姜老师";
		teachers[0].subject = "HTML";
		teachers[0].mark = 80;

		// 创建第二个老师对象
		teachers[1] = new Teacher();
		teachers[1].name = "于老师";
		teachers[1].subject = "JAVA";
		teachers[1].mark = 95;
        
        
		teachers[2] = new Teacher();
		teachers[2].name = "毛老师";
		teachers[2].subject = "JAVA";
		teachers[2].mark = 95;
		
	}

	@Override
	public String toString() {
		return "TeacherSys [teachers=" + Arrays.toString(teachers) + "]";
	}
	
	
}
```

测试类

```java
public class TestSys {
	public static void main(String[] args) {
		TeacherSys s = new TeacherSys();
		
		s.init();
		System.out.println(s);
	}
}
```

对应类图:

![](img\17.PNG)

![](img\20.PNG)练习：购物系统



![](img\21.PNG)

```java
package com.cl.demo.shopping;
/**
 *  顾客类
 * @author Administrator
 *
 */
public class Customer {
	public int no;
	public String pass;
	//顾客积分
	public double cre;
	public boolean vip;
	
	/**
	 * 登录方法
	 * @param no 用户登录时候填写的账号
	 * @param cPass 用户登录时候填写的密码
	 * @return boolean表示是否可以登录成功
	 */
	public boolean login(int no,String pass) {
		if(this.no == no && this.pass.equals(pass)) {
			return true;
		}else {
			return false;
		}
	}
	
	/**
	 * 购买支付方法: vip 八折  积分抵扣 1000顶10
	 * @param money 购买金额
	 * @return 实付金额
	 */
	public double pay(double money,int c) {
		if(vip) {
			money *= 0.8;
		}
		//判断积分
		if(c != 0) {
			money -= (c / 1000) * 10;
			
			//积分减掉重置
			cre -= c;
		}
		return money;	
	}
}


package com.cl.demo.shopping;
/**
 * 商品类
 * @author Administrator
 *
 */
public class Goods {
	public int no;
	public String name;
	public double price;
	//库存数量
	public int count;
	@Override
	public String toString() {
		return "Goods [no=" + no + ", name=" + name + ", price=" + price + ", count=" + count + "]";
	}	
}


package com.cl.demo.shopping;

import java.util.Arrays;
import java.util.Scanner;

/**
 * 购物系统
 * 
 * @author Administrator
 * @version 3.0
 */
public class Shopping {

	// 商品数组
	public Goods[] goods;
	
	public Customer c;
	
	// 商品上架,顾客存储
	public void init() {
		Scanner sc = new Scanner(System.in);
		goods = new Goods[3];
		for (int i = 0; i < goods.length; i++) {
			goods[i] = new Goods();
//			System.out.println("请输入商品信息【编号 名称 价格  库存】");
//			goods[i].no = sc.nextInt();
//			goods[i].name = sc.next();
//			goods[i].price = sc.nextInt();
//			goods[i].count = sc.nextInt();
		}
		goods[0].no = 1;
		goods[0].name = "辣条";
		goods[0].price = 5;
		goods[0].count = 100;
		
		goods[1].no = 2;
		goods[1].name = "汉堡";
		goods[1].price = 15;
		goods[1].count = 20;
		
		
		goods[2].no = 3;
		goods[2].name = "火腿肠";
		goods[2].price = 3.5;
		goods[2].count = 200;
		
		c = new Customer();
		c.no = 1001;
		c.pass = "admin123";
		c.cre = 5000;
		c.vip = true;
		
	}

	public void menu() {
		Scanner sc = new Scanner(System.in);
		System.out.println("欢迎使用我行我素购物系统3.0版本");
		while (true) {
			System.out.println("1-登录系统");
			System.out.println("2-退出");

			System.out.println("请输入选项");
			int i = sc.nextInt();
			if (i == 1) {
				// 登录
				System.out.println("请输入账户和密码");
				//顾客调用login方法
				boolean boo = c.login(sc.nextInt(), sc.next());
				System.out.println(boo && c.vip ? "尊敬的VIP您好"  : "用户您好");
				System.out.println(boo ? "登录成功，欢迎您" + c.no  : "账户或密码错误");
				
				// 二级菜单
				while (true) {
					System.out.println("1-购买商品");
					System.out.println("2-查询商品");
					System.out.println("3-积分查询");
					System.out.println("4-真情回馈");
					System.out.println("5-退出");
					System.out.println("请输入选项");
					int opr = sc.nextInt();
					if (opr == 1) {
						double sum = buy();
						System.out.println("总计金额:" + sum);
						//支付
						System.out.println("顾客您剩余:" + c.cre + "是否使用？ 0/xx");
						//判断
						double p = c.pay(sum,sc.nextInt());
						System.out.println("实付:" + p);
						System.out.println("积分剩余:" + c.cre);
					} else if (opr == 2) {

					} else if (opr == 3) {

					} else if (opr == 4) {

					} else if (opr == 5) {
						System.out.println("系统注销中.....");
						break;
					} else {
						System.out.println("非法操作");
					}
				}

			} else if (i == 2) {
				System.out.println("谢谢使用");
				break;
			} else {
				System.out.println("选项有误");
			}
		}
	}
	/**
	 * 购买方法
	 * @return 返回总计金额
	 */
	public double buy() {
		Scanner sc = new Scanner(System.in);
		double sum = 0;
		do {
			System.out.println("请选择购买的商品编号");
			for (int i = 0; i < goods.length; i++) {
				System.out.print(goods[i].no + ":" + goods[i].name + "\t" + goods[i].price + "\t");
			}
			System.out.println();
			System.out.println("请输入商品编号");
			int pNo =  sc.nextInt();
			
			//查找问题,找到的商品下标
			int index = find(pNo);
			if(index != -1) {
				//有商品
				System.out.println("请输入商品数量");
				int pCount =  sc.nextInt();
				
				//判断库存
				if(goods[index].count >= pCount) {
					//充足
					sum += pCount * goods[index].price;
					//更新库存
					goods[index].count -= pCount;
					System.out.println("购买成功该商品：" + goods[index]);
				}else {
					System.out.println("sorry,库存不足");
				}
				
				
			}else {
				System.out.println("暂未上架");
			}							
			
			System.out.println("是否继续购买y/n");
			
		}while(sc.next().equals("y"));
		
		return sum;
	}
	
	public int find(int no) {
		for (int i = 0; i < goods.length; i++) {
			if (goods[i].no == no) {

				return i;
			}
		}
		return -1;
	}
	
	
	@Override
	public String toString() {
		return "Shopping [goods=" + Arrays.toString(goods) + "]";
	}
}


public class TestShopping {
	public static void main(String[] args) {
		Shopping p = new Shopping();
		p.init();
		p.menu();
		//System.out.println(p);
	}
}
```

#### 3.12 方法的参数

##### 3.12.1 参数定义

1.固定长度的方法参数

```java
1.方法名相同，参数相同，在一个类中不能共存
2.方法的重载： 方法名相同，参数不同【个数，类型，顺序】
public class TestMethod {
	//以下方法都是重载
	public void sum(int a,int b) {
		
	}
	public void sum(double a,double b) {
		
	}
	public void sum(double a,int b) {
		
	}
	public void sum(int a,double b) {
		
	}
	public void sum(int a,int b,int c) {
		
	}
}
```

2.可变长参数【jdk5+】

> 参数的个数任意。

```java
public 返回值 方法名(参数类型 参数变量, 参数类型 ... 变量名) {
		
}
```

注意：

1,   可变长参数一定放在参数列表最后

2，可变长参数在方法中看作数组

3，如果想任意类型的参数，参数类型设置为Object

示例代码：

```java
public static double add(String name,double ...a) {
		double sum = 0;
		for (int i = 0; i < a.length; i++) {
			sum += a[i];
		}
		return sum;
	}
public static void main(String[] args) {
		System.out.println(add("ys",1,2,6.0,7,34));
}
```

练习：

```java
设计一个类 
max() 获得2个整数最大值
max() 重载方法三个数最大值
max() 重载方法n个数最大值
    
public class TestMethod2 {
	
	public int max(int a,int b) {
		return a > b ? a : b;
	}
	
	public int max(int a,int b,int c) {
		int max =  a > b ? a : b;
		max = max > c ? max : c;
		return max;
	}
	
	public int max(int...a) {
		int max =  0;
		for (int i = 0; i < a.length; i++) {
			if(max < a[i]) {
				max = a[i];
			}
		}
		return max;
	}
}
```

##### 3.12.2 参数传递

> 当方法被调用的时候，实参给形参赋值，传递值
>
> 当传递的值基本类型，只传递值
>
> 当传递的值引用类型，传递的是"地址"

示例代码

```java
public class TestMethod3 {
	
	public static void main(String[] args) {
		Computer c = new Computer();
		c.name = "雷神";
		
//		Computer c2 = c;
//		c2.name = "联想";
//		
//		System.out.println(c.name);
//		System.out.println(c2.name);
		
		int a = 10;
		int[] m = {1,2,3,4};
		test(a,c,m);
		System.out.println(a);//10
		System.out.println(c.name);//联想
		System.out.println(Arrays.toString(m));//88 2 3 4
	}
	
	public static void test(int a ,Computer c,int[] m) {
		a = 20;
		//c.name = "联想";
		c = new Computer();
		c.name = "联想";
		m[0] = 88;
	}
}
```

练习:

```java
public class TestMethod4 {
	
	public static void main(String[] args) {
		int x = 100, y = 200;
		swap(x,y);
		System.out.println(x + "," + y);//100 200
	}
	
	public static void swap(int x ,int y) {
		int temp = x;
		x = y;
		y = temp;
		System.out.println(x + "," + y);//200 100
	}
}
```

注意： String类型的特殊的

```java
public class TestMethod5 {
	
	public static void main(String[] args) {
		String s = "abc";
		swap(s);
		System.out.println(s); //abc
	}
	
	public static void swap(String s) {
		s = "abcd";
	}
}

```



#### 3.13  构造方法 

> 又叫做构造器，是一个特殊的方法，专门用于对象创建的时候给属性做初始化的。



##### 3.13.1 作用

```
1. 直接为与生俱来的对象的属性直接赋值，如创建的人对象的时候，姓氏固定
2. 创建对象的时候，给所有属性【某些属性】一次性直接赋值
3. 简化属性赋值
```



##### 3.13.2  声明

```java
控制权限 类名(形参类型 形参变量...){
    //给属性初始化
    
}

```

注意：

1. 构造方法没有设定返回声明
2. 构造方法的方法名是固定： 类名
3. 参数可有可无，无参数构造器   带参数构造器给属性赋值



##### 3.13.3  调用

1.调用时机

```
创建对象的时候，new
类 对象 = new 类();
```

2.调用者

```
JVM，构造方法JAVA虚拟机在创建对象的时候，自动调用
```

3.具体调用哪一个

```
调用时候的实参
```

4.构造方法的分类

```java
参数角度：【构造方法的重载】
		无参数 
		带参数  利用参数给属性赋值
构造显性隐性
		隐性 ： 系统为JAVA类自动生成构造方法
		class A{	
            A(){

            }
        }
        public class Goods {
        	public Goods() {
		
			}    
        }
		显性： 手动添加构造方法，一旦显性定义构造，隐性失效，被覆盖
        注意： ******一定将无参数构造手动添加******
```

示例代码

```java
public class TestCustomer {
	public static void main(String[] args) {
		//调用构造，初始化
        Customer c = new Customer();		
		Customer c2 = new Customer(1, "jack", 3000, true);
		
		//调用toString
		System.out.println(c2);
	}
}
```



思考：构造方法和普通方法的区别？ 区分？ 普通方法的名字可以是类名？

```
构造方法特殊方法，普通方法的名字可以类名，不推荐
```

|          | 构造方法     | 普通方法                |
| -------- | ------------ | ----------------------- |
| 返回类型 | 没有         | 有返回声明【void  int】 |
| 作用     | 给属性赋值   | 自定义                  |
| 隐性     | 系统有默认的 | 没有                    |
| 调用方式 | JVM          | 对象.xx()    this.xx()  |
| 调用时机 | new          | 任意                    |
| 调用次数 | 1个对象1次   | 1个对象n次              |



#### 3.14  包和导包

##### 3.14.1 包声明

```java
package  根包.子包.子包 ;
```

注意：

1.置于JAVA源文件有效代码第一行

2.包命名要小写，.间隔 ，  网站后缀.企业名.项目名.xxx   xxx模块名    com.cl.medicine.pill/admin/store    edu.neu.web 

3.作用 ：  1.有效管理JAVA源文件 2.限制类的权限和访问

##### 3.14.2 导包声明

```java
import 根包.子包.类/接口;
import 根包.子包.* ; //引入该包全部资源
```

注意：

1. import导入包可以写多个
2. 导入的可以是JAVA内的资源，也可以本项目其他包的资源

##### 3.14.3  JAVA中可用资源

```java
java.lang      JAVA核心包，内含JAVA核心类： String  System Object  线程....

java.util      JAVA工具包，内含JAVA工具类 ： 集合类  日期类  Scanner  Arrays ....
    
java.io        JAVA读写文件包，内含文件操作，读写IO
    
java.net	   JAVA网络相关，Socket  协议  TCP IP
 
java.sql	   JAVA和数据库操作相关的包
```

注意： 仅有java.lang包不需要使用import就可以使用，系统自动导入。

总结：

JAVA源文件构成：

```
包声明;
导包声明 + ;
类声明 + ;
public class A{
	//属性
	
	//构造方法
	
	//方法
}
class B{
	//属性
	
	//构造方法
	
	//方法
}
//....
```

编码习惯：

```
包 : 全小写
类【接口，枚举，注解】 : 首字母大写
属性、方法、变量 ： 小写或驼峰
常量 : 全大写
```



#### 3.15  对象包含关系

> 两种类型的关联性，对象关系，常见的关联关系【包含，有.....】
>
>  比如： 学校有学生 ， 图书馆有图书  ， 停车场和车 ，   银行客户有账户  ，  线段有两点 ...
>
> 三种关联： 1对1   1对多   多对多     1:1    1:n    m:n
>
> 比如： 一个学生 一个椅子        一个教室 多个学生        学生和课程 



1对1：

```java
//学校类
public class School{
	
	public PlayGround p;
}

//操场类
public class PlayGround{
    
}
```

1对多：

```java
//学校类
public class School{
	
	public PlayGround p;
	
	public Student[] stu;
}

//学生类
public class Student{
    
}
```

练习：

```
点类 ： x和y坐标
线段类： 包含两点，线程长度
		获得线段长度的方法
```

|        Point        |
| :-----------------: |
| +x:int<br />+y:int  |
| +Point(x:int,y:int) |
|       info()        |

|                     Line                     |
| :------------------------------------------: |
| +p1:Point<br />+p2:Point<br />+length:double |
|           +Line(p1:Point,p2:Point)           |
|               getLen():double                |



1对多

|                       Card                        |
| :-----------------------------------------------: |
| +cNo:String<br /> +cPass:int<br />+balance:double |
|                       ....                        |
|                                                   |

|                           Customer                           |
| :----------------------------------------------------------: |
| +cards:Card[]<br />             +name:String<br />+id:String |
|                             ....                             |
| +checkCard(String no,int pass): int<br />+update(int newPass):boolean<br /> |

|                           Banking                            |
| :----------------------------------------------------------: |
|                       +cus:Customer[]                        |
|                                                              |
| open():String<br />close(String no):boolean<br />transfer()<br />deposit(m:double):boolean<br />withdraw(m:double):boolean<br />checkBalance():double<br />menu() |

#### 第四章 JAVA三大基本特性

> JAVA三大基本特性： 封装，继承和多态。
>
> 封装性：  JAVA中信息或数据的隐藏和包装，保证数据安全性
>
> 继承性：  JAVA中代码【属性和方法】的继承，提高代码的重用性，避免冗余
>
> 多态性： 基于继承性，父类呈现更多种形态， 提高代码的扩展性，延展性，灵活



#### 4.1  封装性

> JAVA中属性或方法的隐藏，（在极其个别情况下隐藏构造），让属性或方法无法被访问。

##### 4.1.1 作用

```
提高类的成员的安全性
	1. 无法任意访问
	2. 不能非法赋值  
```

##### 4.1.2  实现过程

封装属性：

```
1.使用权限： private 私有的，修饰属性和方法，使用范围仅限于当前类 

2.属性添加一对方法[公开的]
  setXX(XX x)  赋值
  xx getXX()   取值
  
3. 在方法中添加限制条件，保证安全  
```

注意：

1. 开发中，所有的属性都私有化，为了安全，每个属性都会对应两个方法 setXX getXX
2. 方法中添加条件，保证安全

思考： 有getXX setXX之后，是否需要构造？

需要，一个私有属性被赋值全过程

```
1. 默认值
2. 属性声明时值
3. 构造方法得值
4. setXX()
```

示例代码

```java
package com.cl.oop;

public class Animal {
	
	//名字
	private String name = "娜娜";
	//腿个数    必须是0 2 4 8
	private int legs;
	//年龄 必须大于0
	private int age;
	
	
	public Animal() {
	}
	
	public Animal(String name, int legs, int age) {
		super();
		this.name = name;
		this.legs = legs;
		this.age = age;
	}
	public String getName() {
		return name;
	}
	public void setName(String name) {
		this.name = name;
	}
	
	public int getLegs() {
		return legs;
	}
	public boolean setLegs(int legs) {
		if(legs == 0 || legs == 2 || legs == 4 || legs == 8 ) {
			this.legs = legs;
			return true;
		}else {
			return false;
		}
		
	}
	
	public int getAge() {
		return age;
	}
	public void setAge(int age) {
		if(age > 0)
			this.age = age;
		else
			System.out.println("年龄不合法");
	}

	@Override
	public String toString() {
		return "Animal [name=" + name + ", legs=" + legs + ", age=" + age + "]";
	}	
}

package com.cl.oop;

public class Card {
	private String cNo;
	private int cPass;
	//余额
	private double balance;
	
	public String getcNo() {
		return cNo;
	}

	public void setcNo(String cNo) {
		this.cNo = cNo;
	}

	public int getcPass() {
		return cPass;
	}

	public void setcPass(int cPass) {
		this.cPass = cPass;
	}

	//设置
	public void setBlanace(double balance) {
		if(balance <= 0) {
			System.out.println("金额错误");
		}else {
			this.balance = balance;
		}	
	}
	
	//获取
	public double getBalance() {
		if(cNo.equals("123456") && cPass == 123456)
			return balance;
		else
			return 0;
	}
	
	
	
	public Card(String cNo, int cPass) {
		super();
		this.cNo = cNo;
		this.cPass = cPass;
	}
	
	public Card() {
		
	}

	@Override
	public String toString() {
		return "Card [cNo=" + cNo + ", cPass=" + cPass + ", balance=" + balance + "]";
	}	
}

```

```java
public class Test {
	public static void main(String[] args) {
		//Card c = new Card("123456", 123456);
		//c.setBlanace(2000);
		//System.out.println(c.getBalance());
		
		Animal a = new Animal("莉莉",4,1);
		//a.age = -9;
		//年龄变大
		//a.setAge(a.getAge() + 1);
		a.setName("花花");
		System.out.println(a);
	}
}

```

封装方法：

> JAVA中封装主要是封装属性，但是有些封装方法，当某些方法仅需要类内部调用，无需外部暴露，方法封装。

```java
package com.cl.oop;

public class TV {
	private String brand;
	private String size;
	
	public TV() {
		
	}
	
	public TV(String brand, String size) {
		super();
		this.brand = brand;
		this.size = size;
	}

	public String getBrand() {
		return brand;
	}

	public void setBrand(String brand) {
		this.brand = brand;
	}

	public String getSize() {
		return size;
	}

	public void setSize(String size) {
		this.size = size;
	}
	//该方法仅限于类内部使用
	private void work() {
		System.out.println("电视零件启动工作.....");
	}
	
	public void open() {
		System.out.println(brand + "电视被打开");
		work();
	}
	
	public void close() {
		System.out.println(brand + "电视被关闭");
		work();
	}

	@Override
	public String toString() {
		return "TV [brand=" + brand + ", size=" + size + "]";
	}
}

```

封装构造

> 不希望外部创建对象。

单例设计【单实例，永远一个对象，共享一个： 地球，太阳】

设计模式 23种常用

```java
public class Earth {
	
	private static Earth e = new Earth();
	//私有化构造
	private Earth() {
		
	}
	
	public static Earth getEarth() {
		return e;
	}

}
```



#### 4.2  继承性

> JAVA代码的继承： 利用现有的类创建新类的过程。
>
> 现有的类 ： 父类 ， 根类 ， 基类 ， 超类
>
> 新类： 子类  ，派生类 ， 衍生类



##### 4.2.1 作用

```
代码重用，提供代码的复用，减少冗余
```

##### 4.2.2 实现过程

父类：

```java
public class Person extends Object{
	public String id;
    public String name;
    public int age;
    public String gender;
    
    public void eat() {
    	System.out.println(name + "吃饭");
    }
    
    public void sleep() {
    	System.out.println(name + "睡觉");
    }
}
```

子类：

```java
public class Student extends Person{
	//....
    
    //学生的属性
    public int sno;
    public String subject;
    
    //学生行为
    public void study() {
    	System.out.println("学习");
    }
    
}
```

##### 4.2.3 可以继承什么

```
非私有的属性和方法
不能继承构造方法【需要调用】
```

练习：

```java
子类Teacher继承父类Person，添加行为授课
测试老师

public class Teacher extends Person{
	
	public void teach() {
		System.out.println(getName() + "在授课");
	}
}

```



##### 4.2.4 JAVA中继承的特点

```
1. JAVA中继承关系： 单继承 【一个父类可以有多个子类，每个子类只能一个父类】
2. JAVA继承关系多层继承： 祖先 > 爷爷 > 父类 >子类 ...
3. JAVA的祖先类 Object 所有的类都直接或间接继承它
4. JAVA中继承： 顶层 抽象，底层 具体
```

![](img\22.PNG)

##### 4.2.5  JAVA中权限【重点】

| 权限         | 含义     | 使用范围           |
| ------------ | -------- | ------------------ |
| private      | 私有的   | 仅限当前类         |
| 缺省【默认】 | 友好的   | 同包友好           |
| protected    | 受保护的 | 同包友好，跨包继承 |
| public       | 公开的   | 整个项目使用       |

范围排序：

```java
private < default < protected < public 
```

可以修饰：

```
类 、接口 、枚举 :   public / 缺省 

属性 、方法 、构造 ： 四个

局部变量： 不加权限
```

示例代码



```java
package com.cl.oop.x;
public class A {
	public int x = 10;
	protected int y = 20;
	int z = 30;
	private int k = 40;
	
	public void test() {
		//public int m = 50;
	}
}

public class B {
	
	public void test() {
		A a = new A();
		System.out.println(a.x);
		System.out.println(a.y);
		System.out.println(a.z);
		//System.out.println(a.k);
	}
}

```

```java
package com.cl.oop.y;
import com.cl.oop.x.A;
public class C {	
	public void test() {
		A a = new A();
		System.out.println(a.x);
		//System.out.println(a.y);
		//System.out.println(a.z);
		//System.out.println(a.k);
	}
}

package com.cl.oop.y;
import com.cl.oop.x.A;
public class D extends A{
	
	public void test() {
		
		System.out.println(x);
		System.out.println(y);
		//System.out.println(z);
		//System.out.println(k);
	}
}
```



##### 4.2.6 方法的重载和重写[重点]

方法的重写：

方法的覆盖，当子类继承父类的行为，子类重写或覆盖父类的行为，方法重写。

重写的条件：

```
1. 方法名相同
2. 参数必须相同
3. 返回值必须相同
4. 权限不能降低 
```

注意： 子类覆盖父类行为，子类调用该行为，执行自己的

练习：

```java
Card  普通卡
	积分 credit
	pay(double money)  正常支付，积分抵扣 1000抵扣10元
	
黑金卡 
	重写： 八折，1000抵扣100
钻石卡
	重写： 有50%免单 ，不免7折
	
测试....
    
public class Card {
	private int credits;

	public int getCredits() {
		return credits;
	}

	public void setCredits(int credits) {
		this.credits = credits;
	}
	
	public double pay(double money) {
		//3500
		int c = credits / 1000 ;
		double m = money - c * 10;
		credits %= 1000;
		return m;
	}
}

class BlackCard extends Card{
	public double pay(double money) {
		int c = getCredits() / 1000 ;
		double m = money * 0.8 - c * 100;
		setCredits(getCredits() % 1000); 
		return m;
	}
}

class DiamondCard extends Card{
	public double pay(double money) {
		int a = (int)(2 * Math.random() + 1);
		if(a == 1) {
			return 0;
		}else {
			return money * 0.7;
		}		
	}
}
```

重载和重写【重点背】

|          | 重载                   | 重写【覆盖】       |
| -------- | ---------------------- | ------------------ |
|          | overload               | override           |
| 作用     | 方法根据参数实现多样化 | 子类覆盖父类行为   |
| 参数     | 参数不同               | 必须相同           |
| 返回类型 | 不限制                 | 必须相同           |
| 权限     | 不限制                 | 必须不能降低       |
| 次数     | n次                    | 1次                |
| 位置     | 父类、子类             | 子类重写           |
| 构造方法 | 可以                   | 不可以             |
| 异常抛出 | 不限制                 | 不能比父类抛出更多 |

##### 4.2.7 继承后的构造方法

```java
1.父类中的构造方法，不能被子类继承
2.子类需要初始化父类继承的属性，需要调用父类的构造方法
   super(); 调用父类的空构造
   super(参数1，参数2...);  调用参数对应的父类的构造方法
```

示例代码：

```java
public class Person extends Object{
	private String id;
	private String name;
	private int age;
	private String gender;
	

    public String getId() {
		return id;
	}

	public void setId(String id) {
		this.id = id;
	}

	public String getName() {
		return name;
	}

	public void setName(String name) {
		this.name = name;
	}

	public int getAge() {
		return age;
	}

	public void setAge(int age) {
		this.age = age;
	}

	public String getGender() {
		return gender;
	}

	public void setGender(String gender) {
		this.gender = gender;
	}

	public Person() {
    	//super();
    }
    
    public Person(String name, int age) {
		//super();
		this.name = name;
		this.age = age;
	}

	public Person(String id, String name, int age, String gender) {
		super();
		this.id = id;
		this.name = name;
		this.age = age;
		this.gender = gender;
	}
    
	public void eat() {
    	System.out.println(name + "吃饭");
    }
    
    public void sleep() {
    	System.out.println(name + "睡觉");
    }

	@Override
	public String toString() {
		return "Person [id=" + id + ", name=" + name + ", age=" + age + ", gender=" + gender + "]";
	}  
    
}
```

子类：

```java
public class Student extends Person{
	//....
	
    //学生的属性
    private int sno;
    private String subject;
    
    public int getSno() {
		return sno;
	}

	public void setSno(int sno) {
		this.sno = sno;
	}

	public String getSubject() {
		return subject;
	}

	public void setSubject(String subject) {
		this.subject = subject;
	}
	public Student(String name, int age,int sno, String subject) {
		//前两个属性父类继承，调用父类的构造
		super(name,age);
		//子类自己定义的属性自己初始化
		this.sno = sno;
		this.subject = subject;
	}
	public Student(String id, String name, int age, String gender,int sno, String subject) {
        //调用父类的四个参数构造
		super(id,name,age,gender);
		this.sno = sno;
		this.subject = subject;
	}

	//学生行为
    public void study() {
    	System.out.println("学习");
    }

	@Override
	public String toString() {
        //super.方法() 父类被覆盖的方法
		return super.toString() + "Student [sno=" + sno + ", subject=" + subject + "]";
	}  
}
```

```java
3. 子类super调用父类的构造方法，只是执行代码，并没有创建对象【重点】

4. JAVA构造方法执行顺序： 祖先 > 父类 > 子类 【继承关系】

5. 为了保证构造方法的执行顺序，每个构造方法的首行必须是super调用

 显式调用  super(参数);
 public Student(String name, int age,int sno, String subject) {
		//前两个属性父类继承，调用父类的构造
		super(name,age);
		//子类自己定义的属性自己初始化
		this.sno = sno;
		this.subject = subject;
 }
 隐式调用 super(); 即使不写，系统默认添加，调用父类的空构造
 class Son extends Father{
	public Son() {
		//super();
		System.out.println("儿子出现了");
	}
 }

因此，每个类都要补加 空构造，保证子类顺利调用【一旦定义构造方法，空构造会被覆盖】
```

##### 4.2.8 super和this

```java
super两种用法： 继承关系中，子类中使用super

1. 子类中调用父类的构造方法
   super()
   super(参数)
   
2. 子类中调用父类的成员【属性、方法】
	super.父类属性
	super.父类方法
public String getMsg() {
		//调用父类的信息方法
		return super.getMsg() + "count=" + count + "]";
	}
	//重写
	@Override
public double getGongLi() {
		// 调用父类方法计算
		return super.getGongLi() / count;
	}
```



#### 4.3 类之间关系

> 类和类之间关系： 泛化【继承和实现】，关联，依赖，组合，聚合

关联："有"  has a   学生 学校

```java
public class A{
    //一对一
	public B b;
    //一对多
    public C[] c;
}

public class B{

}

public class C{

}
```

继承： 是   is  a   学生   人类

```java
public class A{

}

public class B extends A{

}
```

依赖 ： 用  use a    学生 交通工具

```java
public class A{
	
	public void test(B b){
	
	}
	public B test(){
	
	}
}

public class B{

}
```



#### 4.4  多态性

> 广义上，一个父类呈现出多种子类的形态，称之为多态。得有继承，一个父类多个子类。

##### 4.4.1 作用

```
1. 提高代码的灵活性，扩充性，延展性

2. 降低耦合 【高内聚 低耦合 】
```

##### 4.4.2 多态的实现

狭义上多态设计：  对象向上转型 【对象向上造型】

```java
父类  多态对象 = new 子类();
```

角度1： 编译角度分析

```
自动转换
父类  对象  = new 子类();

//强制转换
子类 对象 = (子类) new 父类();
```

   

角度2： 运行角度分析

![](img\23.PNG)





总结：

```
多态对象只能访问父类的成员，当且仅当子类覆盖方法，执行子类的方法
```

##### 4.4.3 多态的必要条件【重点】

```
1. 继承，父类多个子类
2. 子类必须覆盖父类方法
3. 对象向上转型  父类  多态对象 = new 子类();
```

```java
package com.cl.homework;

public class Father {
	public int a = 10;
	
	public void eat() {
		System.out.println("爸爸吃一碗米饭");
	}
	
	public static void main(String[] args) {
		//多态 执行父类属性，子类覆盖的方法
		Father f = new Son();
		System.out.println(f.a);//10
		f.eat();//2碗
		
		//子类自己的
		Son s = new Son();
		System.out.println(s.a);//20
		
		//父类自己的
		Father f2 = new Father();
		System.out.println(f2.a);
	}
}
class Son  extends Father{
	public int a = 20;
	
	public void eat() {
		System.out.println("儿子吃2碗米饭");
	}
}
```



##### 4.4.4 多态的传参设计

> 多态使用在参数传递。

```java
public class USB {
	
	//设备名字
	private String name;

	public String getName() {
		return name;
	}

	public void setName(String name) {
		this.name = name;
	}
	public USB() {
		
	}
	public USB(String name) {
		super();
		this.name = name;
	}
	
	public void work() {
		System.out.println("设备工作运转");
	}
}

class KeyBoard extends USB{

	public KeyBoard() {
		super();
		// TODO Auto-generated constructor stub
	}

	public KeyBoard(String name) {
		super(name);
		// TODO Auto-generated constructor stub
	}
	@Override
	public void work() {
		System.out.println("键盘插入，库库输入.....");
	}
}

class Mouse extends USB{

	public Mouse() {
		super();
		// TODO Auto-generated constructor stub
	}

	public Mouse(String name) {
		super(name);
		// TODO Auto-generated constructor stub
	}
	@Override
	public void work() {
		System.out.println("鼠标插入，工作.....");
	}
}

class Fan extends USB{

	public Fan() {
		super();
		// TODO Auto-generated constructor stub
	}

	public Fan(String name) {
		super(name);
		// TODO Auto-generated constructor stub
	}
	@Override
	public void work() {
		System.out.println("风扇插入，呼呼吹");
	}
}

```

```java
package com.cl.oop.dt;

public class Programmer {
	
	//编码需要使用键盘，依赖键盘
//	public void code(KeyBoard b) {
//		System.out.println("程序员使用" + b.getName() + "编码");
//	}
//	
//	public void code(Mouse b) {
//		System.out.println("程序员使用" + b.getName() + "编码");
//	}
//	
//	public void code(Fan b) {
//		System.out.println("程序员使用" + b.getName() + "编码");
//	}
	
    //依赖关系
	public void code(USB b) {
		System.out.println("程序员使用" + b.getName() + "编码");
	}
	
	public static void main(String[] args) {
		new Programmer().code(new KeyBoard("阿米诺"));
	}
	
}

```

练习：

```
乐器
	Instrument
	乐器类型 乐器名
	
	行为  演奏
	
吉他  Guitar   表演吉他
钢琴  Piano    弹奏钢琴
小提琴  Violin  拉奏

演奏家 Player  
		表演 show(父类  对象){
			
		}
		
对象 周杰伦 
	表演 演奏钢琴...
```

##### 4.4.5  向下转型 

> 向上转型：  父类  父类对象 = new 子类()  ;   父类引用任何一个子类的实例化对象
>
> 向下转型:     子类  对象 = （子类）父类对象；  将多态对象强行转化为对应的子类

```java
s.goToSchool(new Bus("金龙牌", "白色"));

//向上转型
public void goToSchool(Vehicles v) {
	System.out.println(name + "准备去上学");
	System.out.println();
	v.run();
}

//去上学,依赖交通工具
	public void goToSchool(Vehicles v) {
		System.out.println(name + "准备去上学");
		//向下转型,强行将多态对象转换为子类
		if(v instanceof Bus) {
			Bus b = (Bus)v;
			System.out.println("线路：" + b.getRoute());	
			b.run();
		}
		else if(v instanceof Car) {
			Car c = (Car)v;
			System.out.println("车牌:" + c.getId());	
			c.run();
		}else {
			v.run();
		}		
}
```

向下转型判断

```java
变量 instanceof 类型 
```

true  变量是否是该类型，该类型子类类型

false 不是这个类型

instanceof仅限于有继承关系的判断

```java
public class TestInstanceOf {
	public static void main(String[] args) {
		Bus b = new Bus();
		Vehicles v = new Vehicles();		
		Vehicles v2 = new Bus();
		Student s = new Student();
		
		System.out.println(b instanceof Bus);
		
		System.out.println(b instanceof Vehicles);
		
		System.out.println(b instanceof Object);
					
		System.out.println(v instanceof Bus);
		
		System.out.println(v2 instanceof Bus);
		
		//System.out.println(s instanceof Bus);
		//System.out.println(b instanceof Car);
		
	}
}
```

#### 第五章 JAVA高级特性

> 高级修饰词： abstract   final   static 
>
> 接口
>
> 枚举
>
> 内部类 ： 匿名类 【jdk8+  Lambda】
>
> 设计模式 ： 工厂模型
>
> 异常处理



#### 5.1 abstract

> abstract：  抽象的。在JAVA中修饰难以描述清楚的，概念模糊，比较笼统的，不具体的事物。

##### 5.1.1 abstract修饰什么

1.类  抽象类

```java
public abstract class 类名{

}
```

2.方法  抽象方法

```java
public abstract  返回类型 方法名(参数) ;
```



##### 5.1.2 抽象类的特点

```
1. 抽象类抽象概念，无法描述，不可以实例化对象

2. 抽象类一定要有子类继承，具体的子类将抽象的概念继承

3. 子类继承抽象父类，必须重写所有抽象方法，否则该子类变成抽象类

4. 抽象父类一定要有构造方法，不是创建对象，而是子类调用的
```

示例代码：

```java
package com.cl.oop;
/**
 * 抽象类
 * @author Administrator
 *
 */
public abstract class Animal {
	private String name;
	private int age;
	
	public Animal() {
		
	}
	public Animal(String name, int age) {
		super();
		this.name = name;
		this.age = age;
	}
	public String getName() {
		return name;
	}
	public void setName(String name) {
		this.name = name;
	}
	public int getAge() {
		return age;
	}
	public void setAge(int age) {
		this.age = age;
	}
	@Override
	public String toString() {
		return "Animal [name=" + name + ", age=" + age + "]";
	}
	
	/**
	 * 抽象方法： 吃饭
	 */
	public abstract void eat() ;
	
	/**
	 * 抽象方法： 行走
	 */
	public abstract void run() ;
}

```



##### 5.1.3 抽象方法的特点

```
1. 抽象方法是无法讲清楚的行为，因此不能有方法体

2. 抽象方法所在的类一定是抽象类，抽象类里不一定全是抽象方法
```



> 总结： 抽象类用于修饰父类，强制子类继承，父类中抽象方法必须由子类覆盖
>
> 抽象父类不能实例化，因此必须创建子类对象，对象向上转型



#### 5.2 final

> 最后的，最终的，用于JAVA中修饰没有后续，没有后代，值不能改了。

##### 5.2.1 final修饰什么

```java
1. 修饰变量 
    private  final  int YEAR = 365;
	final double PI = 3.14;
2. 修饰方法 
	public final 返回类型 方法名(参数){
    
	}
3. 修饰类
   public final class 类名{
       
   }
```

##### 5.2.2 final修饰特点

```java
1. 修饰变量 ： 常量
    修饰属性 ： 必须给初始值
	修饰局部变量
	public class TestFinal {
	//private int a;
	private final int YEAR = 365;
	
	public void test() {
		final double PI;
		PI = 3.14;
		//PI = 3.15;
	}
}

2. 修饰方法 
	子类不能重写
3. 修饰类 
    不能有子类，最后的
    public final class Math { }

	public final class String{}
```

注意： final 和abstract不能一起修饰方法和类，不能共用



#### 5.3  static

> 静态的，类的，用于修饰的是不归属于某个个体对象的资源。
>
> 私家车   共享车



##### 5.3.1 static修饰什么

```java
1. 属性 【局部变量不能】 静态属性
   private static int a ;
2. 方法  静态方法
   public static void main(String[] args){
    
   }
3. 内部类 
    
   public class A{
       //静态内部类
       public static class B{
           
       }
       
   }
```



##### 5.3.2 静态属性的特点

> 静态属性内存在静态区，一份拷贝，归属于当前类，对象共享使用。
>
> 静态属性初始化时机 ： 类加载时【第一次使用类的时候】

![](img\24.PNG)

```java
package com.cl.oop;

public class TestStatic {
	
	//静态属性、 类属性
	public static int a ;
	
	//实例属性
	public int b ;
	
	public TestStatic() {
		a ++;
		b ++;
	}
		
	//静态方法
	public static void main(String[] args) {
		
	//	System.out.println(TestStatic.a);
		
		TestStatic t1 = new TestStatic();
		System.out.println(t1.a + "," + t1.b);
		
		TestStatic t2 = new TestStatic();
  		System.out.println(t2.a + "," + t2.b);
	}
	
	public static void test() {
		
	}
	//实例方法
	public  void test2() {
		//局部变量不能使用
		//static int i = 10;
	}
	//内部类
	static class B{
		
	}
	
}

```

##### 5.3.3 静态属性和实例属性区别[重点]

|            | 静态属性【类属性】  | 实例属性     |
| ---------- | ------------------- | ------------ |
| 内存       | 静态区              | 堆           |
| 拷贝       | 1份                 | 每个对象一份 |
| 初始化时机 | 加载类              | 创建对象     |
| 归属       | 归属类，对象共享    | 对象         |
| 调用方式   | 类.属性   对象.属性 | 对象.属性    |



##### 5.3.4  静态方法

```
归属于类的，因此 类.静态方法()

原则：
静态方法只能调用静态成员【静态属性、静态方法】
实例方法可以调用静态方法的
静态方法一旦调用实例成员，必须创建对象
```

示例代码：

```java
package com.cl.oop;

public class TestStatic2 {
	
	
	//静态属性、 类属性
	public static int a ;
	
	//实例属性
	public int b ;
	
	public void test1() {
		System.out.println(a);
		System.out.println(b);
	}
	public void test2() {
		test1();
		//实例方法可以调用静态的
		test3();
	}
	
	public static void test3() {
		//test2();
		System.out.println(a);
		//System.out.println(b);
		TestStatic2 t = new TestStatic2();
		System.out.println(t.b);
	}
	public static void test4() {
		test3();
	}
	
	public static void main(String[] args) {
		test4();
	}
}

```

##### 5.3.5  静态代码块

> 静态代码块用于初始化静态成员。

语法：

```java
static{
	//初始化...
}
```

特点：

```
1. 在类加载的时候执行
2. 只执行一次
3. 可以定义多个，按照声明顺序执行 
```

注意： 实例代码块 {}  ，跟对象执行，执行顺序 ： 静态代码块 1 > 实例代码块 n > 构造方法 n

```java
package com.cl.oop;

public class TestStatic3 {
	//实例代码块
	{
		System.out.println("实例代码块");
	}
	//构造
	public TestStatic3() {
		System.out.println("构造方法");
	}
	
//	static {
//		System.out.println("静态代码块2");
//	}
	//静态代码块
	static {
		System.out.println("静态代码块");
	}
	

	public static void main(String[] args) {
		new TestStatic3();
		new TestStatic3();
		
	}
}

```



##### 5.3.6  修饰符共用

1.不能共用的关键字

```java
abstract final    不能一起修饰类和方法
abstract private  不能一起修饰方法
abstract static   不能一起修饰方法 
```

2.可以共用的关键字

```java
final static     可以一起使用，一起修饰属性和方法

    静态常量 :  public static final int YEAR = 365;
			   public final static int YEAR = 365;

	静态方法，不能重写
        		public static final void test(){
        
    			}
```



#### 5.4 接口

> 接口，interface ，在JAVA中一种规则的指定，指定的规范，某种类型的标准化，满足该规范的类属于这种类型。
>
> 如 USB接口 【USB指定规范格式】 ，满足USB规范称之为USB设备。

##### 5.4.1 作用

```
1. 解决JAVA的单继承问题 【为了类多元化】
2. 设计与实现分离，设计师做接口的设计【what】，程序员具体用类实现【how】
3. 分工明确，职责解耦
```

##### 5.4.2 声明定义

```java
控制权限 interface 接口名{

	
}
```

注意：

权限： public ， 缺省

接口名：

```
1.首字母大写
2.字母 数字 _ $ ,数字不能开头
3.不能关键字，有含义
4.IUser   UserImpl
```



##### 5.4.3  接口的成员[重点]

```java
1. 属性 ：  公开的静态常量  public static final 

2. 方法 ：  公开的抽象方法  public abstract 
    
注意：
    1. 以上任何修饰词均可省略，默认也是该类型
    2. 接口的方法在JDK8+以后 修正，允许非抽象 
    3. 接口中没有构造
```



##### 5.4.4  接口的实现

```java
public class 实现类【子类】 extends 父类  implements 接口1,接口2...{

}
```

1. 实现多个接口同时，可以继承，先继承，后实现
2. 一个实现类可以多实现n个接口，隔开
3. 实现接口后，所有抽象方法都被获得，实现类必须覆盖所有的抽象方法，否则该类为抽象类
4. 属性： 接口名.静态常量 

示例代码

```java
/**
 * 武器接口
 * @author Administrator
 *
 */
public interface IWeapon {
	//属性:公开的静态常量
	public static final int POWER = 200;	
	int YEAR = 30;
	
	//方法:公开的抽象方法	
	public abstract void fire();
	
	void attack() ;
	
}


/**
 * 交通工具
 * @author Administrator
 *
 */
public interface IVehicles {
	
	void run();
}
   
/**
 * 父类
 * @author Administrator
 *
 */
public class Iron {

}
   
 /**
 * 坦克 单继承 多实现
 * @author Administrator
 *
 */
public class Tank extends Iron implements IWeapon,IVehicles{

	@Override
	public void run() {
		System.out.println("坦克行驶");
	}

	@Override
	public void fire() {
		System.out.println("坦克开火");
	}

	@Override
	public void attack() {
		System.out.println("坦克袭击敌人");
	}

}

public class TestTank {
	public static void main(String[] args) {
		Tank a = new Tank();
		a.fire();
		a.attack();
		a.run();
	}
}

```

练习：

```
定义USB接口  属性：设备版本 3.0  添加方法：工作

三种设备实现类： 
U盘
鼠标
键盘

程序员类 插入设备使用  设备工作
添加测试
```

##### 5.4.5  接口的多态

```
1. 接口要有多个实现类
2. 实现类必须覆盖接口中抽象方法
3. 向上转型  接口 多态变量 = new  实现类();
4. 变量 instanceof 接口 
5. 向下转型 实现类 对象 = （实现类）多态变量;
```

示例代码

```java
package com.cl.oop.usb;

public interface USB {
	
	double VERSION = 3.0;
	
	void work();

}
class U implements USB{

	@Override
	public void work() {
		System.out.println(USB.VERSION + "u盘正在工作");
	}
	
}

class Mouse implements USB{

	@Override
	public void work() {
		System.out.println(USB.VERSION + "鼠标正在工作");
	}
	
}

class KeyBoard implements USB{

	@Override
	public void work() {
		System.out.println(USB.VERSION + "键盘正在工作");
	}
	
	public void light() {
		System.out.println("键盘闪烁灯光");
	}
	
}
```

```java
package com.cl.oop.usb;

public class Programmer {
	
	//多态设计
	public void useTool(USB u) {
		System.out.println("程序员插入usb设备");
		//判断类型
		if(u instanceof KeyBoard) {
			u.work();
			//向下转型
            //KeyBoard k = (KeyBoard)u;
            //k.light();
			((KeyBoard) u).light();
		}else		
			u.work();
	}
	
	
	public static void main(String[] args) {
		new Programmer().useTool(new KeyBoard());
	}
}

```



##### 5.4.6  接口的接口关系

| 1    | 2    | 关系                           |
| ---- | ---- | ------------------------------ |
| 类   | 类   | 单继承（关联，依赖）   extends |
| 类   | 接口 | 多实现  implements             |
| 接口 | 接口 | 多继承  extends                |

示例代码

```java
public interface A extends B,C{

}

interface B{
	
}
interface C{
	
}
```



##### 5.4.7  接口和抽象类区别【重点】

相同点：

```
1. 都是抽象概念，都包含抽象方法
2. 都不能创建对象，不能实例化
```

区别：

|        | 抽象类             | 接口                   |
| ------ | ------------------ | ---------------------- |
|        | abstract class     | intreface              |
| 构造   | 有                 | 没有                   |
| 方法   | 抽象方法或普通方法 | 抽象方法               |
| 权限   | 属性方法的权限任意 | 属性方法权限必须public |
| 属性   | 任意               | 静态常量               |
| 类关系 | 单继承 extends     | 多实现 implements      |

练习：

```
 *    生物接口   呼吸 breath()
 *    
	 * 动物  IAnimal  eat()  sleep()
	  		人接口  think()
	  		学生类  study() 
	 * 植物   
 * 
 *         测试 
```



#### 5.5 枚举

> 枚举，一一的列举出来，一组固定的离散值。 限制住一组值范围。 
>
> 性别：男女    交通灯： 红 黄 绿    一年固定12月  ，四季 ，  上传文件类型【视频 音频 图片】，
>
> 上传头像固定图像格式【.png  .jpg  .gif 】

##### 5.5.1 作用

```
1.  增强代码的可读性，枚举类型，固定选择类型，不需要强行记录常量的值

2.  安全性增强，除去枚举之外的值无法使用的 

3.  耦合性降低，方便代码维护
```

##### 5.5.2 声明定义

```java
控制权限 enum  枚举名{

	
}
```

注意：

权限： public  缺省

枚举名： 同JAVA类名，XXType    Gender  

##### 5.5.3  枚举的成员

```java
控制权限 enum  枚举名{
	//列举枚举型常量值，隔开
	值1,值2,值3...;
	
}
```

##### 5.5.4  枚举的调用

```
枚举名.枚举常量
```

示例代码

```java
public enum TrafficType {
	
	RED,GREEN,YELLOW;
}


public class TrafficSystem {
	
	//交通灯颜色
	private TrafficType color;
	
	
	//切换灯的颜色
	public TrafficType change(TrafficType curr) {
		
		switch (curr) {
		case RED:	color = TrafficType.GREEN;		
			break;
		case GREEN:	color = TrafficType.YELLOW;			
			break;
		case YELLOW: color = TrafficType.RED;				
			break;		
		}
		return color;
	}


	public TrafficType getColor() {
		return color;
	}


	public void setColor(TrafficType color) {
		this.color = color;
	}
	
}

public class Test {
	public static void main(String[] args) {
		TrafficSystem s = new TrafficSystem();
		s.setColor(TrafficType.RED);
		while(true) {
			//3秒
			try {
				Thread.sleep(3000);
			} catch (InterruptedException e) {
				// TODO Auto-generated catch block
				e.printStackTrace();
			}
			System.out.println(s.change(s.getColor()));
		}	
	}
}
```



#### 5.6 工厂模型

> 最常用的设计模式之一。工厂模型对象创建型的设计模式。

工厂模型对象类型限制： 枚举

```java
public enum ShoesType {
	
	NIKE,ANTA,ADDI;
}

```

多态设计

```java
public interface Shoes {
	
	//鞋子生产制造
	void make();
}

class Nike implements Shoes{

	@Override
	public void make() {
		System.out.println("nike鞋子生产制造");
	}
	
}
class Anta implements Shoes{

	@Override
	public void make() {
		System.out.println("安踏鞋子生产制造");
	}
	
}

class Addi implements Shoes{

	@Override
	public void make() {
		System.out.println("阿迪鞋子生产制造");
	}
	
}
```

工厂类： 根据需要返回类型的对象

```java
public class ShoesFactory {
	//多态设计
	public static Shoes shoe;
	
	public static Shoes getShoes(ShoesType type) {
		switch (type) {
		case NIKE:
			shoe = new Nike();
			break;
		case ANTA:
			shoe = new Anta();
			break;
		case ADDI:
			shoe = new Addi();
			break;
		}
		return shoe;
	}
}
```

测试

```java
public class TestShoes {
	public static void main(String[] args) {
		ShoesFactory.getShoes(ShoesType.NIKE).make();
	}
}

```



#### 5.7 内部类【了解】

> 类里定义的类，称之为内部类。
>



##### 5.7.1 作用

```
1.形成闭包
2.完善多重继承
```

##### 5.7.2 声明定义                                                                                                               

```
全局内部类 ： 内部类写外部类里，方法外
		静态内部类  
		实例内部类
局部内部类 ： 内部类写在方法里
```

示例代码

```java
public class A {
	
	public int i = 10;
	//静态内部类
	public static class B{
		public int j = 20;
	}
	//实例内部类
	protected class C{
		public int k = 30;
	}
	
	public void test() {
		//局部内部类
		class D{
			int m = 40;
		}
		
	}
}
```



##### 5.7.3  内部类使用

> 内部类的使用取决于所在的外部类，全名 ： 外部类.内部类

```java
public class TestInner {
	public static void main(String[] args) {
		//System.out.println(A.B.j);
		
		//A.B b = new A.B();
		//System.out.println(b.j);
		
//		A.C c = new A().new C();
//		System.out.println(c.k);
		
		new A().test();
		
	}
}
```

##### 5.7.4  匿名内部类

> JAVA中特殊的内部类，没有名字的类。

作用：

```
简化子类或实现类的写法
```

语法规则:

```java
接口  变量 =  new 接口(){
		//当前接口的实现类类体
};

父类  变量 =  new 父类(){

};
```

实例：

```java
public interface IDrink {
	
	void taste();
}


public class TestInner2 {
	public static void main(String[] args) {
		//匿名内部类
		IDrink coffee = new IDrink() {
			@Override
			public void taste() {
				System.out.println("咖啡真好喝");
			}			
		};		
		coffee.taste();

		//jdk8+ Lambda表达式
		IDrink milk = () -> System.out.println("牛奶丝滑");
		milk.taste();
	}
}

```

jdk8+ lambda 表达式： 用于生成匿名内部类

```java
接口 变量 = () -> {};
```

1.lambda 仅限于函数式接口【只有一个抽象方法】

2.()覆盖的方法的参数,只有一个参数，可以省略()

3.{} 覆盖的方法体，{} 只有一句话可以省略，当方法有返回值，return 可以省略

示例代码

```java
public interface IPerson {	
	int sum(int a,int b);
}
public class TestPerson {
	public static void main(String[] args) {
		IPerson p = (a,b) -> a + b;		
		System.out.println(p.sum(1,2));
		
	}
}
```



#### 第六章 JAVA的API

> API : application programming interface  应用程序接口，JAVA的第三方帮助文档。
>
> 通过API学习，深入了解JAVA 接口，类，方法设计....
>
> java.lang包  核心包    异常类   String   StringBuilder  Math Object   包装类   线程 ....
>
> java.util包   工具包      集合类  Arrays   Random   Date ...
>
> java.io包    文件输入输出包  
>
> java.awt     图形界面   JPanel    JButton   
>
> java.sql包   数据库衔接 



#### 6.1 异常类

> 程序中出现的问题，统称为异常 Throwable
>
> 异常：程序员因疏忽导致的程序的问题，程序员可以解决的， Exception 
>
> 错误：程序中出现内存故障，系统故障，JVM，堆栈溢出，程序员无法解决， Error

```java
public class Exception extends Throwable {

}

public class Error extends Throwable {

}
```

##### 6.1.1 Exception 分类

```java
编译时异常  编译程序的时候异常，不解决无法编译
		 IOException  IO异常
		 FileNotFoundException  文件未找到异常
		 SQLException   数据库异常
		 ...

运行时异常 RuntimeException  
编译通过，运行抛出异常
		 ArrayIndexOutOfBoundsException  数组下标越界异常
		 NullPointerException   空引用异常
		 ClassCastException  类型转换异常
		 NumberFormatException  数字转换异常
		 ArithmeticException  数学异常
		 ...
```

示例代码

编译时异常

```java
while(true) {
			System.out.println("现在时间:" + new Date());			
			try {
				Thread.sleep(1000);
			} catch (InterruptedException e) {
				// TODO Auto-generated catch block
				e.printStackTrace();
			}
		}
```

运行时异常

```java
package com.cl.lang.exception;
/**
 *  运行时异常
 * @author Administrator
 *
 */
public class TestException2 {
	public static void main(String[] args) {
		//数学异常
		//System.out.println(10 / 0);
		
		//数组越界
//		int[] a = new int[4];
//		System.out.println(a[4]);
		
		Student s = new Student();
		//空引用
//		Dog dog = new Dog();
//		dog.name = "大黄";
//		System.out.println(s.dog.name);
		
		//类型转换异常，多态强转
		//Pupil p = (Pupil)s;
		
		String count = "a";
		//数字转换异常
		System.out.println(Integer.parseInt(count) * 20);
	}
}

```

##### 6.1.2 异常的发生

```
1. 程序意外终止，提示错误信息，整个系统崩塌
2. 程序控制权力丢失，返给操作系统
3. 系统内存分配的资源可能泄露
```

##### 6.1.3 异常的捕获机制

> 对于程序中有可能出现异常的代码都需要捕获，捕获机制： try  catch  finally
>
> try ： 监视器   ，监控代码，一旦代码发生异常，抛出异常对象
>
> catch : 捕获处理器， 将try块中抛出异常捕获住，并将其处理【提示当前开发者】
>
> finally ： 无条件语句块， 不管程序是否有异常，无条件运行。可有可无，一旦有，必须执行。

###### 1.语法规则

```java
try{
    //有可能发生异常的代码块，抛出一个异常对象
}catch(异常类型1  变量名) {
	//捕获对应类型的异常
    //提示： 打印异常信息栈 错误类型 信息  错误行
    e.printStackTrace();
}catch(异常类型2  变量名) {
			
}...
catch(异常根类  变量名){
    
}
[
   finally{
       //无条件执行的语句
       //资源清理操作
       
   } 
    
]
```

注意：

1, try块不能单独出现，配合catch或finally块

2, try块对应多个catch，catch块异常类型对应的捕获try抛出的对象，多个catch并列，捕获不同类型的

3, catch 从上向下依次执行，找到匹配的，catch(Exception e){} 必须置于最下方

4, finally可有可无，一旦有，必须执行语句，除非退出虚拟机,finally之前执行return，会执行，在return前执行

示例代码

```java
public class TestException2 {
	public static void main(String[] args) {
		//数学异常
		int a = 10, b = 10;
		try {
			System.out.println(a / b);
			//数组越界
			int[] m = new int[4];
			System.out.println(m[4]);
			
			String count = "a";
			//数字转换异常
			System.out.println(Integer.parseInt(count) * 20);
			
			
		}catch(ArithmeticException e) {
			//打印异常堆栈信息
			e.printStackTrace();
			//System.out.println("注意：发生了数学异常");
		}catch(ArrayIndexOutOfBoundsException e) {
			//System.out.println("注意：发生了越界异常");
			e.printStackTrace();
		}catch(Exception e) {
			System.out.println("注意：发生了异常");
		}

		
		System.out.println("哈哈哈");
		
		Student s = new Student();
		//空引用
//		Dog dog = new Dog();
//		dog.name = "大黄";
//		System.out.println(s.dog.name);
		
		//类型转换异常，多态强转
		//Pupil p = (Pupil)s;	
	}
}
```

###### 2.捕获流程

![](img\25.PNG)

捕获流程示例代码：

```java
public class TestException4 {
	public static void main(String[] args) {
		
		try {
			System.out.println(10 / 0);
			System.out.println("继续");
		} 
		catch (ArithmeticException e) {			
			System.out.println("发生数学异常");
			//return;
			System.exit(0);
		}	
		catch (Exception e) {		
			System.out.println("发生异常");
		}finally {
			System.out.println("资源回收清理");
		}
		
		System.out.println("执行我么?");
	}
}
```

特殊情况： 程序中没有catch,异常吗，没有捕获发生，finally无条件执行

```java
try{
	
}
finally{

}
```

示例代码：

```java
public class TestException4 {
	public static void main(String[] args) {
		
		try {
			System.out.println(10 / 0);
			System.out.println("继续");
	    }	
		finally {
			System.out.println("资源回收清理");
		}
		
		System.out.println("执行我么?");
	}
}
// 资源回收清理
```



##### 6.1.4 异常的抛出【重点】

> throws    当方法中出现异常时，不解决异常，向外抛出
>
> throw      在方法中手动构建一个异常，抛出



###### 1. throws 

> 方法内部出现异常，不解决异常，程序员向外抛出异常类型，让方法的调用位置解决
>
> 当方法不解决，可以继续向外抛出，直到抛给虚拟机

语法规则：

```java
控制权限 修饰符 返回值 方法名(参数) throws NullPointerException,Exception {
	
}
```

示例代码

```java
package com.cl.lang.exception;

import java.io.FileNotFoundException;
import java.io.FileReader;

public class TestThrows {
	
	public static void a() throws FileNotFoundException,NullPointerException {
		//编译时异常
		FileReader fr = new FileReader("F:\\1.txt");
		
		String s = null;
		System.out.println(s.length());
	}
	
	public static void b() throws FileNotFoundException, NullPointerException {
		a();
	}
	public static void main(String[] args) {
		try {
			b();
		} catch (FileNotFoundException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		} catch (NullPointerException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
	}
}

```

注意： 

1.通常，向外抛出的是编译时异常比较多。

2.方法抛出异常： 方法重写，子类不能比父类、接口抛出类型更多异常。

```java
public abstract class Person {
	
	public abstract void eat() ; 

}

class Teacher extends Person{
	
	public void eat() throws Exception{
		
	}
	
}

public abstract class Person {
	
	public abstract void eat() ; 

}

interface Animal{
	
	void sleep() throws ArrayIndexOutOfBoundsException;
	
}

class Teacher implements Animal{
	
//	public void eat() throws Exception{
//		
//	}
	
	public void sleep() throws Exception{
		
	}
	
}
```



###### 2. throw

> 在方法中，手动创建一个异常对象，抛出去【生成一个异常】，使用throw
>
> 制定异常出现： 出现不符合逻辑或系统需求，JAVA中没有对应的异常类型 

语法规则：

```java
控制权限 修饰符 返回值 方法名(参数) throws AgeException {
	
    //1. 创建一个异常对象
    //Exception e = new Exception("错误信息");
    AgeException e = new AgeException("年龄不合法");
    
    //2. 抛出,一旦抛出，相当于有异常存在
    throw e;
    
    
}
```

区别：

```
throws
	方法内异常不解决，向外抛出，抛出异常类型 
throw
	方法内创建异常对象，抛出，抛出异常对象
		
```

示例代码:

```java
package com.cl.lang.exception;
public class AgeException extends Exception{

	public AgeException() {
		super();
		// TODO Auto-generated constructor stub
	}

	public AgeException(String message) {
		super(message);
		// TODO Auto-generated constructor stub
	}
	
}
public class Doctor {
	
	public static void checkAge(int age) throws AgeException {
		
		if(age >= 1) {
			System.out.println("年龄合法，录入成功");
		}else {
			//制造异常
			AgeException e = new AgeException("年龄非法啦，录入的必须合法");
			//抛出
			throw e;
		}
		System.out.println("系统其它板块");	
	}
	
	public static void main(String[] args) {
		try {
			checkAge(9);
		} catch (AgeException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}finally {
			
		}		
		System.out.println("codeddddddd");
	}
}

```



##### 6.1.5 自定义异常类

```java
public class AgeException extends Exception{

	public AgeException() {
		super();
		// TODO Auto-generated constructor stub
	}

	public AgeException(String message) {
		super(message);
		// TODO Auto-generated constructor stub
	}
	
}
```

关键字

try  catch finally   throw  throws

类型

Throwable   Exception  RuntimeException ....



#### 6.2 String

> 字符串，不可变的字符串，定义后不能改变的。

```java
public final class String
    implements java.io.Serializable, Comparable<String>, CharSequence {
    
}
```

##### 6.2.1 String的分类和内存

```
String定义后不能改变
String分为两种：
		字符串变量 str
		字符串常量 "abc"
		
		String str = “abc”;

注意： 字符串常量和变量皆为对象。
```

堆栈图：

![](img\26.png)

示例代码

```java
public class TestString {
	public static void main(String[] args) {
		
		int a = 10;
		String str = "abc";
		String str2 = "abc";			
		String str3 = new String("abc");
		
		System.out.println(str == str2);	//true
		System.out.println(str2 == str3);	//false
		
		//str = "abcd";		
		//System.out.println(str.length());		
		//System.out.println("abc".length());
	}
}
```

```java
public class TestString2 {
	public static void main(String[] args) {
		
		
		String str = "abc";
		String str2 = "abcd";			
		String str3 = new String("abc");
		
		//以上三行代码，创建几个对象
		// 3个对象
	}
}
```



##### 6.2.2 String的创建

```java
1. 引用常量对象

String 变量 = "abc";


2.创建对象
new String();

new String("abc");

new String(char[] c);

new String(StringBuilder b);


```

示例代码

```java
public class TestString3 {
	public static void main(String[] args) {
		String s1 = "abc";
		
		String s2 = new String();
		
		String s3 = new String("abcd");
		
		char [] c = {'我','爱','中','国'};
		
		String s4 = new String(c);
		System.out.println(s4);
			
	}
}
```



##### 6.2.3 String的方法

> 字符串有下标，从0开始

| 方法名                 | 含义                                                | 参数   | 返回值   |
| ---------------------- | --------------------------------------------------- | ------ | -------- |
| length()               | 返回字符串内容的长度，统计字符个数，汉字按1字符     |        | int      |
| charAt(index)          | 返回对应下标上的字符                                | int    | char     |
| toCharArray()          | 将字符串转化为字符数组                              |        | char[]   |
| substring(int index)   | 截取，从起始位置截取最后 [index,length()-1]         |        | String   |
| substring(int s,int e) | 截取，从起始位置截取到结束的前一个位置 [s,e)        |        | String   |
| contains(String)       | 判断字符串是否存在于原串                            |        | Boolean  |
| indexOf(子串)          | 查找，子串在原串中第一次出现的位置，找不到返回-1    | String | int      |
| lastIndexOf(子串)      | 查找，子串在原串中最后次出现的位置                  | String | int      |
| equals(string)         | 判断两个串值是否相等，地址 ==                       |        | boolean  |
| compareTo(String s)    | 比较两个字符串字典顺序   0  正  负                  |        | int      |
| split(String )         | 根据切割内容将串切成一段段,切割符号很多时候需要转义 |        | String[] |
| replace(old,new)       | 替换                                                |        |          |
| endsWith(string)       | 判断是否是..结尾，判断文件类型                      |        | boolean  |
| trim()                 | 自动去掉字符串两侧空格，删除多余空格                |        |          |
| matches(正则表达式)    | 检测字符串是否匹配模式                              | 表达式 | boolean  |

练习1： 定义一个方法，传入字符串，返回该串的逆置串   【charAt  length】

```java
	/**
	 * 定义一个方法，传入字符串，返回该串的逆置串  
	 */
	public static String getReverse(String str) {
		String s = "";
		for (int i = str.length() - 1; i >= 0; i--) {
			s += str.charAt(i);
		}
		
		return s;
	}
```

练习2 ： 字符串中哪个字母出现的次数最多，多少次 【charAt  length】

```java
/**
	 * 字符串中哪个字母出现的次数最多，多少次
	 */
	public static String getCount(String str) {
		char c = ' ';
		int max = 0;
		//char[] cc = str.toCharArray();
		
		for (int i = 0; i < str.length(); i++) {
			int count = 1;
			for (int j = i + 1; j < str.length(); j++) {
				if(str.charAt(i) == str.charAt(j)) {
					count ++;
				}
			}
			if(max < count) {
				max = count ;
				c = str.charAt(i);

			}		
		}		
		return "出现最多的是:" + c + ",出现：" + max + "次";
}	
```

练习3：写一个方法传入串ip地址，隐藏IP ： 192.168.23.56     192.168.23.*【截取substring和查找lastIndexOf】

```java
/**
	 * 写一个方法传入串ip地址，隐藏IP ： 192.168.23.56     192.168.23.*【截取和查找】
	 */
	
	public static String hideIp(String ip) {
		int index = ip.lastIndexOf(".");
		String sub = ip.substring(0, index) ;
		return sub + ".*";
}
```

示例代码：

```java
public class TestString7 {
	public static void main(String[] args) {
		String s1 = "abc";
		String s2 = "abc";
		String s3 = new String("abc");
		
		System.out.println(s1 == s2);
		System.out.println(s3 == s2);
		
		System.out.println(s1.equals(s2));
		System.out.println(s2.equals(s3));
		System.out.println(s1.equals(s3));
	}
}
```

练习4 ： 给定字符串数组 {"cat","boy","apple","dog","monkey"} 按照字典顺序排列【compareTo()】

```java
		//给定字符串数组 {"cat","boy","apple","dog","monkey"} 按照字典顺序排列
		String [] arr =  {"cat","boy","apple","dog","monkey"};
//		for (int i = 1; i < arr.length; i++) {
//			for (int j = 0; j < arr.length - i ; j++) {
//				if(arr[j].compareTo(arr[j + 1]) > 0) {
//					String temp = arr[j];
//					arr[j] = arr[j + 1];
//					arr[j + 1] = temp;
//				}
//			}
//		}
		
		Arrays.sort(arr);
		System.out.println(Arrays.toString(arr));
```

练习5 ： 分割split()

```java
	public static void main(String[] args) {
//		String citys = "北京|上海|大连|本溪";
//		
//		//切割
//		String[] c = citys.split("\\|");
//		
//		for (int i = 0; i < c.length; i++) {
//			System.out.println(c[i]);
//		}
		
		System.out.println(hideIp("192.168.23.56"));
	}



	/**
	 * 192.168.23.56 
	 */
	public static String hideIp(String ip) {
		//使用符号分割
		String[] ips = ip.split("\\.");
		ips[ips.length - 1] = "*";
		//将数组使用符号连接
		return String.join(".", ips);
	}
```

正则表达式：

> 正则表达式理解为指定的格式规范。

规范：

1.分隔符

```
^  表达式开始
$  表达式结束
```



2.内容

```
abc  匹配的就是abc

[abc] 任意选

[a-z] a-z任选
[A-Z]
[0-9]    \d
[a-zA-Z0-9_]  \w



```

3.位数

```
{n}  n位

{n,m} n~m位

{n,} n位以上
```





示例代码

```java
// QQ 

//^[1-9]{1}[0-9]{4,}$
    
public class TestPattern {
	
	public static void main(String[] args) {
		String qq = "1234";
		System.out.println(qq.matches("^[1-9]\\d{4,}$"));// \d [0-9]
		
		//检测手机号
		System.out.println("13610943167".matches("^1\\d{10}$"));
		//大连座机
		System.out.println("0411-88068025".matches("^0411-[0-9]{8}$"));
		//账户名  字母 数字 _ 构成，8-12位之间
		System.out.println("ys9988654".matches("^\\w{8,12}$"));
		//身份证 18位数字 17位X
		
		System.out.println("21055345675643234X".matches("^\\d{17}[0-9X]$"));
		
	}

}
```



#### 6.3 可变字符串

> 可变字符串指的是字符串的缓冲，在一定范围内，将字符串进行改变【增删改】。
>
> 可变字符串的本质： 数组扩容
>
> StringBuilder  线程不安全，不同步的，多线程的，效率高，速度块，推荐
>
> StringBuffer  线程安全，单线程，效率低



##### 6.3.1 可变字符串的创建

```java
new StringBuilder() ; // 缓冲区空间大小16字符  

new StringBuilder("abc") ; // 缓冲区空间大小19字符 

new StringBuilder(25); // 缓冲区空间大小25字符  
```



##### 6.3.2 可变字符串方法

| 方法名                  | 含义                           | 参数 | 返回值        |
| ----------------------- | ------------------------------ | ---- | ------------- |
| append(内容)            | 返回可变字符串，尾部追加字符串 |      | StringBuilder |
| length()                | 字符串内容的长度               |      | int           |
| capacity()              | 缓冲区容量大小                 |      | int           |
| insert(下标，内容)      | 在下标前面插入内容             |      | StringBuilder |
| delete(s,e)             | 从s删除e-1                     |      | StringBuilder |
| deleteCharAt(index)     | 删除对应下标字符               |      | StringBuilder |
| setCharAt（index,内容） | 将对应下标字符修改             |      |               |
| reverse()               | 字符串翻转                     |      |               |

练习：使用可变字符串完成是否回文串

```java
	public static boolean isHuiWen(String str) {
		
		//思路3 转化可变  reverse() 
		StringBuilder bul = new StringBuilder(str);
		if(bul.reverse().toString().equals(str)) {
			return true;
		}
		return false;
        
    }
```





#### 6.4 Math

> 数学相关的API，是final修饰终端类。私有化构造，Math类中所有的成员：属性，方法都是静态。

```java
public final class Math {

    /**
     * Don't let anyone instantiate this class.
     */
    private Math() {}
    
 }
```

##### 6.4.1 属性

```
Math.PI 圆周率

Math.E  自然底数
```



##### 6.4.2 方法

| 方法名      | 含义                                  | 参数   | 返回值     |
| ----------- | ------------------------------------- | ------ | ---------- |
| abs(参数)   | 返回该数的绝对值                      |        | int/double |
| ceil(参数)  | 返回比当前参数稍大的整数 【向上取整】 | double | double     |
| floor(参数) | 返回比当前参数稍小的整数 【向下取整】 | double | double     |
| max(a,b)    | 返回a和b的最大值                      |        |            |
| min(a,b)    |                                       |        |            |
| pow(a,b)    | a的b次幂                              |        | double     |
| sqrt(a)     | a的平方根                             |        |            |
| round(）    | 四舍五入 , Math.floor(a + 0.5)        |        |            |
| random()    | 随机数 [0,1)  随机小数                |        | double     |

随机数公式：[a,b]

```java
(int)((b - a + 1) * Math.random() + a)
```

示例代码

```java
package com.cl.math;

public class TestMath1 {
	public static void main(String[] args) {
		System.out.println(Math.PI);
		
		System.out.println(Math.E);
		
		System.out.println(Math.abs(-9));
		
		System.out.println(Math.ceil(4.21));
		
		System.out.println(Math.ceil(4));
		
		System.out.println(Math.ceil(-3.98));
		
		System.out.println(Math.ceil(-4.01));
		
		
		System.out.println(Math.floor(3.98));
		
		System.out.println(Math.floor(3));
		
		System.out.println(Math.floor(-3.98));
		
		System.out.println(Math.max(10, 8));
		
		System.out.println(Math.pow(2, 3));
		
		System.out.println(Math.sqrt(25));
		
		System.out.println(Math.round(25.6789));
		
		System.out.println(Math.round(2.5));
		
		System.out.println(Math.round(-2.5));
		// Math.floor(a + 0.5)
		System.out.println(Math.round(-2.6));// -2.1
		
		
		System.out.println(Math.random());
		
		System.out.println((int)((9) * Math.random() + 1));
	}
}

```



#### 6.5 包装类

> 为了面向对象的设计，JAVA将八个基本数据类型进行类型封装，将八个基本数据类型封装成一个个类。变量被变成对象。

| 基本数据类型 | 包装类    |
| ------------ | --------- |
| byte         | Byte      |
| short        | Short     |
| int          | Integer   |
| long         | Long      |
| float        | Float     |
| double       | Double    |
| char         | Character |
| boolean      | Boolean   |



##### 6.5.1 装箱和拆箱

> 装箱： 将基本数据类型转化为包装类型
>
> 拆箱： 将包装类型转化为基本数据类型

###### jdk5+ 支持自动

手动装箱

```java
new Integer(int i);
```

自动装箱

```java
Integer a = 20;
Double d = 20.0; //注意,自动装箱不执行类型自动转换，必须完全匹配
```

手动拆箱

```java
Integer a = new Integer(20);
//手动拆箱
int  i = a.intValue();		
```

自动拆箱

```java
//自动拆箱
int j = a;	
double d  = a;
```

面试考题：

```java
public class TestWrapper3 {
	public static void main(String[] args) {
		//堆开辟两个
		//Integer a = new Integer(10);		
		//Integer b = new Integer(10);
		
		//10 存储在常量池
		//Integer a = 10;
		//Integer b = 10;
				
		//128以上各自开辟
		Integer a = 128;
		Integer b = 128;
		
		
		System.out.println(a == b);
		
	}
}
```



##### 6.5.2 包装类型和String的转换

string转为基本/包装

```java
Integer.parseInt(string)

Double.parseDouble(string)
    
注意： 当转换出现问题时，发生 NumberFormatException
    
    
        String s = "10";
		//int a = (int)s;
		//System.out.println(s * 10);
		
		int a = Integer.parseInt(s);
		
		System.out.println(a * 10);
		
		String s2 = "12.56";
		double d = Double.parseDouble(s2);
		
		System.out.println(d + 10);//精度 
```

基本/包装转换为string

```java
拼接  + ""
String.valueOf();
toString()


public class TestWrapper5 {
	public static void main(String[] args) {
		int a = 10;
		
		//toString()
		//Integer i = a;
		//System.out.println(i.toString());
		
		//拼接
		System.out.println(a + "");
		
		
		//String.valueOf()
		
		System.out.println(String.valueOf(a));
	}
}


```



#### 6.6 Object

> Object是所有的类父类，作为类体系的根类。  父类：根类  超类  基类 

##### 6.6.1 Object的方法

| 方法名     | 含义                                                | 参数 | 返回值  |
| ---------- | --------------------------------------------------- | ---- | ------- |
| finalize() | 垃圾回收方法，可以覆盖实现资源清理，JVM调用         |      |         |
| hashCode() | 返回每个对象的哈希码，每个对象唯一的哈希值          |      | int     |
| toString() | 打印对象信息：当前类名@哈希码十六进制，建议子类覆盖 |      |         |
| equals()   | 默认判断对象地址是否相等，重写，实现想要的比较机制  |      | boolean |

面试考题：

```java
final  finally  finalize()

final   关键字 最终的修饰 类 方法 变量 
    
finally 语句块 {} 异常处理机制 无条件执行块
    
finalize() 方法，子类覆盖该方法，做垃圾回收    
```

equlas重写：

```java
package com.cl.object;

public class Student {
	
	private String name;
	
	private int age;
	
	@Override
	public boolean equals(Object obj) {
		//向下转型
		Student s = (Student)obj;
		if(this.name.equals(s.name) && this.age == s.age) {
			return true;
		}
		return false;
	}
	public Student() {
		
	}
	public Student(String name, int age) {
		super();
		this.name = name;
		this.age = age;
	}

	@Override
	public String toString() {
		return "Student [name=" + name + ", age=" + age + "]";
	}
	
}


package com.cl.object;

public class TestObject {
	public static void main(String[] args) {
		Student s1 = new Student("jack",20);
		Student s2 = new Student("jack",20);
		
		System.out.println(s1.equals(s2));
			
		//Student s3 = s2;
	//	System.out.println(s1.hashCode());
	//	System.out.println(s2.hashCode());
		
	//	System.out.println(s1 == s2);
		
	//	System.out.println(s3.hashCode());
		
	//	System.out.println(s1.toString());
	}
}

```



#### 6.7 集合 java.util [重点]

> 集合： 数据集合，存储数据的介质
>
> 1. 集合是类型，需要创建对象
> 2. 集合相对于数组，大小可变的
> 3. 集合的数据类型广泛的，但是也可以限制类型。



##### 6.7.1 集合体系结构

体系1 ：存储数值

```java
Iterator接口
	Collection 上层接口
		
		List子接口 :  有下标，元素可以重复
			实现类：
			ArrayList    线性集合，线性存储，元素挨着的，方便检索不方便更新元素 。 线程不安全，不同步，效率高
			LinkedList   链式集合，链式存储，通过元素地址链接，方便更新，不方便查找。线程不安全，不同步，效率高
			Vector       线程安全，同步的，单线程，效率低

		Set子接口  :  没有下标，元素不保证顺序，不能重复
            实现类：
            
            HashSet  不能重复，没有顺序
            TreeSet  不能重复，自动排序 
```



体系2： 存储键值对

```
Map 上层接口

		实现类
		
			HashMap  线程不安全，允许null值
			Hashtable 线程安全，不允许null值
			TreeMap  带排序
```



##### 6.7.2  ArrayList

> 线性集合，底层数据结构是线性数组。有下标。



###### 创建集合对象

```java
new ArrayList();  //默认空间大小10

new ArrayList(Collection c);

new ArrayList(int) ; //给多少开辟多大空间
```

注意：

1. 集合默认的数据类型Object



###### 集合方法【重点】

| 方法名          | 含义               | 参数       | 返回值  |
| --------------- | ------------------ | ---------- | ------- |
| add(元素)       | 尾部添加元素       | E 集合类型 | boolean |
| add(下标，元素) | 在下标前面插入元素 |            |         |
| remove(下标)    | 删除下标对应元素   |            |         |
| remove(元素)    | 删除元素           |            |         |
| clear()         | 清空集合           |            |         |
| size()          | 集合大小           |            |         |
| get(下标)       | 获取对应下标的元素 |            |         |
| set(下标，元素) | 修改对应下标的元素 |            |         |
| contains()      |                    |            |         |
| indexOf()       |                    |            |         |
| lastIndexOf()   |                    |            |         |

注意： 删除元素默认数字按下标处理，元素需要包装对象

示例代码

```java
package com.cl.util;

import java.util.ArrayList;

public class TestList1 {
	public static void main(String[] args) {
		ArrayList<Object> list = new ArrayList<Object>(); 
		//添加元素
		list.add("jack");// Object o = "jack";
		
		list.add(10); // Object o = 10; //自动装箱
		
		list.add(20.0);
		
		//插入
		list.add(1, 80);
		
		//删除元素
		list.remove(0);		
		//list.remove(new Integer(80));
		
		//System.out.println(list);
		//System.out.println(list.size());
		
		//修改
		list.set(list.size() - 1, 90);
		
		//遍历集合
//		for (int i = 0; i < list.size(); i++) {
//			System.out.println(list.get(i));
//		}
		
		for (Object o : list) {
			System.out.println(o);
		}
		
		//System.out.println(list.get(list.size()));
	}
}

```



##### 6.7.3 HashSet 

> Set的实现类，底层数据结构： 哈希表
>
> 集合特点： 无下标，不能保证顺序的，不能重复
>
> 不同步，不安全，效率高



###### 创建集合对象

```java
new HashSet();

new HashSet(Collection c);
```

###### 集合方法

| 方法名                                                    | 含义                 | 参数       | 返回值        |
| --------------------------------------------------------- | -------------------- | ---------- | ------------- |
| add(元素)                                                 | 添加元素             | E 集合类型 | boolean       |
| size()                                                    | 集合大小             |            |               |
| remove(元素)                                              | 删除对应元素         |            |               |
| **[iterator](../../java/util/HashSet.html#iterator())**() | 返回当前集合的迭代器 |            | Iterator 接口 |



###### Iterator 接口

> 迭代器接口，集合顶级接口，Collection是他的子接口

方法

| 方法名    | 含义           | 参数 | 返回值  |
| --------- | -------------- | ---- | ------- |
| hasNext() | 判断是否有元素 |      | boolean |
| next()    | 获取一个元素   |      | T       |
| remove()  | 删除迭代器指定 |      |         |

示例代码

```java
public class TestSet {
	public static void main(String[] args) {
		HashSet<String> set = new HashSet<String>();
		
		set.add("jack");
		set.add("rose");
		set.add("tom");
		set.add("jack");
		
		//System.out.println(set.size());
		
		//set.remove("rose");
		//foreach 增强for遍历不能删除元素
//		for (String s : set) {
//			System.out.println(s);
//		}
		
		//迭代器
		
		//1 获得迭代器
		Iterator<String> it = set.iterator();
		
		//2 判断元素
		while(it.hasNext()) {
			//获取一个
			System.out.println(it.next());
		}		
	}
}
```

去重复：

面试题： 数组，如何去重，几种方式

int[] a = {10,43,56,10,77,34,43};

```
1. 数组法 ： 新建无重复数组，遍历数组，不重复的存入

2. 集合
			1. HashSet 里  自动去重 迭代
			
			2. ArrayList  contains()
			
3. JDK 8 +  Stream 去重 distinct
```



两个数组 合并，去重，排序

```java
public class TestSet {
	public static void main(String[] args) {
		Integer [] a = {12,3,5,7,3};
		Integer [] b = {2,81,6,3,9};
		
		TreeSet<Integer> set = new TreeSet<Integer>();
			
		set.addAll(Arrays.asList(a));
		set.addAll(Arrays.asList(b));
		
		
		//List集合
		//排序
		//Collections.sort(set);
		
		System.out.println(set);
		
	}
}
```

数组，将其中的0去除 Integer [] a = {0,12,3,5,7,0,3,0};

```java
1. 新建数组， 统计0个数 
package com.cl.util;

import java.util.ArrayList;
import java.util.Arrays;
import java.util.Iterator;
import java.util.List;

public class TestList {
	public static void main(String[] args) {
		
		 Integer [] a = {0,12,3,5,7,0,3,0};		 
		 //思路1
//		 int count = 0;		 
//		 for (int i = 0; i < a.length; i++) {
//			if(a[i] == 0) {
//				count ++;
//			}
//		}
//		 int [] b = new int[a.length - count];
//		 int index = 0;
//		 for (int i = 0; i < a.length; i++) {
//				if(a[i] != 0) {
//					b[index ++] = a[i];
//				}
//		 }
//		 System.out.println(Arrays.toString(b));
		 
		 //思路2
		
		 
//		 for (int i = 0; i < list.size(); i++) {
//			if(list.get(i) == 0) {
//				list.remove(i);
//			}
//		 }
//		 List<Integer> list = new ArrayList<Integer>();
//		 list.addAll(Arrays.asList(a));
//		 //迭代器
//		 Iterator<Integer> it = list.iterator();
//		 while(it.hasNext()) {
//			 int m = it.nextpackage com.cl.util;

import java.util.ArrayList;
import java.util.Arrays;
import java.util.Iterator;
import java.util.List;

public class TestList {
	public static void main(String[] args) {
		
		 Integer [] a = {0,12,3,5,7,0,3,0};		 
		 //思路1
//		 int count = 0;		 
//		 for (int i = 0; i < a.length; i++) {
//			if(a[i] == 0) {
//				count ++;
//			}
//		}
//		 int [] b = new int[a.length - count];
//		 int index = 0;
//		 for (int i = 0; i < a.length; i++) {
//				if(a[i] != 0) {
//					b[index ++] = a[i];
//				}
//		 }
//		 System.out.println(Arrays.toString(b));
		 
		 //思路2
		
		 
//		 for (int i = 0; i < list.size(); i++) {
//			if(list.get(i) == 0) {
//				list.remove(i);
//			}
//		 }
//		 List<Integer> list = new ArrayList<Integer>();
//		 list.addAll(Arrays.asList(a));
//		 //迭代器
//		 Iterator<Integer> it = list.iterator();
//		 while(it.hasNext()) {
//			 int m = it.next();
//			 if(m == 0) {
//				it.remove();
//			 }else {
//				 System.out.println(m);
//			 }
//		 }
		 
		// System.out.println(list);
		 
		 
		 //思路3
		 List<Integer> list = new ArrayList<Integer>();
		 for (int i = 0; i < a.length; i++) {
			if(a[i] != 0) {
				list.add(a[i]);
			}
		}
		 System.out.println(list);
	}
}

//			 if(m == 0) {
//				it.remove();
//			 }else {
//				 System.out.println(m);
//			 }
//		 }
		 
		// System.out.println(list);
		 
		 
		 //思路3
		 List<Integer> list = new ArrayList<Integer>();
		 for (int i = 0; i < a.length; i++) {
			if(a[i] != 0) {
				list.add(a[i]);
			}
		}
		 System.out.println(list);
	}
}

```



##### 6.7.4 TreeSet

> Set接口实现类，底层数据结构 ：红黑树【平衡二叉树】  
>
> 可以实现自然排序【必须集合泛型T必须实现Comparable接口，覆盖compareTo()方法】
>
> 自然排序： 默认的排序方式，升序

###### 创建集合对象

```java
new TreeSet() ;  //默认使用自然排序

new TreeSet(Collection c) ;  //默认使用自然排序

new TreeSet(Comparator c); // 使用比较器定制、排序
```

###### 集合方法

| 方法名   | 含义             | 参数 | 返回值 |
| -------- | ---------------- | ---- | ------ |
| add()    | 元素添加         |      |        |
| last()   | 获取最后一个元素 |      |        |
| first()  | 获取第一个元素   |      |        |
| size()   | 集合大小         |      |        |
| remove() | 删除元素         |      |        |

自然排序：

```java
public class Teacher implements Comparable<Teacher>{
	private int age;
	private String name;
	
	
	public int getAge() {
		return age;
	}
	public void setAge(int age) {
		this.age = age;
	}
	public String getName() {
		return name;
	}
	public void setName(String name) {
		this.name = name;
	}
	public Teacher() {
		
	}
	public Teacher(int age, String name) {
		super();
		this.age = age;
		this.name = name;
	}
	@Override
	public int compareTo(Teacher o) {
		if(this.age > o.getAge()) {
			return -1;
		}else if(this.age < o.getAge()) {
			return 1;
		}else {
			return this.name.compareTo(o.getName());
			//return 0;
		}
	}
	@Override
	public String toString() {
		return "Teacher [age=" + age + ", name=" + name + "]";
	}	
	
}
```

排序：

```java
package com.cl.util;

import java.util.TreeSet;

public class TestSet {
	public static void main(String[] args) {
		TreeSet<Integer> set = new TreeSet<Integer>();
		
		set.add(10);
		set.add(5);
		set.add(7);
		set.add(3);
		
		System.out.println(set);
		
		
		TreeSet<String> set2 = new TreeSet<String>();
		
		set2.add("rose");
		set2.add("apple");
		set2.add("cat");
		set2.add("dog");
		
		System.out.println(set2);
		
		
		
		TreeSet<Teacher> set3 = new TreeSet<Teacher>();
		
		set3.add(new Teacher(23, "jack"));
		set3.add(new Teacher(18, "rose"));
		set3.add(new Teacher(18, "tom"));
		
		System.out.println(set3.first());
		System.out.println(set3.last());
	}
}

```

比较器方式：

> Comparator 接口，java.util包，定制比较器的接口，含有抽象方法compare(T t1,T t2);
>
> 

```java
package com.cl.util;

import java.util.Comparator;
import java.util.TreeSet;

public class TestSet2 {
	public static void main(String[] args) {
		//自定义比较器 
		//1. 按照教师的名字降序排列
		
		//定义实现类实现接口
		//Comparator<Teacher> c = new MyCompare();
		
		//匿名内部类
//		Comparator<Teacher> c = new Comparator<Teacher>() {
//
//			@Override
//			public int compare(Teacher o1, Teacher o2) {
//				// TODO Auto-generated method stub
//				return o1.getName().compareTo(o2.getName());
//			}
//			
//		};
		
		//jdk8+  lambda
		Comparator<Teacher> c = (o1,o2) -> o1.getName().compareTo(o2.getName()) ;
		
		
		TreeSet<Teacher> set3 = new TreeSet<Teacher>(c);
		
		set3.add(new Teacher(23, "jack"));
		set3.add(new Teacher(18, "rose"));
		set3.add(new Teacher(18, "tom"));
		System.out.println(set3);
	}
}

```

练习：

```java
1. 定制比较器  整数降序排序

2. 定制比较器 字符串集合降序

3. 定制比较器 按照字符串长度降序 

	cat ab  mother hello   
	
	
package com.cl.util;

import java.util.Comparator;
import java.util.TreeSet;

public class TestSet3 {
	public static void main(String[] args) {
		TreeSet<Integer> s1 = new TreeSet<Integer>(new Comparator<Integer>() {

			@Override
			public int compare(Integer o1, Integer o2) {
				// TODO Auto-generated method stub
				return o2 - o1;
			}
		});
		
		s1.add(10);
		s1.add(8);
		s1.add(32);
		s1.add(18);
		
		System.out.println(s1);
		
	
		TreeSet<String> s2 = new TreeSet<String>((o1,o2) -> o2.compareTo(o1));
		
		s2.add("dog");
		s2.add("cat");
		s2.add("pig");
		s2.add("apple");
		
		System.out.println(s2);
		
		TreeSet<String> s3 = new TreeSet<String>((o1,o2) -> o2.length() - o1.length() == 0 ? o2.compareTo(o1) :o2.length() - o1.length() );
		//TreeSet<String> s3 = new TreeSet<String>((o1,o2) -> o2.length() - o1.length());
		s3.add("cat");
		s3.add("ab");
		s3.add("mother");
		s3.add("hello");
		s3.add("jac");
		System.out.println(s3);
	}
}
	
```

###### 总结Comparable和Comparator接口【重点】

```java
1. Comparable lang包   Comparator util包

2. Comparable覆盖compareTo(o)  Comparator覆盖compare(o1,o2)

3. Comparable 自然排序，固定的排序机制，方便但是不灵活
   Comparator 每次定制比较器， 非常灵活，缺点每次都需要给比较机制 
```



##### 6.7.5 Collections和Arrays

> Arrays 数组帮助类 ，提供数组的相关操作方法： 排序 查找 转集合  转化流 ...
>
> Collections 集合Collection类型集合的帮助类，提供该类型集合相关操作方法： 排序 查找 交换 最大值...
>
> Collection 上层接口 

###### Arrays 

| 方法名                    | 含义                         | 参数 | 返回值 |
| ------------------------- | ---------------------------- | ---- | ------ |
| toString(数组)            | 快速打印数组元素             |      |        |
| sort(数组)                | 对数组元素做自然排序【升序】 |      |        |
| sort(数组,比较器)         | 对数组元素定制比较器排序     |      |        |
| binarySearch(数组,  目标) | 二分查找                     |      |        |
| asList(T...a)             | 将数组转化为List集合         |      |        |
| copyOf()                  | 数组复制                     |      |        |

###### Collections

| 方法名                           | 含义                         | 参数 | 返回值 |
| -------------------------------- | ---------------------------- | ---- | ------ |
| addAll(集合)                     | 批量添加集合元素             |      |        |
| sort()                           | 对数组元素做自然排序【升序】 |      |        |
| sort(比较器)                     |                              |      |        |
| binarySearch(集合,  目标)        |                              |      |        |
| binarySearch(集合,  目标,比较器) |                              |      |        |
| swap(集合，位置1，位置2)         | 交换位置                     |      |        |
| reverse(集合)                    | 翻转                         |      |        |
| max(集合）                       | 自然排序，求最大值           |      |        |
| max(集合，比较器)                | 比较器，获取最大值           |      |        |
| min()                            |                              |      |        |

##### 6.7.6 HashMap

> 底层数据结构： 红黑树【平衡二叉B树】 +  链表 + 数组
>
> 键值对型  ：  key-value
>
> 线程不安全，不同步，效率高， 可以存空值空健



###### 创建集合对象

```java
new HashMap<K,V>(); // K 键类型  V 值类型
```

###### 集合方法

| 方法名                                                       | 含义                         | 参数 | 返回值  |
| ------------------------------------------------------------ | ---------------------------- | ---- | ------- |
| put(键，值)                                                  | 添加元素                     |      |         |
| remove(键)                                                   | 根据键删除键值对             |      |         |
| put(键，值)                                                  | 键相同，值不同，修改集合元素 |      |         |
| get(键)                                                      | 根据键获取值                 |      |         |
| size()                                                       | 集合大小                     |      |         |
| **[containsKey](../../java/util/HashMap.html#containsKey(java.lang.Object))**(Object key) | 判断集合当中是否存在键       |      | Boolean |
| **[keySet](../../java/util/HashMap.html#keySet())**()        | 获得所有的键                 |      | Set     |

示例代码

```java
package com.cl.util;

import java.util.HashMap;
import java.util.Set;

public class TestMap {
	public static void main(String[] args) {
		HashMap<String,String> map = new HashMap<String, String>();
		
		map.put("ip", "192.168.1.19");
		map.put("system", "win10");
		map.put("username", "86136");
		map.put("password", "1223");
		
		map.remove("password");
		map.put("username", "ys998");
		//map.put("username2", "ys998");
		//System.out.println(map);
		
		//System.out.println(map.get("ip"));
		
		//获得所有的键
		Set<String> keys = map.keySet();
		
		for (String key : keys) {
			System.out.println(key + "=" + map.get(key));
		}
		
		//迭代器
		
		
	}
}

```

练习： 给定数组，返回出现次数最多的元素

```java
int[] a ={12,45,12,67,34,8,12};

//HashMap

//键 数字  值 次数

package com.cl.homework;

import java.util.HashMap;
import java.util.Set;

public class TestMap {
	public static void main(String[] args) {
		int[] a = {45,12,45,12,67,45,45,34,8,12};
		HashMap<Integer,Integer> map = new HashMap<Integer, Integer>();
		//时间复杂度 n
		for (int i = 0; i < a.length; i++) {
			if(map.containsKey(a[i])) {
				map.put(a[i],map.get(a[i]) + 1);
			}else {
				map.put(a[i],1);
			}
		}
		
		int max = 0, key = 0;
		Set<Integer> set = map.keySet();
		for (Integer k : set) {
			if(max < map.get(k)) {
				max =  map.get(k);
				key = k;
			}
		}
		System.out.println(key + "=" + max);
	}
}

```



##### 6.7.7 泛型

> 接口或类， List<T> ,  Comparable<T>  ,T 叫做泛型，泛指的某个类型，类型参数化
>
> 类型参数化： 将数据类型像参数一样可以实现传递
>
> 三种体现：  泛型接口   泛型类   泛型方法

好处：

```
  1. 减少强制类型转化
  2. 类型使用安全
  3. 灵活，性能高，类型参数化
```



```java
List<E> 泛型接口  E 泛型

Comparable<T>  泛型接口 T泛型


ArrayList<E>  泛型类  E泛型


public E get(int index)  泛型方法  E 指定泛型

```

泛型类：

```java
package com.cl.util;

public class Generic<T> {
	
	private T t;
	
	
	public Generic(T t) {
		super();
		this.t = t;
	}

	public void get(T t) {
		System.out.println(t);
		if(t instanceof String) {
			System.out.println(((String) t).length());
		}
	}
	
	public T getT() {
		return t;
	}
}

```

泛型接口

```java
public interface MyGeneric<T> {
	
	
	public void set(T t);
}


```

泛型使用

```java
package com.cl.util;

import java.util.function.Consumer;
import java.util.function.Supplier;

public class TestGeneric {
	public static void main(String[] args) {
		//Generic<String> a = new Generic<String>("jack");
		
		//a.get("hello");
		
		//System.out.println(a.getT().length());
		
		MyGeneric<String> my = new MyGeneric<String>() {

			@Override
			public void set(String t) {
				System.out.println(t.length());
			}
			
		};
		
		my.set("jack");
		
		MyGeneric<Teacher> t = s -> System.out.println(s);
		
		t.set(new Teacher(1, "于老师", 98, "JAVA"));
		
		//Supplier 供给者
		Supplier<Double> s = () -> Math.random();
		
		System.out.println(s.get());
		
		//Consumer 消费者
		//Consumer<String>  c =  s-> System.out.println(s.length());
		
		//c.accept("MissYu");
		
	}
}

```



#### 6.8 Date 

> java.util.Date   日期类
>
> java.sql.Date  



###### 创建时间对象

```java
new Date(); //系统当前时间

new Date(long l); l时间戳，毫秒，将时间差值转换为时间点
```



###### 日期方法

| 方法名      | 含义                       | 参数 | 返回值 |
| ----------- | -------------------------- | ---- | ------ |
| getTime()   | 获取当前日期的时间差       |      | long   |
| compareTo() | 比较日期                   |      |        |
| after()     | 判断日期是否在指定日期之后 |      |        |
| before()    | 判断日期是否在指定日期之前 |      |        |





###### 格式转化日期

```java
SimpleDateFormat  s = SimpleDateFormat(String pattern) ;
```

格式化方法

```java
String format(Date d); // 将日期格式化成串

Date parse(String) ; //将字符串转化为日期
```



#### 6.9 Calendar 日历类

> 善于获取年月日 时分秒等，抽象类，不允许实例化对象，调方法获得日历，认为日历对象固定的

不能创建对象，获取日历

```java
Calendar.getInstance() ;  //获得日历实例

set(年，月，日)
    
get(指定常量)
    
getTime() //时间差
    
    
```

示例代码

```java
package com.cl.util;

import java.util.Calendar;

public class TestCalendar {
	public static void main(String[] args) {
		Calendar c = Calendar.getInstance();
		
		//设置日期
		c.set(2023, 10, 11);
		
		System.out.println(c.get(Calendar.YEAR));
		
		System.out.println(c.get(Calendar.MONTH));
		
		System.out.println(c.get(Calendar.DATE));
		
		//System.out.println(c.get(Calendar.));
	}
}

```



#### 6.10  IO处理

> I： input  O： Output   输入输出， 输入输出的是文件
>
> 文件,文件的处理 
>
> 读写文件



##### 6.10.1 文件

> 文件： 相关记录或相关数据的集合，称之为文件。
>
> 如 ： 记事本，word文档，压缩文件，光盘，硬盘，磁盘 ，mp3...



##### java.io.File

可用于操作文件或目录【文件夹】

pathname路径是文件，此时操作是文件，pathname路径目录，此时操作的是目录

###### 创建对象

```java
new File(String pathname) ;
```

举例：

```java
public class TestFile {
	public static void main(String[] args) {
		//f1操作的是文件
		File f1 = new File("D:\\1.txt");
		
		System.out.println(f1.canRead());
		System.out.println(f1.length());
		
		//f2操作的是目录
		File f2 = new File("D:\\a");
		
	}
}
```

###### 文件的方法

| 方法名                  | 含义                       | 参数 | 返回值   | 适用范围  |
| ----------------------- | -------------------------- | ---- | -------- | --------- |
| createNewFile()         | 创建新文件                 |      | boolean  | 文件      |
| exists()                | 判断文件或目录是否存在     |      | boolean  | 文件/目录 |
| length()                | 文件的长度，字节为单位     |      | int      | 文件      |
| getName()               | 获得文件名                 |      |          |           |
| getPath()               | 获得文件路径               |      |          |           |
| isFile()                | 是否是文件                 |      | boolean  | 文件      |
| canRead()  canWrite()   | 是否可读可写               |      | boolean  | 文件      |
| lastModified()          | 最后修改时间               |      | long     | 文件      |
| delete()                | 删除文件                   |      |          | 文件/目录 |
| setWritable()           | 设置读写                   |      |          |           |
| renameTo()              | 重命名                     |      |          |           |
| mkdir()                 | 创建目录，前提是父目录存在 |      |          | 目录      |
| mkdirs()                | 创建目录，父子目录一并     |      |          | 目录      |
| list()                  | 列举目录内容的名字         |      | String[] | 目录      |
| listFiles()             | 列举目录内容文件返回       |      | File[]   | 目录      |
| isDirectory()           | 判断是否是目录             |      |          |           |
| listFiles(FileFilter f) | 筛选过滤文件内容           |      |          |           |
| delete()                | 删除空目录，无法删除非空   |      |          |           |

注意： 

FileFilter  是文件过滤接口，函数式接口，accept() 



示例代码：

```java
package com.cl.io;

import java.io.File;
import java.io.IOException;
import java.text.SimpleDateFormat;
import java.util.Date;

public class TestFile2 {
	public static void main(String[] args) throws IOException {
		//f1操作的是文件
		File f1 = new File("D:\\1.txt");
		
		//先判断
		if(!f1.exists()) {
			//新建
			f1.createNewFile();
			System.out.println("文件创建成功");
		}else {
			//获取信息
			System.out.println(f1.getName());
			System.out.println(f1.getPath());
			System.out.println(f1.length());//字节长度 一字符三字节
			System.out.println(f1.canRead());
			System.out.println(f1.canWrite());
			System.out.println(f1.isFile());
			
			//获得最后修改的时间
			SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
			System.out.println(sdf.format(new Date(f1.lastModified())));
			
			//删除
			f1.delete();
		}
	}
}

```

递归删除目录：

```java
package com.cl.homework;

import java.io.File;

public class DeleteDir {
	
	/**
	 * 方法递归： 递归删除目录全部
	 */
	public static void deleteAll(File dir) {
		
		//先删除里面内容
		File[] files = dir.listFiles();
		for (int i = 0; i < files.length; i++) {
			if(files[i].isDirectory()) {
				deleteAll(files[i]);			
			}else {
				files[i].delete();
			}
		}
		//删除自己
		dir.delete();
	}
	
	public static void main(String[] args) {
		deleteAll(new File("D:\\m"));
		System.out.println("删除结束");
	}
}

```



##### 6.10.2 流

> Stream，流，一连串不间断的数据信号集合。数据传输【读写】的管道。
>
> 读写文件的介质



###### 流的分类

```
1 流的方向

	输入流	读文件
	输出流 写文件
	
	
2 文件类型	
	
	二进制文件，字节型文件，文件存储字节形式存储 .doc  .mp3 
	纯文本文件，字符型文件，文件存储字符形式存储   .txt  .java  
	
	字节流
	字符流
	
	
3 流的传输量	
	节点流 
	缓冲流【处理流】
```



###### 1.字节型输入输出流

```java
InputStream 抽象父类

	FileInputStream  子类，文件字节输入流
	new FileInputStream(文件/字符串);
	
	int read() ;  一次读取一字节，当返回-1读不到  
    read(byte[] b)  一次读取多个内容 
        //瓶颈  128K
        //过大 内容丢失

	void close(); 关闭
	
OutputStream

	FileOutputStream  子类，文件字节输出流
    new FileOutputStream(文件)； 写入时文件可以不存在，自动创建，覆盖写
     new FileOutputStream(文件，boolean)； boolean真，追加写   
        
    write(int i);
	write(byte[] b);
	void close(); 关闭
```

示例：

```java
public class TestInputstream {
	public static void main(String[] args) throws IOException {
		FileInputStream fis = new FileInputStream("D:\\1.txt");
		
		int i = fis.read();
		
		while(i != -1) {
			System.out.println((char)i);
			//读取下一个
			i = fis.read();
		}
		
		fis.close();
	}
}
```

```java
public class TestOutputstream {
	public static void main(String[] args) throws IOException {
		FileOutputStream fos = new FileOutputStream("D:\\3.txt",true);
		fos.write('H');
		fos.write('E');
		fos.write('L');
		fos.write('L');
		fos.write('O');
		fos.close();
	}
}
```

练习： 

```java
//将1.txt文件的内容复制到2.txt

public class Copy {
	public static void main(String[] args) throws IOException {
		FileInputStream fis = new FileInputStream("D:\\1.txt");
		FileOutputStream  fos = new FileOutputStream("D:\\2.txt");
		
		int i = fis.read();
		
		while(i != -1) {
			fos.write(i);
			i = fis.read();
		}
		
		fis.close();
		fos.close();
	}
}
```

加强复制：

```java
package com.cl.io;

import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.IOException;

public class Copy {
	public static void main(String[] args) throws IOException {
		//字节流复制
		FileInputStream fis = new FileInputStream("D:\\apache-tomcat-8.5.24-windows-x64.zip");
		FileOutputStream  fos = new FileOutputStream("D:\\cp2.zip");
		//读取一字节
		byte[] b = new byte[102400];
		int i = fis.read(b);
		
		while(i != -1) {
			fos.write(b);
			i = fis.read(b);
		}
		
		fis.close();
		fos.close();
	}
}

```

###### 2.字符型输入输出流

```
Reader  字符流抽象父类

		FileReader  子类  文件读
		read() 一次读取一字符

Writer 字符流抽象父类

		FileWriter  子类  文件写
		write(String s)
```

示例代码

```java
public class TestReader {
	public static void main(String[] args) throws IOException {
		FileReader fr = new FileReader("D:\\1.txt");
		
		int i = fr.read();
		
		while(i != -1) {
			System.out.println((char)i);
			i = fr.read();
		}
		
		
		fr.close();
	}
}
```

```java
public class TestWriter {
	public static void main(String[] args) throws IOException {
		FileWriter fr = new FileWriter("D:\\4.txt");
		
		fr.write("我爱中国");
		fr.write("\n\r");
		fr.write("我爱辽宁");
		
		fr.close();
	}
}

```



###### 3.缓冲流

> 节点流 ： 和文件直接接触的，没有缓冲的流 ： 字符流  FileReader  FileWriter
>
> 缓冲流 ： 处理流，对节点流进制处理，不会直接接触文件，而是对节点流处理
>
> 好处： 加大数据读写效率，提高速度和性能



```java
Reader  字符流抽象父类
		BufferedReader 从字符输入流中读取文本，缓冲各个字符，从而实现字符、数组和行的高效读取。 
		new BufferedReader(Reader in);
		readLine(); 一次读取一行  String 
		close(); 一旦关闭，将相关流关闭
Writer 字符流抽象父类

		BufferedWriter 将文本写入字符输出流，缓冲各个字符，从而提供单个字符、数组和字符串的高效写入
		new  BufferedWriter(Writer out) ;

		write(String s)
        newLine() 换行
        flush() 刷新
        close() 一旦关闭，将相关流关闭
```

示例代码

```java
public class TestBufferedReader {
	public static void main(String[] args) {
		FileReader fr = null;
		BufferedReader br = null;
		try {
			fr = new FileReader("D:\\《剑道第一仙》.txt");
			//缓冲的是节点流
			br = new BufferedReader(fr);
			String s = br.readLine();
			while(s != null) {
				System.out.println(s);
				s = br.readLine();
			}
		} catch (IOException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}finally {
			try {
				br.close();
			} catch (IOException e) {
				// TODO Auto-generated catch block
				e.printStackTrace();
			}
		}
	}
}
```

```java
public class TestBufferedWriter {
	public static void main(String[] args) throws IOException {
		FileWriter fw = new FileWriter("D:\\5.txt");
		
		BufferedWriter bw = new BufferedWriter(fw);
		
		bw.write("寻常修道者在这样的法相面前，和一根汗毛一般渺小");
		bw.newLine();
		bw.write("我还是喜欢三体");
		bw.flush();
		bw.close();
		
	}
}
```

练习： 使用缓冲流复制小说，且在没每行前四位行号： 0001  0002 ...

```java
package com.cl.io;

import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;

public class Copy3 {
	public static void main(String[] args) throws IOException {
		FileReader fr = new FileReader("D:\\《剑道第一仙》.txt");
		BufferedReader br = new BufferedReader(fr);
		FileWriter fw = new FileWriter("D:\\copy.txt");		
		BufferedWriter bw = new BufferedWriter(fw);
		String s = br.readLine();
		int count = 0;
		while(s != null) {
			count ++;
			if(count >= 1 && count <= 9) {
				bw.write("000"+ count + "\t" + s);
			}else if(count >= 10 && count <= 99) {
				bw.write("00"+ count + "\t" + s);
			}else if(count >= 100 && count <= 999) {
				bw.write("0"+ count + "\t" + s);
			}else {
				bw.write( count + "\t" + s);
			}
			
			//换行
			bw.newLine();
			s = br.readLine();
		}
		br.close();
		bw.flush();
		bw.close();
	}
}

```

##### 6.10.3 转换流

> 字节流向字符流转化，可以加大缓冲【只能缓冲字符流】。

```java
public class InputStreamReader extends Reader{

}

new InputStreamReader(InputStream in) ;
```

示例代码

```java
public class TestInputStreaReader {
	public static void main(String[] args) throws IOException {
		System.out.println("请输入内容");
		//将字节流转化字符流
		InputStreamReader isr = new InputStreamReader(System.in) ;
		BufferedReader br = new BufferedReader(isr);
		
		System.out.println("您输入的内容:" + br.readLine());
	}
}
```



##### 6.10.4 打印流

> PrintWriter打印输出流，网页打印，输出。

好处：

```
1. 自动创建文件
2. 自带缓冲
3. 自动刷新
4. 自动换行
```

方法：

```
print()  println()

close();
```

示例代码

```java
public class TestPrint {
	public static void main(String[] args) throws IOException {
		PrintWriter pw = new PrintWriter("D:\\6.txt");
		
		pw.print("hello");
		pw.println("world");
		pw.print("HelloWorld");
		
		pw.close();
	}
}
```

示例代码

```java
package com.cl.io;

import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
import java.io.PrintWriter;

public class Copy4 {
	public static void main(String[] args) throws IOException {
		FileReader fr = new FileReader("D:\\《剑道第一仙》.txt");
		BufferedReader br = new BufferedReader(fr);
		PrintWriter pw = new PrintWriter("D:\\7.txt");
	
		String s = br.readLine();
		int count = 0;
		while(s != null) {
			count ++;
			pw.printf("%04d",count);
			pw.println(s);
			s = br.readLine();
		}
		br.close();		
		pw.close();
	}
}

```



##### 6.10.5 序列化和反序列化【重点】

> 对象序列化： 将JAVA创建出来对象数据写入到文件中，永久保存
>
> 反序列化 ： 从文件中读取对象的数据信息

```java
简言之，对象的文件读写操作

好处：
	对象持久化
	
前提：
必须实现Serializable接口【标志】，排除属性关键字： private transient int age;
```

API:

```java
ObjectOutputStream 序列化  
writeObject(Object obj)  写入对象

ObjectInputStream  反序列化
readObject() 读取对象，按顺序
```

序列化：

```java
package com.cl.io;

import java.io.Serializable;

public class Student implements Serializable{

	/**
	 * 唯一标志
	 */
	//private static final long serialVersionUID = 1L;
	
	private int sno;
	private String name ;
	private transient int age;
	public Student(int sno, String name) {
		super();
		this.sno = sno;
		this.name = name;
	}
	@Override
	public String toString() {
		return "Student [sno=" + sno + ", name=" + name + "]";
	}
}

```



```java
public class WriteObject {
	public static void main(String[] args) throws IOException {
		FileOutputStream fos = new FileOutputStream("D:\\ys.txt");
		ObjectOutputStream oos = new ObjectOutputStream(fos);
		//Integer
		oos.writeObject(10);
		//String
		oos.writeObject("jack");
		//Student
		oos.writeObject(new Student(1,"rose"));
		
		oos.close();
	}
}
```

反序列化：

```java
package com.cl.io;

import java.io.FileInputStream;
import java.io.IOException;
import java.io.ObjectInputStream;

public class ReadObject {
	public static void main(String[] args) throws IOException, ClassNotFoundException {
		FileInputStream fis = new FileInputStream("D:\\ys.txt");
		ObjectInputStream ois = new ObjectInputStream(fis);
		
		System.out.println(ois.readObject());
		System.out.println(ois.readObject());
		Student s = (Student)(ois.readObject());
		System.out.println(s);
	}
}

```



#### 6.11 多线程

> 应用程序 ： 一组静态的指令集，比如没有使用的qq，谷歌浏览器
>
> 进程 ： 当应用程序处于运行状态，包含多个进程，进程是能够独立运行的最小单元，开辟内存，浏览器进程，谷歌xx进行
>
> 线程 ：  一个进程会包含多个线程，线程是一条程序控制流， 一条分支，并发运行，qq多个聊天窗口。



##### 6.11.1 作用

JAVA 多线程，并发运行 ： 程序运行n条分支并发执行

```
提高代码的执行效率
```

##### 6.11.2 进程和线程的区别

```
1. 进程需要开辟内存，要独立空间，分配系统资源，系统的能够独立运行的基本单元

2. 线程是进程中最小单元，不需要再次分配
```

##### 6.11.3 多线程实现

java.lang中包含线程操作。主方法就是一个线程： 主线程，JVM自动启动线程

###### 1.继承父类Thread

```java
public class  XXThread  extends Thread{
	public void run(){
	
	
	}
}
```

###### 属性：

```java
static int MAX_PRIORITY   10
          线程可以具有的最高优先级。 
static int MIN_PRIORITY   1
          线程可以具有的最低优先级。 
static int NORM_PRIORITY  5
          分配给线程的默认优先级。 

```

###### 构造：

```java
new Thread() 
          分配新的 Thread 对象。 
new Thread(Runnable target) 
          分配新的 Thread 对象。 
new Thread(Runnable target, String name) 
          分配新的 Thread 对象。 
new Thread(String name) 
          分配新的 Thread 对象，初始化线程名

```

###### 方法：

| 方法名                        | 含义                                                         | 参数 | 返回值 |
| ----------------------------- | ------------------------------------------------------------ | ---- | ------ |
| run()                         | 线程体，线程执行内容，该方法系统在线程启动后自动调，不要手动调 |      | void   |
| start()                       | 线程的启动，线程执行方法，只需一次，启动之后进入就绪，不会直接执行 |      |        |
| currentThread()               | 返回当前正在运行的线程对象                                   |      | Thread |
| getName()                     | 获得线程名字                                                 |      |        |
| setName()                     | 修改线程名字                                                 |      |        |
| setPriority (int newPriority) | 修改线程的优先级 【1，10】                                   |      |        |
| sleep(毫秒)                   | 线程休眠，主观休息，让步给任何优先级线程                     |      |        |
| yield()                       | 线程暂停，让步给更高优先级，如果没有，立即执行               |      |        |

示例：

```java
package com.cl.thread;

public class TicketWindow extends Thread{
	
	private int tickets = 100;

	public TicketWindow() {
		super();
		// TODO Auto-generated constructor stub
	}

	public TicketWindow(String name) {
		super(name);
		// TODO Auto-generated constructor stub
	}
	/**
	 * 线程体
	 */
	@Override
	public void run() {
		for (int i = 1; i <= 20;i ++) {
			System.out.println(Thread.currentThread().getName() + ":第" + i + "张票被卖出");
		}
	}	
}


public class TestThread2 {
	public static void main(String[] args) {
		System.out.println("开始售票。。。。。。");
		
		TicketWindow w1 = new TicketWindow("窗口1");		
		TicketWindow w2 = new TicketWindow("窗口2");
		
		w1.setPriority(10);
		w2.setPriority(Thread.MIN_PRIORITY);
		
		w1.start();
		w2.start();
	}
}
```



###### 线程的五个状态

```
新建   就绪   执行  阻塞  结束
```

![](img\27.png)

###### 2.实现Runnable

```java
public abstract void run() ;
```

示例：

```java
public class Window implements Runnable{

	@Override
	public void run() {
		for (int i = 1; i <= 20;i ++) {
			try {
				Thread.sleep(1000);
			} catch (InterruptedException e) {
				// TODO Auto-generated catch block
				e.printStackTrace();
			}
			System.out.println(Thread.currentThread().getName() + ":第" + i + "张票被卖出");
		}
	}

}
```

```java
public class TestThread4 {
	public static void main(String[] args) {
		Window w = new Window();
		Thread t = new Thread(w);
		
		t.start();
	}
}

```

匿名内部类

```java
package com.cl.thread;

public class TestThread5 {
	public static void main(String[] args) {
		Thread w1 = new Thread(new Runnable() {
			
			@Override
			public void run() {
				for (int i = 1; i <= 10;i ++) {
					try {
						Thread.sleep(1000);
					} catch (InterruptedException e) {
						// TODO Auto-generated catch block
						e.printStackTrace();
					}
					System.out.println(Thread.currentThread().getName() + ":第" + i + "张票被卖出");
				}
			}
		},"窗口1");
		
		w1.start();
		
		
		
		
		Thread w2 = new Thread(new Runnable() {
			
			@Override
			public void run() {
				for (int i = 1; i <= 5;i ++) {
					try {
						Thread.sleep(2000);
					} catch (InterruptedException e) {
						// TODO Auto-generated catch block
						e.printStackTrace();
					}
					System.out.println(Thread.currentThread().getName() + ":第" + i + "张票被卖出");
				}
			}
		},"窗口2");
		
		w2.start();
	}
}	

```

Lambda

```java
public class TestThread6 {
	public static void main(String[] args) {
		Thread w1 = new Thread(()->{
			for (int i = 1; i <= 5;i ++) {
				try {
					Thread.sleep(2000);
				} catch (InterruptedException e) {
					// TODO Auto-generated catch block
					e.printStackTrace();
				}
				System.out.println(Thread.currentThread().getName() + ":第" + i + "张票被卖出");
			}
		},"窗口1") ;
		
		w1.start();		
	}
}	
```



##### 6.11.4 线程同步，线程安全

> 线程安全，线程同步，多个线程同时访问临界资源时，A线程操作临界数据时，B线程无法操作共享资源，相当于对资源加锁，A操作完毕，B线程再操作。
>
> 线程不安全，不同步，多个线程同时操作，尽量避免使用临界资源，效率高



##### 线程加锁的方式

```
同步锁  
	synchronized 
	
	同步块
	同步方法
	
lock() 锁 jdk5+
	
```

死锁：

> 线程一旦加锁，A线程和B线程分别获得到共享资源的一部分，每个线程都不释放，进入僵持，死锁。



示例：

```java
package com.cl.thread;
/**
 * 银行卡
 * @author 86136
 *
 */
public class Card {
	private double balance;

	public double getBalance() {
		return balance;
	}

	public void setBalance(double balance) {
		this.balance = balance;
	}

	public Card(double balance) {
		super();
		this.balance = balance;
	}
	
	public Card() {
		
	}
}

```

```java
package com.cl.thread;

public class SaveThread implements Runnable{
	
	private Card c ;
	
	
	
	public SaveThread(Card c) {
		super();
		this.c = c;
	}



	@Override
	public void run() {
		synchronized (c) {
			for (int i = 1; i <= 5; i++) {
				
				c.setBalance(c.getBalance() + 1000);
				
				System.out.println(Thread.currentThread().getName() + "存钱成功，当前余额" + c.getBalance());
			
				try {
					Thread.sleep(1000);
				} catch (InterruptedException e) {
					// TODO Auto-generated catch block
					e.printStackTrace();
				}
			}
		}
		
	}

}

```

```java
package com.cl.thread;

import java.util.concurrent.locks.ReentrantLock;

public class FetchThread implements Runnable{
	
	private Card c ;
	//private ReentrantLock lock = new ReentrantLock();
		
	public FetchThread(Card c) {
		super();
		this.c = c;
	}
	@Override
	public void run() {
		//lock.lock();
		//lock.unlock();
		synchronized (c) {
			for (int i = 1; i <= 5; i++) {
				
				c.setBalance(c.getBalance() - 1000);
				
				System.out.println(Thread.currentThread().getName() + "取款成功，当前余额" + c.getBalance());
			
				try {
					Thread.sleep(1000);
				} catch (InterruptedException e) {
					// TODO Auto-generated catch block
					e.printStackTrace();
				}
			}
		}	
	}
}

```

```java
package com.cl.thread;

public class TestThread {
	public static void main(String[] args) {
		Card c = new Card(1000);
		
		Thread t1 = new Thread(new SaveThread(c), "朱朱");
		t1.start();
		
		
		Thread t2 = new Thread(new FetchThread(c), "佳佳");
		t2.start();
	}
}

```



#### 6.12 JDK8+

新增内容：

```
1. 接口中方法变化 ： 新增两类 非抽象的方法  默认方法default 、 静态方法 static

2. String  join()

3. Files 文件处理

4. Lambda 表达式

5. 函数式接口 

6. Stream

7. 日期时间升级 : LocalDateTime  取代了 Date  Calendar

```



##### 6.12.1 接口中方法

```java
//接口中的属性  公开的静态常量
public static final


//接口中的方法  公开的抽象方法
public abstract 
    
    
//新增方法1 ： 默认方法，会被所有的实现类默认实现获得
    
public default void 方法名(){
    
    
}

//新增方法2 : 静态方法 ，接口独有的 ，接口使用， 接口.xx()

public static void 方法名(){
    
    
}
```

示例:

```java
package com.icss.demo;

public interface IWeapon {
	
	public static final int POWER = 200;
	
	//默认方法
	public default void fire() {
		System.out.println("突突突");
	}
	
	void user();
	
	//静态方法
	public static void haha() {
		System.out.println("哈哈哈哈哈");
	}
	
}

class Tank implements IWeapon{

	@Override
	public void user() {
		// TODO Auto-generated method stub
		
	}


	
}
class Gun implements IWeapon{

	@Override
	public void user() {
		// TODO Auto-generated method stub
		
	}
}
```

测试：

```java
public class TestWeapon {
	public static void main(String[] args) {
		IWeapon w = new Tank();
		
		System.out.println(IWeapon.POWER);
		
		w.fire();
		
		IWeapon w2 = () -> {};
		
		IWeapon.haha();
	}
}

```



##### 6.12.2  String新增

```java
join()  

public class TestString {
	public static void main(String[] args) {
		
		//将数组使用某种连接符号成字符串
		
		String[] s = {"192","168","30","200"};
		
//		String str = "";
//		for (int i = 0; i < s.length; i++) {
//			str += s[i] + ".";
//		}
//		
//		System.out.println(str.substring(0,str.length() - 1));
		
		System.out.println(String.join(".", s));
	}
}

```



##### 6.12.3 文件新增

```java
		Path p = Paths.get("D:\\2.txt");
		
		BufferedWriter bw = Files.newBufferedWriter(p);
		
		bw.write("和于老师一起学习");
		bw.close();
```



##### 6.12.4 Lambda 

> Lambda是简化匿名内部类的新型写法，作用简化代码。特殊的匿名内部类

要求： 函数式接口 【只有一个抽象方法的接口，可以有多个非抽象的方法的接口】 ，称之为SAM接口。

例如：

```java
@FunctionalInterface
public interface Consumer<T> {
	
	

}
```

语法规则:

```java
<函数式接口>  变量名  = (参数变量1，参数变量2...)  ->  {覆盖接口的方法体};
```

1. 参数类型直接识别
2. 如果没有参数，只保留()
3. 如果只有一个参数，可以省略()
4. 如果方法体只有一句话，可以省略{} ， 如果只有一个返回值一句话，可以省略return



示例:

```java
@FunctionalInterface
public interface Computer {
	
	//void sum(int a,int b);
	
	int abs(int a);
	
}

public class TestComputer {
	public static void main(String[] args) {
//		Computer c = (a,b) -> {
//			System.out.println(a + b);
//		};
//		
//		c.sum(1, 2);
		
		
//		Runnable r = () ->{
//			for (int i = 1; i <= 100; i++) {
//				System.out.println(i);
//			}
//		};
//		//线程启动
//		new Thread(r).start();
		
		
		Computer c = a -> a >=0 ? a : -a;
		
		
		
	}
}
```



线程池：

```
Thread 
Runnable

Callable



Runnable和Callable区别?

1. Runnable 是lang包 用于创建线程  run() 线程体  无返回值  不能抛出异常
2. Callable 是util 配合线程池创建线程 call() 线程体  有返回值  抛出异常
```

示例：

```java
package com.icss.demo;

import java.util.concurrent.Callable;
import java.util.concurrent.ExecutionException;
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;
import java.util.concurrent.Future;

public class TestCall {
	public static void main(String[] args) throws InterruptedException, ExecutionException {
		//创建线程体 1-100和
		
		//创建线程池ExecutorService 管理线程池
		ExecutorService service = Executors.newFixedThreadPool(2);
		
		Callable<Integer> c = ()->{
			int sum = 0;
			for (int i = 1; i <= 50; i++) {
				sum += i;
			}
			return sum;
		};
		
		Callable<Integer> c2 = ()->{
			int sum = 0;
			for (int i = 51; i <= 100; i++) {
				sum += i;
			}
			return sum;
		};
		//线程池添加任务
		Future<Integer> f1 = service.submit(c);
		Future<Integer> f2 = service.submit(c2);
		
		//线程获得结果
		System.out.println(f1.get() + f2.get());
		
		//关闭线程池不接任务
		service.shutdown();
		
	}
}

```



##### 6.12.5 函数式接口【jdk8+】

```
1. 消费型
2. 供给型
3. 断言型
4. 函数型
```

![](img\28.png)

消费型 Consumer

供给型 Supplier

```java
package com.icss.demo;

import java.io.File;
import java.io.FileFilter;
import java.util.Arrays;
import java.util.function.Consumer;
import java.util.function.Supplier;

public class TestLambda {
	public static void main(String[] args) {
		//供给型
		Supplier<Double> s = () -> Math.random();
		
		//System.out.println(s.get());
		
		//消费型
		Consumer<String> c = t -> System.out.println(t.length());
		
		//c.accept("tom");
		
		//消费性，传入文件获得文件名字的拓展名
		
		Consumer<File> c2 = f -> {
			String name = f.getName();
			System.out.println(name.substring(name.lastIndexOf(".")));
		};
		
		
		//Consumer<File> c3 = f -> f.getName().substring(f.getName().lastIndexOf("."));
		
		//c2.accept(new File("D:\\haha.png"));
		
		//传入目录，打印目录中txt文件
		// d 目录  
		Consumer<File> c4 = d -> {
			//files遍历出的内容  f是目录中的每一个文件
			File[] files = d.listFiles( f -> f.isFile() && f.getName().endsWith(".txt"));
			
			System.out.println(Arrays.toString(files));
		};
		
		c4.accept(new File("D:\\a"));
		
		//供给 随机A-Z
		
		Supplier<Character> rs = () -> (char)((90 - 65 + 1) * Math.random() + 65) ;
		
		System.out.println(rs.get());

	}
}

```

断言式接口 Predicate

```java
package com.icss.demo;

import java.io.File;
import java.io.FileFilter;
import java.util.ArrayList;
import java.util.Arrays;
import java.util.Comparator;
import java.util.Iterator;
import java.util.function.Consumer;
import java.util.function.IntPredicate;
import java.util.function.Predicate;
import java.util.function.Supplier;

public class TestLambda2 {
	public static void main(String[] args) {
		//断言型
		//判断数字是否大于10
		Predicate<Integer> p = i -> i > 10;
		
		System.out.println(p.test(12));
		
		Integer[] a = {12,0,23,0,11,78,45};
		
		//a转化为集合 遍历删除
		
		ArrayList<Integer> list = new ArrayList<Integer>(Arrays.asList(a));
		
		Iterator<Integer> it = list.iterator();
		
		while(it.hasNext()) {
			if(it.next() == 0) {
				it.remove();
			}
		}
		System.out.println(list);
		
		
		//Stream
		//IntPredicate3
		//Arrays.stream(a).filter(i -> i != 0).forEach(System.out::println);

		Student[] s = {new Student(1, "jack", 19),new Student(2, "tom", 21),new Student(3, "rose", 18),new Student(4, "mary", 18)};
		
		
		//数组中名字是4位 成年的学生过滤 
		
		Arrays.stream(s)
		.filter( stu-> stu.getSname().length() == 4 && stu.getAge() >= 18)
		//自然排序 Comparable
		.sorted()
		//比较器Comparator
		//.sorted((s1,s2) -> s1.getAge() - s2.getAge())
		.forEach(System.out::println);
		
	}
}

```

函数式接口 Function

```java
public class TestLambda3 {
	
	public static void main(String[] args) {
		
		Function<String, Integer> f = s -> s.length();
		
		System.out.println(f.apply("Diana"));
		
		
		Function<Integer, Integer> f2 = s -> s >= 0?s :-s;
		
		System.out.println(f2.apply(10));
	}

}
```



##### 6.12.6  方法引用 

```java
::

Lambda表达式的语法糖， 用于简化Lambda表达式，但方法使用的参数和Lambda参数一致，可以使用::

.forEach( s -> System.out.println(s));

.forEach(System.out::println);
```



##### 6.12.7 Stream流 

```
Stream简化代码，优化代码，更加简洁和高效。
```

流的使用过程



![](img\1.JPG)





原料

```
数组
集合
一组连串的数据： 可变长参数 ， 一连串的彩票数字号码 .... 没有经过处理的
```



工序[仅限于对Stream]

```
对原料进行数据处理  排序 去重  筛选 求和  最大值 .... 
```

产品

```
将Stream还原成为数组或集合
```



###### 流的创建：

```java
1 数组创建

Arrays.stream(T[] t)

Arrays.stream(T[] t,int s,int e)
```



```java
2.集合创建

ArrayList<String> list = new ArrayList<String>();
		list.add("bana");
		list.add("appl");
		list.add("jack");
		list.add("rose");
		list.add("tom");
		list.add("jack");
		
list.stream().distinct().filter(s -> s.length() == 4).sorted().forEach(System.out::println);
```



```java
3.Stream.of(T...a)

Stream.of(10,30,12,67,23,30).sorted().forEach(System.out::println);
```



```java
4.generate()

Stream.generate(Supplier s);

//6个红球 1-33 无重复
Stream.generate(() -> (int)(33 * Math.random() + 1)).limit(6).distinct().forEach(System.out::println);
```



```java
5.随机数
Random r = new Random();
r.ints(1, 34).distinct().limit(6).forEach(System.out::println);

```


###### 流的加工

```java
filter(Predicate p) 过滤

distinct() 去重，底层原理： 覆盖hashCode()  equals()

limit(maxlen) 限制个数


map(Function f) 映射
int [] a = {2,5,10,4,9};
Arrays.stream(a).filter(n -> n % 2 == 0).map(f->f * f).forEach(System.out::println);


sorted()   自然排序
sorted(Comparator c)  比较器
   

```



###### 流的终止

```java
//匹配查找
forEach(Consumer c);

count() 统计个数
    
//统计非空串个数
long l = Stream.of("jack","","rose","tom","").filter(s-> !s.equals("")).count();
System.out.println(l);    

max(Comparator c)
min(Comparator c)
 
//还原，归约成产品
collect(Collector c)
    
    
//归约  所有流数据汇总到一个值
reduce()
```

示例

```java
public class TestStream7 {
	public static void main(String[] args) {
		//原料
		List<String> list = new ArrayList<String>();
		list.add("ban");
		list.add("apple");
		list.add("jack");
		list.add("rose");
		list.add("tom");
		list.add("jack");
		//工序
		list = list.stream().distinct().filter(a -> a.length() == 4).collect(Collectors.toList());
		//产品
		System.out.println(list);
		
	}
}
```

##### 6.12.8 新增日期

```java
LocalDateTime  本地时间日期


创建日期
static now() 系统当前时间
static of(年月日时分秒)  指定时间


方法
getYear()
getMonthValue() getMonth()
getDayof..()
...


格式化
DateTimeFormatter 

static ofPattern() 设定日期格式

format()
parse()
```

示例:

```java
public class TestDate2 {
	public static void main(String[] args) {
		LocalDateTime date = LocalDateTime.now();
		//System.out.println(date);
		
//		System.out.println(date.getYear());
//		System.out.println(date.getMonthValue());
//		System.out.println(date.getDayOfMonth());
//		System.out.println(date.getDayOfYear());
		//星期几
		//System.out.println(date.getDayOfWeek());
		
		LocalDateTime date2 = LocalDateTime.of(2000, 5, 12, 10, 30);
		//System.out.println(date2);
		
		
		DateTimeFormatter fotm = DateTimeFormatter.ofPattern("yyyy年MM月dd日");
		
		System.out.println(fotm.format(date2));
		
		
	}
}
```


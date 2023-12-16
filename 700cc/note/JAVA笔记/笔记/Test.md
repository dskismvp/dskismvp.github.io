###  8-22

```
1. java 3个领域
javase 标准版 桌面开发
javaee 企业版 企业开发
javame 微型版 手机开发


2.java运行机制

java半编译半解释

3. 源文件 .java   编译后 ： 字节码文件 【类文件】  .class 

4. 优势
   多线程 高并发
   跨平台
   安全性
   鲁棒性
   ...
5. 项目开发流程

   市场调研 >  需求分析 >  设计 >  研发 > 测试 >  交付 > 运维 
   
6. 包  com.cl.car    
7. 注释 
	//
	/*  */ 
	/** / 文档注释
	
8. 系统架构
	
	《基于BS架构二手交易系统的设计与实现》
	《基于SSM框架的在线教育系统的设计与实现》
	
	BS 浏览器服务器架构
	CS 客户端服务器架构
	
9. JVM java虚拟机 虚拟的操作系统  程序运行在JVM上

10. sun  oracle 甲骨文
```

### 8-23

命名规范：

```
包  	  小写       com.cl.demo
类  	  首字母大写  HelloWorld 
变量   小写，复合单词 驼峰   a b c stuNo 
常量   全大写    PI YEAR MONTH 
```



```
1.
int age = 18;

2. 
int a , b = 2 , c ;

3.常量
final double PI = 3.14 ;

4.
整数型  
byte 字节型  1  8
short 短整型 2  16
int 整型     4  32
long 长整型  8  64

7.手机号
long tel = 13610943167L;

//思考?
long l = 10;

8.
class   关键字 
Class   类 反射类

9.
JAVA数据类型
基本数据类型
	整数型  浮点型  字符型  布尔型 
	
引用数据类型 
	数组 类 接口 枚举 注解
	
10.JAVA运行机制
	
   半编译半解释
   
   JAVA编码机制
   UTF-8  全球资源编码 字符包括汉字和字母
```



### 8-24

```
1.
浮点型
float  单精度浮点
double 双精度浮点

2. 编码机制  UTF-8

3. int 4 32 
   double 8 64
   
   byte < short < int < long < float < double
   
4. float f = 3.58F;
   float f = 3.58f;
   float f = (float)3.58;
   
5.  强制转换
	int a = (int)f;
	
6.  char 2 16 0~65535  short 2 16  -32768 ~  32767

7.  a-z 97 - 122  A-Z  65-90  0-9 48 -57

	随机数
	[a,b]
	(int)((b - a + 1) * Math.random() + a )

8.  boolean  true false

9.  算术运算符  + - * / % ++ --
10. 转义 \  \n \t \u0000 空字符   
	// 注释
```



### 8-25

```
1. 
短路与 &&  左侧操作数假的，右侧操作数短路 
逻辑与 &   都执行 

||  左侧操作数真的，右侧操作数短路 
|   都执行

2. a % b == 0   != 

3. 2 << 2 =  8

4. String opr = m % 7 == 0 ? "是" : "不是";

5. ++ -- 前置 一定先+ - 1 再执行其他运算  后置 先执行其他操作，再做自加自减

6. a % 5 == 0 && a % 6 == 0

7. true false

8. A-Z 65-90  0-9 48-57

   '1' + 1 =  49 + 1 = 50
    "1" + 1 = "11"
    
9. 
long 8 64  L 
float 4 32 F 
    float空间大  float > long
    
10. final double E = 2.71828;    
```



### 8-28

```
1. 

BS  浏览器 服务器
CS  客户端 服务器

2. 
float 4 32
double 8 64 

3.
运算符

算术 + - * / % ++ --
比较 > < == != >= <=
逻辑 && || !
条件 ? :
赋值 = += ...

4.
int min = a < b ? a : b ;

5.
byte short int char String 枚举enum

6.
break;

7.
|| 左侧操作数真，右侧短路
| 都执行

8.
char  UTF-8

9.double d = 8.58;  int a = (int)d;

10.boolean boo = false;
```





### 8-29

```java
1. switch case 
值类型 ： byte short  int  char  String【7+】 枚举【5+】

2.default

3. 0-9  48-57

4. javase javaee javame

5.
int count = 0;
for(int i = 1;i <= 12;i ++){
	switch(i){
		case 1:
		case 3:
		case 5:
		case 7:
		case 8:
		case 10:
		case 12: count ++; break;
	}
}
sout...(count);

6.
int sum = 0;
for(int i = 2;i <= 100;i += 2 ){
	sum += i;
}
for(int i = 1;i <= 100;i ++ ){
	if(i % 2 == 0)
        sum += i;
}
sout...(sum);

7.
public class TestStar {
	public static void main(String[] args) {
		//行
		// 4 0
		// 3 1
		// 2 2
		// 1 3
		for (int i = 4; i >= 1 ; i --) {
			for (int k = 1; k <= 4 - i; k++) {
				System.out.print(" ");
			}
			for (int j = 1; j <= i; j++) {
				System.out.print("*");
			}
			System.out.println();
		}
	}
}

```



### 8-30

```java
package com.cl.homework;
/**
 * 百钱买百鸡
 * @author Administrator
 *
 */
public class Test1 {
	public static void main(String[] args) {
		//母鸡
		for (int i = 0; i <= 33; i++) {
			//公鸡
			for (int j = 0; j <= 50; j++) {
				//小鸡
				for (int k = 0; k <= 100; k++) {
					if(i + j + k == 100 && i * 3 + j * 2 + k * 0.5 == 100) {
						System.out.println(i + "," + j + "," + k);
					}
				}
			}
		}
	}
}

```

```java
public class Test2 {
	public static void main(String[] args) {
		int count = 0;
		for (int i = 1; i <= 100; i++) {
			if(i % 7 == 0 || i % 10 == 7) {			
				count ++;
				if(count == 4) {
					//退出循环
					break;	
				}
			}else {
				System.out.println(i);
			}
		}
	}
}
```

```java
package com.cl.homework;

public class Test3 {
	public static void main(String[] args) {
		for (int i = 1; i <= 4; i++) {
			for (int j = 1; j <= 4; j++) {
				if( i == 2 && j == 2 ||  i == 3 && j == 3 || i == 2 && j == 3 || i == 3 && j == 2)
					System.out.print(" ");
				else
					System.out.print("*");
			}
			System.out.println();
		}
		
		for (int i = 0; i < 4; i++) {
            for (int j = 0; j < 4; j++) {
                if (i == 0 || i == 3|| j == 0 || j == 3) {
                    System.out.print("*");
                } else {
                    System.out.print(" ");
                }
            }
            System.out.println();
        }
	}
}

```

```java
package com.cl.homework;

import java.util.Random;

public class Test4 {
	public static void main(String[] args) {
//		int count = 0;
//		while(true) {
//			char c = (char)((57 - 48 + 1) * Math.random() + 48);
//			System.out.println(c);
//			count ++;
//			if(count == 4) {
//				break;
//			}
//		}
		//jdk8+
		Random r = new Random();
		r.ints(65,90).distinct().limit(4).forEach(a -> System.out.println((char)a));
	}
}

```



### 8-31

```java
1. 循环退出

continue     执行下一个
continue 标签
break        跳出一层
break 标签

return 
System.exit(0);

ok:
for(){	
	for(){	
		break ok;
	}
}


2. while 先判断条件 循环体  0 / n
   do-while 循环体再条件  1 / n
	
	
3.
算术 % /
比较 != ==
逻辑 && || !
条件 ? :
赋值 = += 
    
public class Test {
	public static void main(String[] args) {
		//1 1-100完全平方数 
		//int count = 0;
		//int a = 1; 
		
		//被开方的
//		for (int i = 1; i <= 10; i++) {
//			a = i * i;
//			count ++;
//			System.out.print(a + "\t");
//			if(count % 3 == 0)
//				System.out.println();
//		}
		
		//i平方
//		for (int i = 1; i <= 100; i++) {
//			if(a * a == i) {
//				System.out.println(i);
//				a ++;
//			}
//		}
		//123
//		for (int i = 100; i < 1000; i++) {
//			int a = i / 100;
//			int b = i % 100 / 10;
//			int c = i % 10;
//			
//			if(a * a * a + b * b * b + c * c *c == i) {
//				System.out.println(i);
//			}
//		}
		int count = 0;
		for (int i = 1; i <= 4; i++) {
			for (int j = 1; j <= 4; j++) {
				for (int k = 1; k <= 4; k++) {
					if(i != j && j != k && i != k) {
						System.out.println(i * 100 + j * 10 + k);
						count ++;
					}				
				}
			}
		}
		System.out.println(count);
	}
}

```



### 9-1

```java
1.
double[] a = new double[3];

2. 
int[] a = {1,2,3,4};

int[] a;
a = new int[]{1,2,3,4};

3. 整型 0  浮点 0.0  String字符串  null  char字符 \u0000
    
4. [0,a.length-1]
   
5. sout...(a[a.length - 1]); //a数组最后一个元素
sout...(a[0]);

6. foreach
    for(int i : a){
        sout...(i);
    }
7.  int count = 0;
    for(int i = 0;i < a.length ; i ++){
        if(a[i] == 0){
            count ++;
        }
    }

sout....(count);
```



### 9-4

``` java
1. 
char [] c = new char[3];

2.
    c[0] = 'a';

3. sout...(c[c.length - 1]);

4.
    float [] f = {1,2,3,4}; 
	
5.
    for(int i = 1 ; i < f.length ;i ++){
        for(int j = 0;j < f.length - i; j ++){
            if(f[j] < f[j + 1]){
                int temp = f[j];
                f[j] = f[j + 1]; 
                f[j + 1] = temp;
            }
        }
    }

	for(int t : f){
        sout...(t);
    }

sout...(Arrays.toString(f));


6.
    break 跳出一层循环
    return 退出方法
    continue 略过下一次循环
    
7.
    switch : byte short int char String enum[枚举]  class  interface
8.
    || 左侧为真 右侧短路
     | 都执行
        
9.
    二分查找【折半】
     先排序，取一组数据中间位置元素和目标比较，
        大于目标，中间位置右侧部分取中间位置和目标比较
        ...
        
10.
        整数，输出几位数
public class Test {
	
	public static void main(String[] args) {
		int a = 67423;
		int count = 0;
		
		while(a >= 1) {
			a /= 10;
			count ++;
		}
		System.out.println(count);
	}

}
     
```



### 9-5

```java
1.

int[][] a = new int[4][];

2.
a[0][0]

3.
int[] b = new int[5];

4. //大写字母 A-Z 65-90  (大-小+1)* Math.random() + 小
for(int i = 0; i < b.length;i ++){
    b[i] = (int)((90-65+1)*Math.random()+65);
}

5.
for(int i = 0; i < b.length - 1;i ++){
    for(int j = i + 1 ; j < b.length; j ++){
        if(b[i] > b[j]){
            int temp = b[i];
            b[i] = b[j];
            b[j] = temp;
        }
    }
}
   
6.
    类、对象  
    属性 一类事物的特征
    方法 一类事物的行为
    
7.
    public class Animal{
        public String name;
        public String type;
    }

8. null
    
9. OOA 面向对象分析   OOD 面向对象设计  OOP 面向对象编程
```



### 9-6 

```java
1
public class Teacher{
	public String name;
    public String no;
    public int age;
}
2.
Teacher ys = new Teacher();

3.
    ys.name = "于老师";

4.
    栈            堆
    ys xxx        name  于老师
    			  no  null
    			  age  0
    
5.
    public int time(){
     return 8; 
   }

6. public int max(int a,int b){
    return a>= b? a : b;
}
public int max(int a,int b){
    if(a >= b)
        return a;
    else 
        return b;
}

7.
    public void abs(int a){
    	syso...(a >= 0 ? a : -a);
	}
	 public int abs(int a){
        int res = a >= 0 ? a : -a;
    	return res;
	}
 	public int abs(int a){
    	return Math.abs(a);
	}
8.
    全局  		局部
    有默认值      没有默认
    有权限		   没有
    类里方法外     方法里
    堆			 栈
    对象			{ }

9.
    this.全局
10. ys.max(2,6);    

```



### 9-7

```java
1. 
[返回值 =] 对象.方法(实参); 形参 = 实参  int a = 10;

public void test(int a){
	
}

test(10);

类里两个方法互相调用 a()调用b() ，必须先执行b方法，再执行
public void a(){
	//this.b();
    b();
}
public void b(){
	
}
递归调用 【方法自己调用自己】

2.
    public class Product{
        public int no;
        public String name ;
        public double price;
    }
3. 创建对象
    Product latiao = new Product();

4. 创建商品数组
   Product sp[] = new Product[3];

5. sp[0] = latiao;   //sp[1]  null 
    
6.
    public boolean find(String name){
    	for(int i = 0; i < sp.length;i ++){
            if(sp[i].name.equals(name)){
                return true;
            }
        }
    	return false;
	}
7.
   sp[0].price =  5;

8.
    byte  1
    short 2
    int   4
    long  8
```

### 9-8

```java
1.
public int sum(int a,int b){
	return a + b;
}
public int sum(int c,int d){
	return c + d;
}

2.
public int sum(int a,int b,int c){
	return a + b + c;
} 

3. 
    sum(1,2,3);

4. 
    public class Customer{
        public String tel;
        public String address;
        public String name;
        //...
    }
 	public class Goods{
        public String no;
        public double price;
        public String name;
        public int count;
        //...
    }
    public class MyOrder{
        public int oNo;
        public String time;
        //订单状态
        public String state;
        //客户
        public Customer c;
        //商品数组
        public Goods[] goods ;
    }

5. 订单数组
    MyOrder[] o = new MyOrder[2];

6. 订单对象
    MyOrder o1 = new MyOrder();
    o1.oNo = 1;
	o1.time = "2023-9-8 9:13";
	o1.state = "已发货";

7. 
    全局和局部：  默认值 权限  堆、栈   类、{}   对象、{}  

8.
    toString()

9.
    for(MyOrder i : o){
        ssssss(i);
    }
10. 半编译半解释
    

```

### 9-11

```java
class A{
    A(){
        
    }
    
}
public class Emp{
	public int eNo;
    public String eName;
    public double eSal;
    
    public Emp(){
        
    }
    
    public Emp(int eNo,String eName){
        this.eNo = eNo;
        this.eName = eName;
    }
}
//使用构造方法创建对象
Emp ys = new Emp(1,"ys");
//对象数组
Emp[] e = new Emp[2];

e[0] = ys;

//重载
方法重载： 方法名相同，但是参数不同【个数，顺序，类型】

//可变长参数
public int getMin(int...a){
    int min = Integer.MAXVALUE;//整型int最大值  
    for(int i = 0; i < a.length;i ++){
        if(min > a[i]){
            min = a[i];
        }
    }
    return min;
}    

//构造        普通
  没有返回     有返回声明，void 、 int
  初始化       自定义
  JVM         自己对象.
  new 1次      n次
  隐式         没有
 
对象.方法();

类方法互相调用 【static调用static】
    
递归 递归结束条件   死递归
```



### 9-12

```java
1. import     n个导入
    
2. java.lang  核心包 String Object  System  线程  异常  Math Integer 
    
3. java.io    文件输入输出  FileInputStream  FileOutputStream
    
4. 关联： 1对1  1对多 多对多
    
5. package xxx.xxx;

6. 
    public class Goods{
        public int gNo;
        public double gPrice;
        public Goods(){
            
        }
        public Goods(int gNo){
             this.gNo = gNo;
        }
        //7
        public Goods(int gNo,double gPrice){
            this.gNo = gNo;
            this.gPrice = gPrice;
        }
    }
8.
    Goods g = new Googs(1,80);

9.
    Goods[] goods = new Goods[4];

10. goods[goods.length - 1] = g;
```





### 9-13

```java
1. 封装 继承 多态

2. 私有化 private  本类

3. 
  member manager director vp  
 public class Manager{
    private int no;
    private String name;
     
    public Manager(){
        
    }
     
    public void setName(String name){
        this.name = name;
    }
     
    public String getName(){
        return name;
    }
 }

5. java.util 工具包 集合 日期 随机数 Scanner Arrays ....

6. 属性赋值
    
   1.默认值
   2.声明时赋值
   3.构造方法
   4.setXX()
    
7.import java.*;

8. 可变长参数
    
    public double getSum(double...d){
       double sum = 0;
       for(double i : d){
           sum += i;  // sum += d[i];
       }
    	return sum;
    }

9.
    关联  1:1  1：n  m:n
        
10.
    public Manager(){
        
    } 
11. 
    封装作用： 提高代码的安全性，封装属性，方法，构造（情况少）
```





### 9-14

```java
1. private   本类
   default   本包
   protected 同包友好，跨包继承
   public    整个项目
    
2. 类 ： public  缺省

3. 重写原则： 子类覆盖父类方法
    1.方法名相同
    2.参数相同
    3.返回类型相同
    4.权限不降低 private <default<protected<public   
4.
    extends
5.  Object 
    
6.  子类可以继承： 非私有属性 方法 
    不可以继承： 私有的  构造方法    
7.  java继承关系： 单继承  代码重用    
8.  重载： 方法多样化设计
    1.方法名相同
    2.参数不同
    3.其他不限制   
9. 构造 ： 可以重载  不能重写
    
10. 方法递归： 方法自己调用自己，一定终止条件    
```



### 9-15

```java
1. 重载和重写

重载       重写
参数不同    相同
返回值不限  相同
权限不限    不能降低
n次         1次
本类、子类   子类

2. 顺序 ： 祖先Object  > 父类 > 子类

3. super() 空构造
   super(实参)； 带参数构造
   
4.
 super.属性  super.方法()
 super(); 构造
 
 
5. 类和类【接口】关系
   关联 has a  继承  is a 实现  组合 聚合  依赖 use a 
   
 
6. 
多态条件：
	1. 继承，父类多个子类
	2. 子类必须方法覆盖
	3. 对象向上转型   父类 对象 = new 子类();
   	   
   	   父类的变量引用子类的实例化对象
   	   
   	   子类实例化对象赋值给父类变量
   
7.
多态好处：
1.灵活，方便代码扩展
2.低耦合

8.
多态对象： 只有父类的成员，子类覆盖方法后，执行子类的

9.
public class Student extends Person{

}

10.
    private default protected public 
```



### 9-18

```java
1.
public class Food{
	private String name;
	private double price;
}

2.
public class Drink extends Food{
    
}

3.
    private  本类
    缺省      本包
    protected 本包，跨包，继承关系
    public    公开
    
4.
    重写【覆盖 @Override】 
   方法名相同，参数相同，返回值必须相同，权限不能降低
   1次 子类覆盖父类 不能抛更多异常
    
5.
    多态条件：
    1.继承，多个子类
    2.方法覆盖
    3.向上转型  父类 对象 = new 子类();

6. instanceof
    
7.
  子类 对象 = （子类）多态对象;  

8.
   super:
	super.父类方法()
    super(); 调用父类构造
    super(参数); 

9.类关系： 继承 实现 依赖  关联  组合  聚合
    
10.
    封装  数据安全性
    继承  代码重用
    多态  代码灵活性 降低耦合   高内聚 低耦合
    
    JS jQurey  bootstrap  vue angualr 
    
    maven 构建企业项目 仓库类型
    中央仓库     阿里镜像     私服 ：企业仓库    本地仓库  
```



### 9-20

```java
1. instanceof    变量 instanceof 类   布尔类型 

2.
abstract 可以修饰类 方法  不能属性，构造，变量

3.
public abstract void swim();

4.
final 
    变量  常量，不能改值  全局变量必须给初始值
    方法  不能重写
    类    不能有子类
    
5. 
    静态属性     实例属性
    静态区			堆
    类本身         对象
    1份 共享       n份
    类加载初始化    创建对象
    类.             对象.

6. 静态代码块只执行1次  类加载的
    static{
    
    }
	静态代码块 > 实例代码块 {} > 构造
7. 向上转型   父类 多态变量 = new 子类();
8. 向下转型   子类 变量 = (子类)多态变量 ;

9.static 属性 方法 内部类
10.
    抽象类有构造 ，子类继承调用 
    
    子类继承父类一定会调用父类构造方法： 祖先Object > 父 > 子
    
    public abstract class  Person extends Object{
        //public Person(){
        //    super();
       // }
    }
	public class Student extends Person{
       // public Student(){
       //     super();
       // }
    }
```



### 9-21

```java
1.
public interface IVehicles{
    
} 

2.
public interface ICar extends IVehicles{
    
}

3.
public class Benzi implements ICar{
    
}

4.
    接口属性： 公开 静态常量 public static final
    
5.
    接口        抽象类
    interface  abstract class
    无构造      有构造
    抽象方法    抽象+非抽象
    public     任意
    静态常量    任意
    多实现      单继承
    
6.  接口作用：
        1.解决单继承
        2.设计层面和实现层面分离，解耦
        
        
7.
    静态方法调用 ： 必须调用静态的成员【属性，方法】
        
8.
    静态属性 
        静态区 1份拷贝 属于类本身，多个对象共享资源  类.  对象. 类加载的时候 初始化1次
        
    实例属性 
        堆 n个拷贝 属于对象的，每个对象一份，对象.  创建对象的初始化
        
9.
    public abstract void eat();
        
10.
    重载        重写
    overload   override
    参数不同    参数相同
    返回值不限  相同
    权限不限制  不能降低
    n次        1次
    父类子类    子类
    无限制      异常不能更多
    
```



### 9.22

```java
1.
public interface IWeapon{
	void attack();
}
class Gun implements IWeapon{
     public void attack(){
        System.out.println("tututu");
    }
}

2.
IWeapon w = new IWeapon(){
    public void attack(){
        System.out.println("tututu");
    }
    
} ;

3.
IWeapon w = () -> System.out.println("tututu");
w.attack();

4.
public enum MethodType{
    GET,POST;
}

5.MethodType.GET
    
6. implements 多实现
    
7. extends 多继承
    
8. 接口属性 ： public static final
    
9. 异常顶级根 Throwable
    		 异常 Exception 
    		 错误 Error
    
10. 编译时异常
    运行时异常 
    
    数组下标越界异常 
    数学异常 
    类型转换异常  ClassCastException  多态
    空引用 
    数字转换异常 
```



### 9.25

```java
1.
throw  方法内部创建一个异常 抛出  异常对象
throws 方法向外抛出异常 抛出异常类型 
    
    
2.
    try  catch finally
        
3.
    Throwable
        Exception 
        	RuntimeException  运行时异常
        Error 
        
4.
    public interface  IUSB{
        void work();
    }

5.
    public enum USBType{
    	USB2.0,USB3.0;
	}
6.
    IUSB usb3 = new IUSB(){
    	 public void work(){
             //....
         }
	};

7. IUSB usb2 = () -> {Sout....};

8.
    接口   抽象类
    无构造  构造
    public 任意
    静态常量 任意
    抽象方法 任意
    多实现  单继承
    
    
9.
    static{
    
    }
	类加载 执行1次   静态代码块 > { } >构造
        
10.
     多态：
        1. 继承/实现  多个子类/实现类 
        2. 覆盖方法
        3. 向上转型  
        
        		接口  变量 = new  实现类();
```





### 9.26

```java
1.
String str = "abc";

String str2 = new String("abc");


2.
    str.length();

3.
    str.split(",")
    
4.
    substring(0,2);

5.
    str.charAt(str.length() - 1);
    
    str.substring(str.length() - 1);

6.
    str.replace("a","*")
    
7.
    str.trim();

8. contains("b") boolean
   indexOf("b")  int
   lastIndexOf()
    
9. 判断某个字符串是否是回文串
 
```





### 9.27

```java
1.
qq邮箱正则
"^[1-9]\\d{4,}@qq.com$"   
2.
str.matches("^[1-9]\\d{4,}@qq.com$")       
3.
String 不可变字符串
可变字符串    
StringBuffer  线程安全 单线程 同步的 效率低 速度慢
StringBuilder 线程不安全 多线程 不同步的 效率高 速度快  推荐
    
    
4.append(内容)
    
5.reverse() 翻转
    
6.Math.floor() 向下取整 

7.Math.pow(2,5) 
    
8.(char)((90 - 65 + 1)* Math.random() + 65)
    
9.insert(下标，内容) 
    
10.
    throw  手动产生异常对象抛出
    throws 方法向外抛出异常类型，不解决
   
```





### 9.28

```java
1.😊
ArrayList  线性集合，线性数组，元素挨着的，方便查找不方便更新
LinkedList 链式集合，链表，元素不是挨着，通过元素地址链接，方便更新，不方便查找


2.
HashMap  线程不安全，不同步，效率高 ；  允许null的键和值
Hashtable 反之
    
    
3. Collection 
List    有下标，允许重复
Set     没有下标，不允许重复
    
4.
    Collection  存储值
    Map		存储键值对  key-value
    
5.
    集合大小  size()
    数组 .length
    字符串 length()
    文件  length()
6.
    尾部添加  add() 
    
7.
    集合删除元素 remove()
    文件删除  delete()
    
8.
    修改元素  set(下标，元素)
    
    
9.
    StringBuilder  线程不安全 多线程，效率高  
	StringBuffer 反之
    
    
10.
    append() 字符串尾部添加
```





### 10.10

```java
1. List接口实现类

ArrayList  线程不安全，不同步，效率高
Vector     线程安全 同步
    
    
2. String 正则
    
    matches("^\\d{6}$")
    
    
3. java.util
   Collections 集合帮助类，提供操作集合的各种方法 排序 最大值 ...
    
   Collection  集合上层接口,子接口 Set List ...
    
4.
  Exception  >  Throwable 
  Error
    
  运行时异常
    	数组下标越界
    	空引用
    	数学异常
    	数字转化异常  
    	类型转化异常
    	...
  编译时异常
    	文件未找到
    	数据库异常
    	IOException
  		...
    
5.
    set(下标，元素)
    
6.
    iterator();

7.  next()
    
8.  hasNext();

9.  add()
    
10. Math.floor(10.5);

```



### 10.11

```java
1.
集合上层接口
Collection   存储数值 value
Map   存储键值对 key-value

2. 
Collection 集合上层接口，List，Set子接口
Collections Collection集合的帮助类

3.
Collections.sort(集合)
Collections.sort(集合，比较器)

4.
Comparable 自然排序 固定机制 lang  compareTo()
Comparator 每次定义比较器，灵活，但是比较器比较机制  util  compare()

5.
Arrays.asList()

6.
Map集合  put(key,value); 添加

7.
    remove(key)
    
8.
    获得所有键 keySet();

9.
    iterator();


10.
    TreeSet<String> tree = new TreeSet<String>((o1,o2) -> o2 - o1);

11. List集合 add(value)
```



### 10.13

```java
1.
创建系统当前时间
Date date = new Date();

2.格式化日期
SimpleDateFormat sdf = new  SimpleDateFormat ("yyyy-MM-dd");
sdf.format(date);

3.
泛型体现：
    泛型接口 泛型类 泛型方法
    
    
4.好处
    1. 减少强制类型转化
    2. 类型使用安全
    3. 灵活，性能高，类型参数化
 
5. 
    put(k,v)
    
6,
	Collection  集合上层接口 ，List/Set   上级父接口  Iterator
    Collections 集合帮助类，集合方法
        
        
7，
    Comparable  lang  自然排序接口 compareTo  固定排序方式 ，不灵活
    Comparator  util  比较器接口  compare  灵活的邪恶比较器 每次提供比较机制
        
        
8.
    HashSet  无下标  不能重复 哈希表
    TreeSet  不能重复  可以排序 红黑树
        
9.
    Double.parseDouble("12.56")
        
        
10.
    iterator() ;

	hasNext();
    next();
	remove();
 	
        
```





### 10.16

```java
1.
	TreeSet<Integer> t = new TreeSet<Integer>(new Comparator<Integer>(){
        public int compare(int o1,int o2){
            return o2 - o1;
        }
    });

TreeSet<Integer> t2 = new TreeSet<Integer>((o1,o2) -> o2 - o1);


2.
    List<String> list = new ArrayList<String>();
	//获得迭代器方法
	Iterator it = list.iterator();
	while(it.hasNext()){
        //获得打印
        sout....(it.next());
    }

3. 
    HashMap<String,String> map = new HashMap<String,String>();
	
	map.put("name","ys998");
	map.put("pass","123456");

4. Date d = new Date();
SimpleDateFormat f = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
f.format(d);


5.
    File f = new File("D:\\1.txt");
	
6.  f.createNewFile();

7.
    mkdir() 创建文件夹 父目录存在
    mkdirs() 一并创建 父目录可以不存在
    
    
8.  listFiles(FileFilter f) //accept()
    dir.listFiles( f -> f.getName().endsWith(".png"));


9.
    字节输入流
    FileInputStream fis = new FileInputStream("");
    read()
        
        
10.
        泛型 ： 类型参数化，将数据类型像参数一样传递
        
        1.灵活 性能高
        2.不需要强制转化
        3.类型安全
    
	
```





### 10.17

```java
1.

序列化： 将JAVA对象数据写入到文件中，永久保存，以防止垃圾回收
反序列化： 将文件中对象信息读取出来

作用： 对象持久化


2.
转换流
InputStreamReader ir = new InputStreamReader(字节流);


3.Serializable接口 序列化标志

4.transient 序列化排除属性

5. 
缓冲
BufferedWriter bw = new BufferedWriter(new FileWriter("D:\\1.txt"));

6.
    数组变集合
    
    List Arrays.asList();



7. Map
    HashMap   红黑树 数组 链表   线程不安全  效率高   允许null键和值
    Hashtable 反之

    
8.
    Comparable lang  compareTo()  自然排序  固定排序机制 不灵活
    Comparator util  compare() 定制比较器，灵活，每次都给定排序机制
    
    
9.
    PrintWriter
    
    好处:
	1.自动创建文件  2.自动刷新  3.自带缓存  4.自动换行 println()

10.
    HashSet 去重原理： HashSet覆盖 hashCode()  equals();

//去重机制
package com.cl.io;

import java.io.Serializable;
import java.util.Objects;

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
	public Student() {
		super();
	}
	@Override
	public int hashCode() {
		return Objects.hash(sno,name);
	}
	@Override
	public boolean equals(Object obj) {
		Student s = (Student)obj;
		if(s.sno == this.sno && s.name.equals(this.name)) {
			return true;
		}else {
			return false;
		}
	}	
}

public class TestSet {
	public static void main(String[] args) {
		HashSet<String> set = new HashSet<String>();
		
		set.add("jack");
		set.add("rose");
		set.add("jack");
		set.add("tom");
		
		
		HashSet<Student> set2 = new HashSet<Student>();
		
		set2.add(new Student(1, "jack"));
		set2.add(new Student(1, "jack"));
		System.out.println(set2);
	}
}
```





### 10.18

1.

```

进程  应用程序运行相关指令，需要开辟内存，内存消耗，独立运行的最小单元
线程  进程会包含多个线程，线程是一条程序控制流，不需要开辟内存 
```

2.创建线程

```
Thread 类
Runnable接口
```

3.状态

```
新建 就绪 执行 阻塞 终止结束
```

4.执行线程

```
run()
```

5.

```
sleep()  线程休眠，休眠结束自动恢复就绪，让出cpu给任意优先级线程
yield()  线程暂停，时刻恢复就绪，让出cpu给更高优先级线程

```

6.锁

```
synchronized 锁  同步锁
		同步块
		同步方法
		
		结束后才会释放锁
 
lock()  jdk5+
		随时释放 unlock()
		灵活，性能高，分类适用于不同情况
```

7.死锁

```
死锁： 两个线程临界资源，A，B线程分别获得临界资源一部分，同时两个线程都不释放资源，进入僵持状态，死锁。
```

8.打印流

```
PrintWriter  pw = new PrintWriter();
```

9.对象持久化  Serializable     transient

```
序列化  将对象写入文件，持久保存
反序列化 从文件中将对象读出来 
```

10.字符串查找

```
indexOf()
contains()
```

截取： substring()  替换  replace()  分割split() 比较 compareTo()  equals()   正则 matches()


## Oracle

### 第一章  数据库基本常识

### 1 数据库的相关概念

```
DB  database  数据库  

DBMS 数据库管理系统

DBA  数据库管理员

DBS  数据库系统
```

![](img\1.png)

###  2 数据库的分类

```
关系型数据库  ：  使用二维表存储数据，操作  sqlserver  mysql  oracle  DB2 

非关系型数据库 ： 使用键值对存储数据， 操作  mongodb  redis 
```



关系型数据库: 使用二维表存储数据，对数据进行CRUD（增删改查），使用SQL语言。

SQL语言 ： 结构化的查询语言【不是面向对象】，对DB进行操作。

```
DQL		数据库查询语言

DML     数据库操作语言 

DDL     数据库定义语言 

DCL     数据库控制语言  

```



| 数据库    | 优点                                                     | 缺点                                     |
| --------- | -------------------------------------------------------- | ---------------------------------------- |
| mysql     | 开源的，免费的，灵活高，适合中小型企业项目，方便数据移植 | 安全性差<br />数据存储量小<br />并发性差 |
| sqlserver | 微软产品 ，网络数据库 并发性和数据访问量可以             | 不能跨平台，受限于windows                |
| oracle    | 甲骨文产品，安全性高，数据量大，并发性强，跨平台         | 收费，成本消耗 <br />DBA操作复杂         |
| DB2       | IBM产品，功能巨牛                                        | 灵活性差，细节不足                       |





### 3 数据建模【后续讲解】

### 4 表的相关内容

```
表 ： 关系 
行 ： 记录 ，元组
列 ： 属性 ，分量 ，字段 
主属性： 主键，唯一决定表数据 ，学生表 学号  
域 ： 字段的范围 
```

### 5 Oracle相关内容

> 现为全球最大数据库软件及服务供应商、全球第二大软件供应商

#### 5.1 版本

```
ORACLE8i/9i:  i是Internet  
ORACLE10g 11g ： grid 网格计算 多点应用集群
ORACLE11i ： 电子商务智能

Oracle12c .... c cloud 云计算

```



#### 5.2 客户端 服务端

```
服务端 ：
	服务端口: 1521
	服务协议: TCP/IP
	OracleOraDb10g_home1TNSListener
 	OracleService数据库名

客户端:
	sqlplus
	sqlplusw
	isqlplus 
	
	第三方： plsqldeveloper 
```



#### 5.3 用户信息

```
sys  超级管理员  admin

system 普通管理员 admin

scott 普通用户  tiger
```



#### 5.4 数据表类型

```
数值型		
		Number
			整数 Number(4)
			小数 Number(6,2)  6 总位数 2 小数位数  4整数型

字符串
		Varchar2(10)
		Char(10)

日期型	  Date
		Datetime
```



###  第二章 DQL 

> DQL： 数据查询语言， 简单查询，条件筛查， 排序， 分组查询，表连接查询 ， 子查询。

### 1.简单语法查询

#### 1.1 查询语法

```sql
SELECT	*| [DISTINCT] 列名1,列名2  或 表达式 [别名]
FROM	表名;
```

注意：

1.关键字，表字段之间空格

2.可以在合适的子句换行，建议一条子句一行

3.；作为sql语句的结束

4.不区分大小写，建议：关键字大写，表和列小写

5.注释

```
单行 -- 
多行 /* */
```



语法：

1.SELECT 关键字  查询内容  FROM 从哪张表

2.*查询所有的列 

3.抽取个别的列，使用，隔开,需要计算可以形成表达式

4.DISTINCT去重关键字

示例：

```sql
-- 查询两个表的全部字段数据
SELECT * FROM emp;

SELECT * FROM dept;

-- 查询员工表编号和薪资
SELECT empno,sal
FROM emp;

-- 查询员工编号，姓名，年薪
SELECT empno,ename,sal*12 年薪
FROM emp;

-- 员工表的部门信息
SELECT DISTINCT deptno
FROM emp;
```



练习：

```sql
-- 1. 查询薪资等级表全部数据
SELECT * FROM salgrade;
-- 2. 查询员工编号，薪资，入职时间
SELECT empno,sal,hiredate FROM emp
-- 3. 查询员工的姓名，年薪和年奖金
SELECT ename,sal*12 年薪,comm*12 年奖金
FROM emp
-- 4. 查询员工表中的职位【去重】
SELECT DISTINCT job
FROM emp
```

 

#### 1.2 空值

> 空值 ： 不是0 不是空串 不是空格 是未定义
>
> 注意： 包含空值的运算都会变成空值

```sql
-- 查询姓名，年收入，对于没有奖金的年收入空
SELECT ename,sal,comm,(sal+comm) * 12 收入
FROM emp;
```

> 空值需要处理，再做运算
>
> nvl(列，替换值) ； 列不是空，按照原本值，是空值，按照替换值计算

```sql
-- 查询姓名，年收入
SELECT ename,sal,comm,(sal+nvl(comm,0)) * 12 收入
FROM emp;

-- 2
SELECT NVL(NULL,2)
FROM dual;

-- 1
SELECT NVL(1,2)
FROM dual;
```



#### 1.3 别名 

> 为表达式定义别名，重新定义名字

```sql
表达式/列  别名

表达式/列 AS  别名
```

注意：

1.别名英文自动大写

2.强制大小写和符号需要添加"" 



#### 1.4 字符串

```sql
字符串 ''  

字符串连接 || 

SELECT 'welcome' || 'ys' AS info
FROM dual;

```

示例： xxx worked as xxx ,earns xxx

```sql
SELECT ename || ' worked as ' || job || ' ,earns ' || sal AS info
FROM emp;

```

练习：

```sql
-- 1. 查询员工编号，入职时间和季度薪资【包含奖金】，定义别名
SELECT empno,hiredate, (sal+NVL(comm,0))*3 AS "aSal" 
FROM emp;


-- 2. 查询员工信息按如下： xxx 就职于 xxx部门  入职于 xxx 定义别名

SELECT ename  || '就职于' || deptno || '部门 入职于' || hiredate info
FROM emp;
```



### 2 .条件筛选查询

#### 2.1 查询语法

```sql
SELECT	*| [DISTINCT] 列名1,列名2  或 表达式 [别名]
FROM	表名
WHERE   条件+ 
```

##### 1.等值条件：

```sql
SELECT	*| [DISTINCT] 列名1,列名2  或 表达式 [别名]
FROM	表名
WHERE   列 = 值;
```

注意：

```
1. 等值比较的是数字类型 直接写
2. 等值比较的是字符串类型 使用''
3. 等值比较的是日期类型 不仅使用'' 格式注意 DD-MON-RR  
```

示例：

```sql
-- 查询20部门的员工信息

SELECT *
FROM emp
WHERE deptno=20;

-- 查询smith的信息
SELECT *
FROM emp
WHERE ename = 'smith'


-- 2021/10/1 入职的员工信息
SELECT *
FROM emp
WHERE hiredate = '1-10月-2021'
```

##### 2.不等值条件：需要比较

##### 3.运算符

| 运算符         | 包含                             | 注意               |
| -------------- | -------------------------------- | ------------------ |
| 算术运算符     | +  -  *  /  （）                 | /不会取整  %不可用 |
| 比较运算符     | =  > >= < <=  !=  <>             | <>不等于  = 相同   |
| 特殊比较运算符 | LIKE  IN   BETWEEN AND   IS NULL |                    |
| 逻辑运算符     | not   and  or                    |                    |
| 特殊运算符     | \|\|                             |                    |

注意： 比较类型可以数字或日期。

示例：

```sql
-- 查询薪资4000-6000的员工信息

SELECT *
FROM emp
WHERE sal >= 4000 AND sal <= 6000;


-- 查询10或30部门员工


SELECT *
FROM emp
WHERE deptno=10 OR deptno=30


-- 查1981年入职员工

SELECT *
FROM emp
WHERE hiredate >= '1-1月-1981' AND  hiredate <= '31-12月-1981'
```

练习:

```sql
-- 查询10或30部门中薪资高于4000员工信息

SELECT *
FROM emp
WHERE (deptno=10 OR deptno=30 ) AND sal > 4000;


-- 查询领导是7698，且1981之后入职的员工

SELECT *
FROM emp
WHERE mgr = 7698 AND hiredate > '31-12月-1981'
```



##### 4.模糊查询

字符串类型的模糊匹配： 以xx开头  以xx结尾 包含xxx

```sql
字段  LIKE '%_'

	% 占位0个或多个字符
	— 占位1个字符
	
	NOT LIKE ''
```

示例：

```sql
--查询员工表姓 杨员工

SELECT *
FROM emp
WHERE ename LIKE '杨%'



--查询员工表名字包含S
SELECT *
FROM emp
WHERE ename LIKE '%S%'

--查询员工表名字第二个字母A


SELECT *
FROM emp
WHERE ename LIKE '_A%'


-- 查询员工表名字不包含M


SELECT *
FROM emp
WHERE ename  NOT LIKE '%M%' AND ename  NOT LIKE '%m%'
```

练习：

```sql
-- 1.查询不在20部门 且名字中包含A字母的员工
SELECT *
FROM emp
WHERE deptno != 20 AND ename LIKE '%A%'

-- 2.查询名字倒数第二个字母是L，且薪资高于3000
SELECT *
FROM emp
WHERE ename LIKE '%A_' AND sal  > 3000
-- 3.查询名字中包含A和E字母的员工信息

SELECT *
FROM emp
WHERE ename LIKE '%A%' AND ename LIKE '%E%';
```

##### 5.区间查询【闭区间】

```sql
列  between 值1  and  值2    

列  not between 值1  and  值2   
```

示例

```sql
-- 查询3000-5000员工

SELECT *
FROM emp
WHERE sal BETWEEN 3000 AND 5000;


-- 1981-1987入职的员工

SELECT *
FROM emp
WHERE hiredate  BETWEEN  '1-1月-1981' AND '31-12月-1987'
```



##### 6.集合

```sql
列 in (值1，值2...)  列满足与其中一个值相等即可

列 not in (值1，值2...)  列满足与其中一个值相等即可
```

示例：

```sql
-- 查询10，20员工信息
SELECT *
FROM emp
WHERE deptno IN(10,20)
```



##### 7.判断空值

```sql
列  is null ;

列  is not null;
```

示例：

```sql
-- 没有奖金的员工信息

SELECT *
FROM emp
WHERE comm IS NULL;

-- 没有职位的员工信息

SELECT *
FROM emp
WHERE job IS NULL;


-- 查询有奖金的员工
SELECT *
FROM emp
WHERE comm IS NOT NULL;
```



练习：

```sql
-- 1. 查询没有上司，且薪资在3000-5000之间的员工信息

SELECT *
FROM emp
WHERE mgr IS NULL AND sal BETWEEN 3000 AND 5000;



-- 2. 查询20或30部门，有奖金的员工信息
SELECT *
FROM emp
WHERE comm IS NOT NULL AND deptno IN(20,30)


SELECT *
FROM emp
WHERE comm IS NOT NULL AND (eptno =20 OR deptno=30);

-- 3. 查询Salesman或manager这些员工名字中包含S

SELECT *
FROM emp
WHERE ename LIKE '%S%' AND job IN('SALESMAN','MANAGER')

-- 4. 查询在1987年入职，薪资4000以上的员工信息
SELECT *
FROM emp
WHERE sal > 4000 AND hiredate BETWEEN  '1-1月-1981' AND  '31-12月-1981'
```

优先级

![](img\2.png)



#### 2.2 排序查询

语法规则

```sql
SELECT	*| [DISTINCT] 列名1,列名2  或 表达式 [别名]
FROM	表名
WHERE   条件1 AND/OR 条件2
ORDER BY  列 [ASC/DESC] ,列2 [ASC/DESC]
```

注意：

1.order by 根据某字段排序

2.省略ASC  DESC，默认升序，DESC 降序  ASC 升序 

3.如果需要多个列实现排序，逗号隔开

4.排序是最后一步，排序的时候可以写别名

示例：

```sql
-- 查询20或30员工薪资，薪资降序排列

SELECT *
FROM emp
WHERE deptno IN(20,30)
ORDER BY sal DESC

-- 查询有奖金的员工的年薪，按年薪降序

SELECT ename,(sal+comm) * 12 yearsal
FROM emp
WHERE comm IS NOT NULL
ORDER BY yearsal DESC;


-- 查询名字A员工信息，按照薪资升序，如果薪资相同按照名字降序


SELECT *
FROM emp
WHERE ename LIKE '%A%'
ORDER BY sal DESC,ename ASC

```

练习：

```sql
-- 1.查询领导是7698的员工的信息，按照入职时间降序排列
SELECT *
FROM emp
WHERE mgr = 7698 
ORDER BY hiredate DESC;

-- 2.查询没有奖金的员工的日薪【30天】，按照日薪降序排列
SELECT ename,sal/30 AS daySAl
FROM emp
WHERE comm IS NULL 
ORDER BY daysal DESC;
-- 3.查询1981年入职，薪资在2500-4000的员工信息，按照薪资降序排列，相同的薪资按照员工号升序排列
SELECT *
FROM emp
WHERE sal BETWEEN 2500 AND 4000 AND hiredate BETWEEN '1-1月-1981'AND '31-12月-1981'
ORDER BY sal DESC,empno 


-- 4.查询7698和7369两位领导的下属信息，按照年薪排序

SELECT ename,(sal+NVL(comm,0)) * 12 yearsal
FROM emp
WHERE mgr IN(7698,7369)
ORDER BY yearsal
```

#### 2.3 函数

> y=f(x) ,输入多个值，输出一个值。

##### 1.函数的分类

```
单行函数  对一行数据操作，返回一个结果
	
	字符串函数
	数字函数 
	日期函数 
	转换函数
	通用函数

多行函数 对多行数据操作，返回一个结果
	
	求和函数
	最大值函数
	最小值函数
	平均值函数
	计数函数
	标准差函数
```

##### 2.字符串函数

> 数据库字符串 ''  ,类比String相似

![](img\3.png)

大小写控制

```sql
LOWER(字符串)  小写

UPPER(字符串)  大写

INITCAP(字符串) 首字母大写
```



示例：

```sql
SELECT LOWER('helloWorld')
FROM dual;

SELECT UPPER('helloWorld')
FROM dual;

SELECT INITCAP('hello World')
FROM dual;

-- 查询smith的信息，不区分大小写

SELECT *
FROM emp
WHERE LOWER(ename)='smith';

```



字符控制： 字符串起始下标 从1开始 

```sql
LENGTH(字符串)  字符串长度

SUBSTR(字符串,起始位置，截取长度)  截取，截取位置可以是负数 倒着数 

INSER(原字符串，要查找的子串)  不为0   字符串查找

REPLACE(原字符串，old，new) 替换 

LPAD(原字符串,总位数,填充日容) 左侧填充内容达到总位数
RPAD()

TRIM(字符串)  字符串两侧空格去除
TRIM(单个字符 FROM 字符串) 

LTRIM(字符串,去除字符集)
```

示例：

```sql
SELECT LENGTH('helloWorld')
FROM dual;


-- 查询名字是五位员工信息

SELECT *
FROM emp
WHERE LENGTH(ename) = 3



-- 获得员工的第一个字符

SELECT SUBSTR(ename,1,1) ,ename
FROM emp


-- 获得员工名字后两个字母

SELECT SUBSTR(ename,LENGTH(ename) - 1 ,2) ,ename
FROM emp

SELECT SUBSTR(ename,-2 ,2) ,ename
FROM emp


-- 查找名字包含N

SELECT *
FROM emp
WHERE INSTR(upper(ename),'N') != 0




-- 查找员工 姓名A替换*

SELECT replace(ename,'A','*')
FROM emp

-- 查询员工姓名，左侧填充五个*

SELECT LPAD(ename,LENGTH(ename)+5,'*')
FROM emp;

-- 总长度10位，员工薪资右侧填充$

SELECT RPAD(sal,10,'$')
FROM emp;

-- 员工薪资左侧填充$ 姓名的长度个数

SELECT ename,LPAD(sal,LENGTH(sal)+LENGTH(ename),'$')
FROM emp;


SELECT 'xxx' || TRIM('   sweh se   ') || 'yyyy'
FROM dual;


SELECT  TRIM('a' FROM 'ajahellowwaaa')
FROM dual;


SELECT  LTRIM('aahellowwaaa','a')
FROM dual;

```



##### 3.数字函数

```
ROUND() 四舍五入
ROUND(数值)  四舍五入到整数位
ROUND(数值,0)  同上
ROUND(数值,1)  
ROUND(数值,2) 保留到小数点2位
ROUND(数值,-1)  四舍五入到十位

TRUNC() 截断，不考虑四舍五入

Ceil()
floor()

MOD(值1,值2)  求余数  值1取余数值2 

```

示例：

```sql
SELECT ROUND(-2.5)
FROM dual;


SELECT ROUND(10.55)
FROM dual;

SELECT ROUND(10.55,1)
FROM dual;

SELECT ROUND(10.556,2)
FROM dual;

SELECT ROUND(54.556,-1)
FROM dual;


SELECT TRUNC(54.556,2)
FROM dual;


SELECT floor(12.56)
FROM dual;
```

##### 4.日期函数

> 默认的日期格式 ：  DD-MON-RR  
>
> 系统当前时间  ：  SYSDATE

```
SELECT SYSDATE
FROM dual;
```

日期之间的运算：

```
1. 日期1 -  日期2 =  相差天数

2. 日期  +-  数字 = 日期  在日期上加减天数
```



日期函数：

```sql
Months_between(日期1,日期2)  日期差月份数

add_months(日期，数字)  日期上加减月份

last_day(日期)  返回当前日期所在月份最后一天 

next_day(日期,指定)  数字  '星期一' 
```



示例：

```sql
-- 获得系统当前时间
SELECT SYSDATE
FROM dual;


-- 查询员工表20部门员工入职天数

SELECT ename,ROUND(SYSDATE - hiredate)
FROM emp
WHERE deptno=20 AND hiredate IS NOT NULL

SELECT SYSDATE - 1
FROM dual;

SELECT * 
FROM emp



-- 查询每位员工入职年份


SELECT ename,ROUND((SYSDATE - hiredate) / 365 )
FROM emp



SELECT ename, round(months_between(SYSDATE,hiredate) / 12)
FROM emp;



SELECT add_months(SYSDATE,-2)
FROM dual;


SELECT last_day(SYSDATE)
FROM dual;


-- 查询每个员工入职的最后一天

SELECT ename,last_day(hiredate)
FROM emp


SELECT ename,hiredate
FROM emp

-- 查询每个月倒数第三天入职的员工信息
SELECT ename,hiredate
FROM emp
WHERE hiredate = last_day(hiredate) -2


SELECT next_day(SYSDATE,1)  -- 1 日 2 一 3 周二 .....
FROM dual


SELECT next_day(SYSDATE,'星期日')  -- 1 日 2 一 3 周二 .....
FROM dual

```



##### 5.转换函数

> 转换字符串和日期，字符串和数字转换。

![](img\4.png)



字符串和日期的转换：

```

to_date(字符串，'日期模式')  将字符串变成日期


to_char(日期,'日期模式')  将日期转换为字符串
```

示例：

```sql
----转换函数
SELECT  (SYSDATE - to_date('2001-10-20','YYYY-MM-DD'))/ 365
FROM dual;

SELECT *
FROM emp
WHERE hiredate='20-10月-2001'



-- 1981年入职

SELECT *
FROM emp
WHERE to_char(hiredate,'YYYY') = 1981
```



![](img\5.png)



![](img\6.png)

练习：

```sql
-- 查询每年上半年入职的员工信息

SELECT *
FROM emp
WHERE to_char(hiredate,'MM') <= 6;

-- 查询15之后入职的员工信息

SELECT *
FROM emp
WHERE to_char(hiredate,'DD') > 15

-- 2023 10 25 公司年会，查询可以参加年会的员工信息

SELECT *
FROM emp
WHERE hiredate <= to_date('2023-10-25','YYYY-MM-DD')

```

字符串和数字的转换：

```
to_char(数字,模式)

to_number()
```

![](img\7.png)



示例：

```sql
-- 将员工表信息查询： 姓名  薪资 如下格式显示 : ￥xxx,xxx,xxx.00

SELECT ename,to_char(sal,'L999,999,999.00') sal
FROM emp;

-- 将员工表20部门员工年薪包括奖金如下 ： $ xxx,xxx.00

select ename,to_char((sal+nvl(comm,0))*12,'$999,999.00')
from emp;
```



##### 6.通用函数

> 通设，处理型函数。处理问题的函数。



```sql
-- 处理空值函数

nvl(字段/列，替换值);

判断第一个参数是否为空，空取第二个参数替换，如果第一个参数不为空，取原本值
nvl 适用于各种数据类型

SELECT NVL(1,2)
FROM dual;

-- A  null  B 1  C 2 

-- 查询员工表数据，职位空 显示 空闲职位
SELECT ename,nvl(job,'空闲职位')
FROM emp;


-- 查询员工表数据，入职时间空，显示下周一


SELECT ename,nvl(hiredate,next_day(SYSDATE,2))
FROM emp

--查询员工信息，没有上司的显示 上司编号是9999
SELECT ename,NVL(mgr,9999)
FROM emp;
--查询员工表信息，将没有入职时间显示本月最后一天

SELECT ename,NVL(hiredate,last_day(SYSDATE))
FROM emp;


```





```sql
-- 分支判断处理
-- case表达式【oracle mysql sqlserver 通用】
	
	--语法1  匹配值，不允许条件
	case 字段
	when 值1  then 结果1
	when 值2  then 结果2
	....
	else 结果
	end 

	--语法2  匹配条件
	case 
	when 条件1  then 结果1
	when 条件2  then 结果2
	....
	else 结果
	end 

-- decode()函数 【oracle使用】

decode(字段,值1,结果1，值2，结果...都不满足值);
```

示例：

```sql
-- 员工表部门  10 很有钱  20  很轻松  30  很忙  其他 其他


SELECT ename,deptno,CASE deptno 
                        WHEN 10 THEN '很有钱'
                          WHEN 20 THEN '很轻松'
                            WHEN 30 THEN '很忙'
                              ELSE '其他'
                                END 部门信息
                                
FROM emp;
          
-- 员工表薪资 1-2000 贫穷  2001-4000  中层   4000-6000 小康  6000+ 富有 

SELECT ename,sal,CASE  
                        WHEN sal BETWEEN 1000 AND 2000 THEN '贫穷'
                         WHEN sal BETWEEN 2001 AND 4000 THEN '中层'
                           WHEN sal BETWEEN 4001 AND 6000 THEN '小康'
                              ELSE '富有'
                                END 收入信息
                                
FROM emp;

SELECT ename,deptno,DECODE(deptno,10,'很有钱',20,'很轻松',30,'很忙','其他') 部门信息
FROM emp;
```

注意：

```sql
-- 查询员工职位等级：

	President  A
	Manager  B
	ANALYST C
	SALESMAN D
	CLERK E
	其他 其他 
	
SELECT ename,job
,DECODE(job,UPPER('President'),'A',UPPER('Manager'),'B',UPPER('ANALYST'),'C','SALESMAN','D','CLERK','E','其他') 信息
FROM emp;
```

函数总结：

```
1，字符串函数  大小写转换  截取 长度 查找 替换 填充 去空格
2. 数字函数    四舍五入 截断  求余数 开方  上取整  下取整
3. 日期函数   系统时间 最后一天 下一个日  相差月份 加减月份 
4. 转换函数   to_char()  to_date() 
5. 通用函数   nvl()  case/decode

```



### 3.表连接查询【重点】

> 表连接涉及将两张【n张】表联合查询。

```
1. 笛卡尔集
2. 等值连接查询
3. 不等值连接查询
4. 自我连接查询
5. 外连接查询
```



#### 3.1 笛卡尔集

> 将A表数据完全的和B表的数据交叉查询。
>
> 特点：没有任何连接条件或连接条件无效
>
> 形成数据： 表1记录 * 表2记录

语法：

```sql
SELECT * | 表1.列，表2.列, 表2.*
FROM  表1, 表2
```



#### 3.2 等值连接

> 使用等值的条件将表连接。

语法：

```sql
SELECT * | 表1.列，表2.列, 表2.*
FROM  表1, 表2
WHERE 表1.列 = 表2.列 AND 条件 + 
```

注意1： 没有冲突的字段可以省略表.列，但是开发建议表.列 提高查询效率

```sql
SELECT ename
FROM emp,dept
WHERE emp.deptno=dept.deptno AND ename LIKE '%A%' AND sal > 2000
```

注意2： 当两表都包含的字段，必须要指定表名

```sql
SELECT ename,emp.deptno
FROM emp,dept
WHERE emp.deptno=dept.deptno AND ename LIKE '%A%' AND sal > 2000
```

注意3： 为了提高查询效率，都在列前面加上表名，会为表添加别名，只能空格别名

一旦使用别名，不允许使用原表名

语法：

```sql
SELECT 别名1.列
FROM  表1 别名1, 表2 别名2
WHERE 别名1.列 = 别名2.列 AND 条件 + 
```

示例：

```sql
SELECT e.ename,d.*
FROM emp e,dept d
WHERE e.deptno=d.deptno AND e.ename LIKE '%A%' AND e.sal>2000
```



练习：

```sql
-- 1. 查询有奖金的员工部门信息
SELECT e.ename,d.*
FROM emp e,dept d
WHERE e.deptno=d.deptno AND e.comm IS NOT NULL

-- 2. 查询10或30部门 薪资3-5k 的员工姓名，部门名称

SELECT e.ename,d.dname
FROM emp e,dept d
WHERE e.deptno=d.deptno AND e.deptno IN(10,30) AND e.sal BETWEEN 3000 AND 5000 
```

总结： N张表 至少N-1个连接条件，连接条件和筛选条件AND间隔

#### 3.3 不等值连接

> 使用不等值连接符将两表数据连接。

语法：

```sql
SELECT 别名1.列
FROM  表1 别名1, 表2 别名2
WHERE 别名1.列 不等于 别名2.列 AND 条件 + 
```

示例：

```sql
-- 查询每个员工薪资，薪资等级
 
SELECT e.ename,e.sal,s.grade
FROM emp e,salgrade s
WHERE e.sal BETWEEN s.losal AND s.hisal 


-- 20 部门员工姓名，薪资，等级以及部门位置
SELECT e.ename,e.sal,s.grade,d.loc
FROM emp e,dept d,salgrade s
WHERE e.deptno=d.deptno AND e.sal BETWEEN s.losal AND s.hisal AND e.deptno=20
```



#### 3.4  自我连接

> 表自己和自己连接。 一张表定义两个别名，代表两个身份。



语法：

```sql
SELECT 别名1.列
FROM  表 别名1，表 别名2 
WHERE  别名1.列 = 别名2.列
```



示例：

```sql
-- 查询员工的姓名，薪资，领导姓名，薪资

SELECT e.ename,e.sal,m.ename,m.sal
FROM emp e,emp m
WHERE e.mgr = m.empno

```

练习：

```sql
-- 1. 查询没有奖金的员工姓名，上司姓名【2】
SELECT e.ename,m.ename
FROM emp e,emp m
WHERE e.mgr = m.empno AND e.comm IS NULL
-- 2. 查询下属比上司工资高员工信息 【2】
SELECT e.ename,e.sal,m.ename,m.sal
FROM emp e,emp m
WHERE e.mgr = m.empno AND e.sal >= m.sal
-- 3. 查询员工和领导工资等级相同的员工信息【4】
SELECT *
FROM emp e,emp m,salgrade s1,salgrade s2
WHERE e.mgr = m.empno AND e.sal BETWEEN s1.losal AND s1.hisal AND m.sal BETWEEN s2.losal AND s2.hisal AND s1.grade=s2.grade
```





#### 3.5   外连接【重点】

> 用于显示不满足等值连接条件的表的数据。
>
> 左外连： 左表是主表，主表完全显示，左侧表数据完全显示【即使不满足连接条件】
>
> 右外连： 右表是主表，主表完全显示，右侧表数据完全显示【即使不满足连接条件】



语法：

```sql
-- 左外连
SELECT * | 表1.列，表2.列, 表2.*
FROM  表1, 表2
WHERE 表1.列 = 表2.列 (+)


-- 右外连
SELECT * | 表1.列，表2.列, 表2.*
FROM  表1, 表2
WHERE 表1.列(+) = 表2.列

-- 左外连
LEFT [OUTER] JOIN
-- 右外连
RIGHT [OUTER] JOIN
-- 满外连
FULL [OUTER] JOIN

```

示例：

```sql
-- 查询员工表员工姓名，部门信息

SELECT e.ename,d.*
FROM emp e,dept d
WHERE e.deptno=d.deptno(+)

-- 查询员工姓名，领导姓名，即使没有领导的员工显示

SELECT e.ename,m.ename
FROM emp e,emp m
WHERE e.mgr = m.empno (+)


-- 查询员工的部门，部门位置，没有员工的部门显示
SELECT ename,d.deptno,d.loc
FROM emp e,dept d
WHERE e.deptno(+)=d.deptno
```



#### 3.6 SQL1999 [mysql,oracle]

> sql中表连接的一种语法

笛卡尔集

```sql
SELECT *
FROM 表1 CROSS JOIN 表2
```

等值连接【同一字段】

```sql
SELECT *
FROM 表1 JOIN 表2
USING(连接字段);
```

等值连接【不同字段，条件】

```sql
SELECT *
FROM 表1 JOIN 表2
ON(连接条件)
WHERE ....
```

外连接

```sql
SELECT *
FROM 表1 LEFT [OUTER] JOIN 表2
ON(连接条件)
WHERE ....


SELECT *
FROM 表1 RIGHT [OUTER] JOIN 表2
ON(连接条件)
WHERE ....


SELECT *
FROM 表1 FULL [OUTER] JOIN 表2
ON(连接条件)
WHERE ....
```

示例：

```sql
-- 笛卡尔集
SELECT *
FROM emp CROSS JOIN dept

-- 等值连接
SELECT *
FROM emp JOIN dept
USING(deptno);

SELECT *
FROM emp JOIN dept
ON(emp.deptno=dept.deptno)


SELECT *
FROM emp e JOIN emp m
ON(e.mgr=m.empno)
WHERE e.sal > 3000

-- 左外连
SELECT *
FROM emp e LEFT JOIN emp m
ON(e.mgr=m.empno)

-- 右外连
--查询各个部门的员工个数，没有员工也显示

SELECT d.deptno,COUNT(*)
FROM emp e RIGHT JOIN dept d
ON(e.deptno=d.deptno)
GROUP BY d.deptno


```



### 4 . 分组查询【重点】

> 通过分组函数，将数据按照组查询，得到结果。



#### 4.1 组函数

> 作用于多行数据，返回一个结果，分组函数属于多行函数。
>
> 分组函数会自动忽略空值。

```sql
SUM(列)	求和		 数字类型

AVG(列)  平均值		数字类型

MAX(列)  最大值		数字 / 日期

MIN(列)  最小值		数字 / 日期

COUNT(列) 计数		任意

COUNT(*)	统计所有的记录数
COUNT(列)   统计该列非空记录数
COUNt(DISTINCT 列) 统计该列去重后记录
```

示例：

```sql
-- 查询10部门总支出

SELECT SUM(sal)
FROM emp
WHERE deptno=10


-- 平均值 10或30部门平均薪资
SELECT round(AVG(sal))
FROM emp
WHERE deptno IN(10,30);


-- 查询名字包含S的员工最高薪资

SELECT MAX(sal)
FROM emp
WHERE ename LIKE '%S%'



-- 查询薪资等级为5级中，入职最晚的时间

SELECT MAX(e.hiredate)
FROM emp e,salgrade s
WHERE e.sal BETWEEN s.losal AND s.hisal AND s.grade=5


-- 有奖金员工薪资最小值

SELECT MIN(sal)
FROM emp
WHERE comm IS NOT NULL;


-- 查询领导是King的下属最低薪资

SELECT MIN(e.sal)
FROM emp e,emp m
WHERE e.mgr=m.empno AND m.ename=UPPER('King') 

-- 部门表记录数
SELECT COUNT(*)
FROM dept;


-- 查询20部门员工个数

SELECT COUNT(empno)
FROM emp
WHERE deptno=20


-- 查询员工表有奖金的人数

SELECT COUNT(comm)
FROM emp


-- 查询员工几种职位

SELECT COUNT(DISTINCT job)
FROM emp
```

练习：

```sql
-- 1 查询2月份入职员工总薪资
SELECT SUM(sal)
FROM emp
WHERE to_char(hiredate,'MM') =2
-- 2 查询10或30部门 且有奖金的员工平均薪资
SELECT AVG(sal)
FROM emp
WHERE deptno IN(10,30) AND comm IS NOT NULL;
-- 3 查询在纽约工作员工的最早入职时间
SELECT MIN(e.hiredate)
FROM emp e,dept d
WHERE e.deptno=d.deptno AND d.loc='NEW YORK'
-- 4 查询领导薪资是4级员工的最高薪资
SELECT MAX(e.sal)
FROM emp e, emp m ,salgrade s
WHERE e.mgr = m.empno AND m.sal BETWEEN s.losal AND s.hisal AND s.grade=5
```

练习2:

```sql
-- 1 查询在达拉斯工作的员工人数
SELECT COUNT(empno)
FROM emp e,dept d
WHERE e.deptno=d.deptno AND d.loc='DALLAS'


-- 2 查询Allen的下属人数
SELECT COUNT(e.empno)
FROM emp e,emp m
WHERE e.mgr=m.empno AND m.ename='BLAKE'
-- 3 查询9月份入职的人数
SELECT COUNT(empno)
FROM emp
WHERE to_char(hiredate,'MM') = 9;
-- 4 查询没有奖金的人数
SELECT COUNT(*)
FROM emp
WHERE comm IS NULL OR comm = 0; 
-- 5 查询工资等级2或3的人数
SELECT COUNT(empno)
FROM emp e,salgrade s
WHERE e.sal BETWEEN s.losal AND s.hisal AND s.grade IN(4,5)
-- 6 查询工作地址在 达拉斯 纽约的工作的职位种类

SELECT COUNT(DISTINCT job)
FROM emp e,dept d
WHERE e.deptno=d.deptno AND d.loc IN('DALLAS','NEW YORK')

```



#### 4.2  分组查询

> 对表中数据根据条件，先分n组，按组操作。

```sql
SELECT ...
FROM ...
WHERE ....
GROUP BY 字段【,字段】
[HAVING...限制组函数]
ORDER BY ....
```

> 执行顺序：  FROM  -> **WHERE  > GROUP BY  >  HAVING** > SELECT > ORDER 
>
> SELECT 后面只能两种情况： 1 GROUP BY出现的字段  2. 分组函数
>
> 

示例：

```sql
-- 查询各个部门 名字中有a的平均薪资

SELECT deptno,AVG(sal) a
FROM emp
WHERE ename LIKE '%A%'
GROUP BY deptno
HAVING AVG(sal) > 4500
ORDER BY a DESC 

-- 查询各个职位的有奖金的人数，人数2人以上 ，按照人数排序
SELECT job,COUNT(empno) e
FROM emp
WHERE comm IS NOT NULL
GROUP BY job
HAVING COUNT(empno)>= 2 
ORDER BY e


-- 查询各个部门位置下的人数，即使没有人的部门也显示，按照部门人数降序排列

SELECT d.loc,COUNT(e.empno) c
FROM emp e,dept d
WHERE e.deptno(+)=d.deptno 
GROUP BY d.loc
ORDER BY c DESC


-- 按照职位和部门分组
SELECT deptno,job,COUNT(empno)
FROM emp 
GROUP BY deptno,job
```



### 5 .  子查询

> 查询过程中，分步完成查询: 先进行一个查询（子查询），拿着这个结果继续做查询。

语法规则：

#### 5.1 WHERE型子查询

```sql
SELECT ...
FROM ...
WHERE 列  比较 (子查询);
```

特点： 先查子查询，结果给主查询使用



分类：

```sql
单行子查询  = > >= < <= != 
多行子查询  IN  >ALL  >ANY  <ALL  <ANY 
```

示例：

```sql
-- 查询比smith工资高的员工信息
SELECT *
FROM emp
WHERE sal > 	(SELECT sal
              FROM emp
              WHERE ename=UPPER('smith'))
              
-- 查询allen的同事
SELECT  *
FROM emp
WHERE deptno =(SELECT deptno FROM emp WHERE ename='ALLEN') AND  ename != 'ALLEN'

-- 查询员工表中最晚入职的员工信息
SELECT *
FROM emp
WHERE hiredate = (SELECT MAX(hiredate) FROM emp)

-- 查询公司工资最高的员工
-- 单行子查询 

SELECT *
FROM emp
WHERE sal = (SELECT MAX(sal)
            FROM emp)

-- 多行子查询
SELECT *
FROM emp
WHERE sal >=ALL (SELECT sal FROM emp)


```



#### 5.2 FROM型子查询

> （子查询是一个新表，新表添加别名）

```sql
SELECT ...
FROM 表 , （子查询） 别名
WHERE 连接条件  AND ..... 
```

```sql
-- 查询比公司平均工资高的员工薪资
SELECT *
FROM emp
WHERE sal > (SELECT AVG(sal) FROM emp )



-- 查询比自己所在部门平均工资高的员工
SELECT *
FROM emp e,(SELECT deptno,AVG(sal) a
            FROM emp
            WHERE deptno IS NOT NULL
            GROUP BY deptno) m 
WHERE e.deptno=m.deptno AND e.sal > m.a
```



#### 5.3 TOP-N 分析

> 1. 分页  ROWNUM     
> 2. 查询xx的 前几名，xx的后几名， 2-5名



语法规则：

分页【不需要排序】

```sql
SELECT ....
FROM ....
WHERE ROWNUM <= n
```

ROWNUM 行号，当表构建完行号，伪列，默认存在隐藏的列，手动查询

ROWNUM 必须写成<= n    =1,不能写between and ，不能写> >= 

示例：

```sql
-- 查询1-5条数据 第一页
SELECT *
FROM emp
WHERE ROWNUM <= 5


-- 查询6-10条数据 第二页


SELECT *
FROM (SELECT ROWNUM r, emp.*
             FROM emp) m
WHERE m.r BETWEEN 6 AND 10
             
```

TOP-N xx的前几名

```sql
SELECT ....
FROM (SELECT .... ORDER  BY xx)
WHERE ROWNUM <= n

-- xx最高的
SELECT ....
FROM (SELECT .... ORDER  BY xx)
WHERE ROWNUM = 1
```

示例：

```sql
-- 工资的前三名

SELECT *
FROM (SELECT *
      FROM emp
      ORDER BY sal DESC)
 WHERE ROWNUM <= 3;

-- 工资2-5名
SELECT *
FROM (
      SELECT m.*,ROWNUM r
      FROM 
             (SELECT *
              FROM emp
              ORDER BY sal DESC) m
 ) s
 WHERE s.r BETWEEN 2 AND 5
```

练习：

```sql
-- 查询部门位置下人数的第二到第三名

SELECT *
FROM (
       SELECT ROWNUM r,m.*
       FROM ( SELECT d.loc,count(e.empno) c
               FROM emp e,dept d
               WHERE e.deptno(+)=d.deptno
               GROUP BY d.loc
               ORDER BY  c DESC) m      ) s
 WHERE s.r BETWEEN 2 AND 3

```



### 第三章 DML

> DML 数据库操作语言 ： 增加数据  修改数据  删除数据  事务处理



### 1.增加数据

语法规则：

```sql
INSERT INTO 表名[(列名,列名2...)]
VALUES(值1,值2....);
```

注意：

1.每次只能向表中插入一条数据

2.表的列可以省略，值就需要对应表的全部列，依次对应

示例：

```sql
INSERT INTO emp
VALUES (8888, '于小闹', 'Boss',NULL, last_day(SYSDATE),20000,2000,40 );

INSERT INTO emp
VALUES (9999, '朱小宇', 'Developer',NULL, ADD_MONTHS(SYSDATE, 26),6000,500,40 );
```

3.可以有选择的插入某些字段

```sql
-- 1010 罗小全 HelpDesk 5500 1000 
INSERT INTO emp(empno,ename,job,sal,comm)
VALUES(1010,'罗小全', 'HelpDesk', 5500, 1000)


INSERT INTO emp(empno,ename,hiredate,sal,comm)
VALUES(1011,'姚小帅',to_date('2023-10-30','YYYY-MM-DD'),6500,500)
```

复制表：

```sql
CREATE TABLE emp2
AS
SELECT * FROM emp WHERE deptno=20
```

拷贝数据：

```sql
INSERT INTO 表名
SELECT ...
FROM ....
```



### 2.修改数据

> 对表中的数据更新。

语法规则：

```sql
UPDATE 表名
SET 列=值 , 列=值 ...
[WHERE 条件]
```

1.WHERE可无，修改表中全部数据

2.SET修改多个列，隔开

3.条件可以做子查询

```sql
-- 整个公司降薪1000

UPDATE emp
SET sal=sal-1000

-- 将领导是7698的员工涨500

UPDATE emp
SET sal=sal+500
WHERE mgr=7698


-- 将朱小宇部门修改为smith所在部门

UPDATE emp
SET  deptno=(SELECT deptno FROM emp WHERE ename=LOWER('SMITH'))
WHERE ename='朱小宇'


-- 修改 罗小全奖金和朱小宇一样，薪资提高100

UPDATE emp
SET comm=(SELECT comm FROM emp WHERE ename=('朱小宇')) , sal=sal+100
WHERE ename='罗小全'
```



### 3.删除数据

语法规则：

```sql
DELETE FROM 表名
[WHERE 条件]
```

1.删除添加条件，不加，删除表中全部数据

示例：

```sql
-- 删除SMITH

DELETE FROM emp
WHERE ename='SMITH'


-- 删除部门表20部门[当表中数据被其他表引用外键关系，不能删除，除非级联删除]

DELETE FROM dept
WHERE deptno=20

--删除领导是King的员工信息

--回滚


```



### 4. 事务

> 一连串的DML操作，一个系列的动作【操作】，称之为一个事务。
>
> 好处： 保证一组动作协调，一致的，统一的 （要么都做，要么都不做）



#### 4.1 事务的开始和结束

```
事务的开始：  
		发生第一个DML的时候
		
事务的结束： 
		提交  让一系列事务全部提交执行 COMMIT;
		
		回滚  让一系列事务全部撤回    ROLLBACK;
```



#### 4.2 事务四个特性【重点】

```
ACID

A 原子性 

C 一致性

I 隔离性

D 持久性

事务的四大特性主要是：原子性（Atomicity）、一致性（Consistency）、隔离性（Isolation）、持久性（Durability）。

```



#### 4.3 设置保留点

```sql
DELETE FROM emp
WHERE deptno=20;
-- 设置
SAVEPOINT s1;

DELETE FROM emp
WHERE deptno=10;
```

回滚到保留点

```sql
ROLLBACK TO s1;
```



### 第四章 DDL

> DDL 没有事务操作，提交回滚机制
>
> DDL :  建表    修改表  【增加列 删除列  修改列 】 删除表    约束 



### 1 数据建模

```
现实世界  


概念世界  【概念模型】  E-R 图   实体  关系  
			
		实体： 矩形
		属性： 椭圆 ，主属性 下方横线
		连接符： 实线
		关系： 菱形
		关系类型：
		1：1
		1：n
		m：n
		
机器世界
		
		1. 实体转化为表 
		2. 关系转化为表
		3. 属性转化为表的列
【重点】		
转化要求 ： 数据库范式  1NF  2NF  3NF  BCNF  4NF 5NF(要求级别最高的)

1NF  表的字段不可分割的原子级别，达到不可分割的基本要求

2NF  满足1NF, 表的非主属性都依赖于主属性

3NF  满足2NF，设计表的时候，表的所有字段之间不能存在传递依赖

	员工号  姓名  薪资  部门编号  
	
	
	部门编号 部门名  部门位置 
```



美团设计

```
顾客 ： 手机号 地址 性别  称呼 vip 

商家

平台

商品

骑手


```

示例图:

![](img\8.png)

### 2 创建表

> 1 账户具备建表的权限
>
> 2 足够的表空间
>
> 3 表名列名命名规范
>
> 		1. 必须字母开头 
> 		2. 1-30字符
> 		3. 字母 数字 _ $ #
> 		4. 不能关键字 不能重名 

#### 2.1 建表语法规则

```sql
CREATE table 表名(
	列名 数据类型(大小) [默认值] [约束] ，
    ....
	列名 数据类型(大小) [默认值] [约束]
    
    [约束]
	
)
```

注意： 必须 表名 列名 列数据类型 大小

数据类型：  数字 number()    字符串 char()   varchar2() 日期 Date  Long   ClOB  BLOB  Timestamp ....



![](img\9.png)

 示例：

```sql
-- 学生表  学号 姓名  性别 入学时间  平均成绩  

CREATE  TABLE student(

        sno NUMBER(5) PRIMARY KEY,
        sname VARCHAR2(100),
        gender VARCHAR2(10),
        rdate  DATE,
        score NUMBER(5,2)
)
INSERT INTO student VALUES(11111,'朱小宇','男',SYSDATE,88.88)
SELECT * FROM student
```

练习：

```sql
-- 课程表  课程编号 课程名称  学分  授课老师  授课地点  上课时间
CREATE TABLE course(
       cno NUMBER(4) PRIMARY KEY,
       cname VARCHAR2(100),
       credit NUMBER(2,1),
       teacher VARCHAR2(100),
       loc VARCHAR(100),
       ctime DATE)
```

#### 2.2 复制表

```sql
CREATE TABLE table [(column, column...)]
AS 子查询;
```



### 3 修改表

> 新增列  删除列  修改某列的类型或大小

语法规则

```sql
ALTER TABLE 表名
ADD (列 数据类型(大小))

ALTER TABLE 表名
MODIFY (列 数据类型(大小))


ALTER TABLE 表名
DROP (列)
```

示例：

```sql
ALTER TABLE student
ADD (age NUMBER(3))

ALTER TABLE student
MODIFY (sname VARCHAR2(120))

ALTER TABLE student
DROP (age)
```



### 4 删除表

```sql
-- DDL语句 删除表所有数据，回收表空间 表结构没有 ， 不能回滚
DROP TABLE 表名;

-- DML语句 只删除数据，可以回滚
DELETE FROM 表名;


--清空截断表 不能回滚 ，删除数据，回收空间，只保留结构
TRUNCATE TABLE 表名;
```

### 5 约束

> 在建表或者修改表时，对表添加的强行限制条件，称之为约束。
>
> 约束条件 ： 限制在表上或列上



#### 5.1 约束的分类

```sql
非空约束  NOT NULL 

唯一约束  UNIQUE

主键约束  PRIMARY KEY

外键约束  FOREIGN KEY 

检查约束  CHECK 
```





#### 5.2 约束的创建时机

```
1. 建表的时候  【推荐】

2. 建表后，补加约束
```



#### 5.3 约束创建的语法



```
约束名 ： 

​		1.自定义   

  			CONSTRAINT   表名_列名_xk     emp_empno_pk   emp_ename_nn  _ck  _fk  _uk

​		2.系统定义
```

语法规则： 取决于位置

列级约束 ； 表级约束

```sql
create table 表名(
	
	列  数据类型(大小)  列级约束 ,
	...
	列  数据类型(大小)  列级约束 ,
	
	表级约束 (列)...

)
```

列级约束

```sql
create table student(
	
	sno number(8) CONSTRAINT stu_sno_pk primary key  ,
	
)
```

表级约束

```sql
create table student(
	
	sno number(8)  ,
	sname varchar2(20)，
	-- 表级
	CONSTRAINT stu_sno_pk primary key(sno)
	
)
```





#### 5.4  非空约束

NOT NULL

> 约束在某列上，该列数据不能为空
>
> 非空只能 列级

示例：

```sql
CREATE TABLE course(
       cno NUMBER(4) NOT NULL,
       cname VARCHAR2(20) NOT NULL
 )
 -- 错误 cno 不能空
 -- INSERT INTO course(cname)
 --VALUES('java') 
```





#### 5.5  唯一约束

UNIQUE

> 唯一约束，限制在某列，该列不允许重复
>
> 表级 列级

```sql
CREATE TABLE course(
       cno NUMBER(4) NOT NULL,
       cname VARCHAR2(20) CONSTRAINT cour_cname_uk UNIQUE
 )

INSERT INTO course
VALUES(2,'java')

SELECT * FROM course
```



#### 5.6  主键约束

Primary  key 

> 主码，为表添加某个能够唯一确定表字段。
>
> 1. 任何表必须有且只有一个主键
> 2. 主键不一定是一个列，很多时，多个列构成主键【联合主键】
> 3. 主键 ： 非空 + 唯一 
> 4. 可以列级，可以表级



```sql
CREATE TABLE course(
       cno NUMBER(4) primary key,
       cname VARCHAR2(20) CONSTRAINT cour_cname_uk UNIQUE
 )

```

示例：

```sql
DROP TABLE course;
CREATE TABLE course(
       cno NUMBER(4) CONSTRAINT cour_cno_pk primary key,
       cname VARCHAR2(20) CONSTRAINT cour_cname_uk UNIQUE
 )
 
 
INSERT INTO course
VALUES(1,'java')
 

-- 选课表: cno sno xdate

CREATE TABLE sc(
      sno NUMBER(4),
      cno NUMBER(8),
      xdate DATE,
      --联合主键
      CONSTRAINT sc_scno_pk PRIMARY KEY(sno,cno)     

)

```



#### 5.7 外键约束

Foreign key

> 当A表的某字段参考于B表的主键，该A表的列称之为外键。  员工表的部门编号是外键。
>
> 外键是来源于两张表
>
> 外键夹在某列，限制该列的数据必须参考于其他表
>
> 外键可以有多个，习惯上定义表级



```sql
 CONSTRAINT sc_sno_fk FOREIGN KEY(外键列)   REFERENCES 主表(主键字段);  
```

示例：

```sql
-- 选课表: cno sno xdate
DROP TABLE sc;
CREATE TABLE sc(
      sno NUMBER(4),
      cno NUMBER(8),
      xdate DATE,
      --联合主键
      CONSTRAINT sc_scno_pk PRIMARY KEY(sno,cno),
      
      --外键
      CONSTRAINT sc_sno_fk FOREIGN KEY(sno) REFERENCES student(sno),
      CONSTRAINT sc_cno_fk FOREIGN KEY(cno) REFERENCES course(cno)

)
```

```sql
-- 当添加外键，外键列的数据必须参考于主表
-- sno和cno必须参考另外两表
INSERT INTO sc
VALUES(1,1,SYSDATE)
```

```sql
-- 无法删除
DELETE FROM student
WHERE sno=1
```

注意：当添加外键，子表引用了主表的数据，此时无法删除主表数据。先删除子表相关记录，才能删除主表。

###### 设置级联删除

添加外键的时候，设置关联删除/修改  

```sql
CONSTRAINT sc_sno_fk FOREIGN KEY(外键列)   REFERENCES 主表(主键字段)  on delete Cascade ;
```

设置级联删除，删除主表数据，连带删除子表。



#### 5.8 检查约束

CHECK

> 该约束添加到字段上，限制该列的取值范围【域值】。
>
> 表级和列级
>
> CHECK(条件) ， 条件和WHERE条件一致

```sql
DROP TABLE student;
CREATE TABLE student(
       sno NUMBER(4) PRIMARY KEY,
       sname VARCHAR2(20) NOT NULL,
       gender VARCHAR2(10) CHECK(gender IN('男','女')),
       rdate DATE,
       score NUMBER(4,1),
       CONSTRAINT stu_score_ck CHECK(score BETWEEN 1 AND 100)

)
```



总结：约束可以使得表具备完整性

```
域完整性	非空约束	检查约束

实体完整性  唯一约束    主键约束

参照完整性  外键约束
```



### 第五章  其他数据库对象

### 1 视图 view 

> 从原表中抽取逻辑相关的数据集。 

#### 1.1 视图的作用

```
1. 简化查询 【将逻辑上相关，用户需要的字段提取出来，针对性操作】

2. 数据具备独立性

3. 不会重复访问数据
```



#### 1.2  语法规则

```sql
CREATE [OR REPLACE]  VIEW  视图名  [(别名[, 别名]...)]
AS 子查询

```

注意：

1.[OR REPLACE]   如果添加， 如果视图存在则替换，如果不存在，表示新建，这就是视图的修改

2.查询视图，可以给列加别名 



#### 1.3  查询视图

```sql
select * from 视图名;

```



#### 1.4  视图操作

> 对视图的一切操作都是在操作**原表数据**

```sql
INSERT INTO sal01
VALUES(1111,'aa',8888,20)

DELETE FROM sal01
WHERE ename='aa'

UPDATE sal01
SET sal=sal-1000
WHERE ename='朱小宇'
```



#### 1.5  删除

```sql
DROP VIEW 视图名 ;
```



### 2 序列 sequence

> 序列是一组有规律的数列。    

#### 2.1 作用

```
用来提供主键【为了非空+唯一】
```

#### 2.2 语法规则

```sql
CREATE SEQUENCE 序列名
--起始值
start with  n
-- 增值【步长】
increment by n
-- 最值
maxvalue n / nomaxvalue
-- 是否循环
cycle  / nocycle
-- 是否装入缓存
cache / nocache
```

示例：

```sql
CREATE SEQUENCE seq1


CREATE SEQUENCE seq2
START WITH 50
INCREMENT BY 10
MAXVALUE 100
```



#### 2.3 获取序列值

```sql
--获取当前值
序列名.currval

-- 获得下一个
序列名.nextval

注意： 序列必须向下获取到值，才能获得当前值


SELECT seq2.nextval
FROM dual;

SELECT seq2.currval
FROM dual;



```

示例：

```sql

SELECT seq2.nextval
FROM dual;

SELECT seq2.currval
FROM dual;


INSERT INTO dept
VALUES(seq2.nextval,'财务部','上海')

SELECT * FROM dept;
```

#### 2.4  序列删除

```sql
DROP SEQUENCE 序列名;
```

### 3 索引 index

> 是添加在表的列上，提供查询效率，减少磁盘的I/O。相当于查询时的目录，快速的定位。



#### 3.1 索引的创建

```sql
-- 自动创建 ： 为列添加主键或唯一约束，自带索引

-- 手动创建

Create index 索引名
on 表(列); 

CREATE INDEX index_name
ON emp(ename);
```

#### 3.2 创建索引的时机

```
1. 数据量比较大，数据的访问量比较大
2. 表不会总更新
3. 表中含有空值
4. 表的WHERE筛选某列
```



#### 3.3 不适合索引

索引虽好，需要维护成本

```
1. 表很小，数据很少
2. 表经常更新
```



#### 3.4 索引删除

```sql
DROP INDEX 索引名;
```



### 第六章 DCL

### 1 授权

```
grant create xx  to  用户;
```

### 2  收回

```
revoke create xx from 用户;
```


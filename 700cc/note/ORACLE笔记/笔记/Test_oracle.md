### 10-20

```sql
1.
sql语句分类


dql 数据库查询语言
dml 数据库操作语言
ddl 数据库定义语言
dcl 数据库控制语言


2.
oracle : 跨平台 ，安全性高 ， 数据量大 ， 并发性强  

3.
Distinct

4.
Number(7,2) 5位整数  2小数

5.
select ename,(sal+nvl(comm,0)) * 12 年薪
from emp
where deptno=20;


6.
select *
from emp
where hiredate = '1-1月-1980'


7.
线程锁

	同步锁 synchronized  
	synchronized(锁定资源){
	
	}
		
	
	lock() 锁 性能高 使用灵活 分类 
	
	
	
8.
线程同步： 线程安全，当多个线程，A线程访问临界资源时，B线程无法访问临界资源 

9.
五个状态

新建  就绪  执行  阻塞 结束

10.
Runnable r = ()->{
	syso......
};

r.start();


Runnable r = new Runnable(){
	public void run(){
	
		
	}
};

r.start();

```



### 10-23

```sql
1.
select DISTINCT job
from emp


2.
select *
from emp
where sal between 3000 and 5000
order by sal desc;

3.
select *
from emp
where ename like '%S%' or ename like '%s%'

select *
from emp
where upper(ename) like '%S%'

4.
select *
from emp
where to_char(hiredate,'MM') = 10;


5.
select ename,(sal+nvl(comm,0))*12 年薪
from emp
where length(ename)=3

6.
select substr(ename,1,1)
from emp
where deptno in(10,20)

7.
select *
from emp
where hiredate=last_day(hiredate);

8.-- 系统时间两天
select sysdate+2
from dual;


select next_day(hiredate,2)
from dual;


9.
select *
from emp
where comm is not null;

10.
SQL

	DQL  DML  DDL  DCL 
	
	
	
```





### 10-24

```sql
1.
外连接  显示不满足等值连接条件的数据
左外连  左边表主表，左侧表数据完全显示，即使不满足连接条件
右外连  右边表主表，右侧表数据完全显示，即使不满足连接条件	

2.外连接
select e.ename,m.ename
from emp e,emp m
where e.mgr=m.empno(+)


3. 等值连接
select e.ename,e.sal,d.loc
from emp e,dept d
where e.deptno=d.deptno and e.deptno in(20,30)

4. 不等值连接
select e.sal,s.grade
from emp e,salgrade s
where e.comm is not null and e.sal between s.losal and s.hisal


5.笛卡尔集
select *
from emp,dept

6.自我连接
select (e.sal+nvl(e.comm,0))*12 yearsal
from emp e,emp m
where e.mgr = m.empno and m.ename = upper('KING')


7.
select to_date('2001-10-21','YYYY-MM-DD')
from dual;


select sysdate - to_date('12-12月-1980','DD-MON-YYYY')
from dual;


select sysdate - hiredate
from dual;


8.
select add_months(sysdate,2)
from dual;


9.
select ename,to_char(hiredate,'fmMM"月"'),
case 
  when to_char(hiredate,'MM') between 1 and 3 then '第一季度'
  when to_char(hiredate,'MM') between 4 and 6 then '第二季度'
  when to_char(hiredate,'MM') between 7 and 9 then '第三季度'
  when to_char(hiredate,'MM') between 10 and 12 then '第四季度'
    ELSE '空季度'
  end 
  
from emp

```





### 10-25

```sql
1.
select sum(sal)
from emp
where deptno=10

2.
select count(empno)
from emp
where ename like '%A%'

3.

select max(hiredate)
from emp
where to_char(hiredate,'MM') =8


4.
select count(e.empno)
from emp e,emp m
where e.mgr = m.empno  and m.ename='BLAKE'

5.
select count(distinct deptno)
from emp;


6.
select deptno,avg(sal)
from emp
group by deptno


7.
select job,count(empno) c
from emp
group by job
having count(empno)>=2
order by c desc

8.
select mgr,count(empno), decode(count(e.empno),2,'不够',3,'正好',4,'多了') info
from emp
group by mgr 

9.
select d.loc,count(e.empno)
from emp e,dept d
where e.deptno(+)=d.deptno
group by d.loc
```





### 10-27

```sql
1.
事务的特性
ACID  原子性 一致性 隔离性  持久性


2.COMMIT ;    ROLLBACK;

3.
insert into dept
values(50,'开发部','大连')

4.
update dept
set loc='上海'
where deptno=50


5.
delete from emp where mgr = (select empno from emp where ename='KING')

6.
E_R 实体 矩形  属性 椭圆  关系 菱形 

7.
关系 ： 1对1  1对多  多对多

8.
select *
from emp
where rownum <= 5;


9
select *
from (select * from emp order by sal)
where rownum <= 3


10.
select to_char(hiredate,'MM'),count(empno) c
from emp
group by to_char(hiredate,'MM')
having count(empno)>= 2
order by c desc;
```





### 10-30

```sql
1. 外连接 【将不满足等值连接条件的数据显示】
   左外连  左侧表主表，左侧表数据完全显示 (+)置于右侧
   右外连  右侧表主表，右侧表数据完全显示 (+)置于左侧
   
2.
事务四大特性 :
	ACID
	A  原子性
	C  一致性
	I  隔离性
	D  持久性
	
3.
组函数  sum() avg()  min() max() count()

4.
create table student(
	sno number(8) primary key,
	sname varchar2(20)
)

5.
insert into student
values(1,'朱朱');

6.
update student
set sname='小朱'
where sno=1


7.
delete dml 删除数据 可以回滚
drop  ddl 删除全部 数据 结构和空间回收  不能回滚
truncate  ddl 截断表  删除数据和回收空间，结构还在， 不能回滚


8.
实体关系： 1对1  1对多 多对多

9.
范式
1nf : 字段不可分割原子
2nf : 满足1nf，非主属性依赖于主属性
3nf : 满足2nf，属性之间不能存在传递依赖


10.sql  部门平均薪资处于2级，部门全部信息
select m.*,s.grade
from (
    select d.dname,d.loc,avg(e.sal) a
    from  emp e,dept d
    where e.deptno=d.deptno
    group by  d.dname,d.loc) m ,salgrade s
where m.a between s.losal and s.hisal and s.grade=2



```





### 10-31

```sql
1.
约束

	非空约束  NOT NULL
	唯一约束  UNIQUE
	主键约束  primary key
    外键约束  foreign key
    检查约束  check
    
2.
create view v1020
as
select empno,ename,hiredate
from emp
where deptno in(10,20)
    
    
3.
create sequence seq
start with 1
maxvalue 100
increment by 2

4.
seq.nextval  seq.currval  


5.
drop table sc;
create table sc(
    sno number(4),
    cno number(4),
    sdate date,
    primary key (sno,cno),
    foreign key(sno) references stu(sno),
    foreign key(cno) references course(cno)  on delete cascade
)


6.

delete  dml 只删除数据 可以回滚 
drop    ddl 表全部删除 不回滚
truncate  ddl  表数据删除 空间回收，保留表结构  不能回滚

7.
事务的开始 ： 当执行某个DML 

事务的结束 ： commit ; rollback;


8.
List 接口

	实现类 
			ArrayList 线程不安全 线性存储，元素挨着，适合查询不适合更新
			LinkedList 线程不安全 链式存储，适合更新，不适合查询
			Vector 线程安全 同步 效率低
			
	线程同步： 线程A操作临界资源，线程B无法介入访问		
	添加线程锁
    
    同步锁  
    lock锁 lock()  unlock() 更加灵活  jdk5+  
    
9. Map 接口
HashMap  线程不安全 允许空键空值
Hashtable 反之


10.
List
	add(元素)
	add(下标,元素)
	remove(下标)
	set(下标,元素)
	get(下标)
    
```




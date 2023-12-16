## JDBC

> Java  Database  Connectivity  ， 将JAVA和数据库连接到一起。通过JAVA的API 【java.sql.*】来操作数据库中表的数据，从而通过JAVA代码直接实现对数据表的增删改查。【CRUD】



### 第一章  JDBC操作的原理

> JAVA提供的是一套统一通用的API，适用于各种数据库。前提是： 对应数据库的驱动文件。

![](img\1.png)

### 第二章  JDBC操作的API

| 接口/类       | 含义                                  | 方法                                          | 返回值              |
| ------------- | ------------------------------------- | --------------------------------------------- | ------------------- |
| DriverManager | 驱动管理类 ，用于管理不同数据库的驱动 | getConnection()                               | Connection          |
| Connection    | 连接接口，获得数据库连接              | createStatement()                             | Statement           |
| Statement     | 执行接口，发送sql到数据库             | executeUpdate(sql)<br />executeQuery(sql)     | int <br />ResultSet |
| ResultSet     | 结果集接口， 获得数据库返回结果集     | next() 获取一行<br />getXX(1)   getXX("列名") |                     |
| Driver        | 驱动接口                              |                                               |                     |

int : 执行完DML，受到影响的行数。

getXX() xx列的数据类型  getInt()  getDouble()  getString()  getDate() 

getXX(1)  查询列表的第几列 

### 第三章  JDBC步骤【重点】

```
1. 加载驱动，载入驱动文件

2. 建立和数据库连接 Connection

3. 创建执行命令接口 Statement

4. 执行sql语句，发送到数据库 executeXX() 

5. 接收数据库返回，结果解析结果集 ResultSet

6. 关闭数据库连接  
```



#### 3.1 加载驱动

```
1. 粘贴驱动文件到java项目

2. 配置jar  右键  build path  >  configure > libraries > add jars 

3. 创建JAVA类 ，载入驱动

```

示例：

```java
public class TestConnection {
	
	public static void main(String[] args) {
		
		// 1 加载驱动-> 反射机制 提供.class 
		try {
			Class.forName("oracle.jdbc.driver.OracleDriver");
		} catch (ClassNotFoundException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
	}
}

```



#### 3.2 数据库连接

```
连接地址 jdbc:数据库名:连接类型:@IP地址：端口:数据库名 
IP ： 本地 localhost / 127.0.0.1     

jdbc: oracle :thin: @166.111.7.89:1521:ora9


数据库账户名  scott
密码  tiger 
```

示例：

```java
		//2 连接
		String url = "jdbc:oracle:thin:@localhost:1521:orcl";
		String username = "scott";
		String pass = "tiger";
		
		try {
			DriverManager.getConnection(url,username,pass);
			System.out.println("连接成功");
		} catch (SQLException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
```



#### 3.3  发送SQL语句，解析结果

##### 1.执行DML

增加：

```java
package com.cl.jdbc;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;

/**
 * 测试连接
 * @author 86136
 *
 */
public class TestConnection {
	
	public static void main(String[] args) throws SQLException {
		
		// 1 加载驱动-> 反射机制
		try {
			Class.forName("oracle.jdbc.driver.OracleDriver");
		} catch (ClassNotFoundException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
		//2 连接
		String url = "jdbc:oracle:thin:@localhost:1521:orcl";
		String username = "scott";
		String pass = "tiger";
        //连接接口
		Connection conn = null;
		try {
			conn = DriverManager.getConnection(url,username,pass);
			System.out.println("连接成功");
		} catch (SQLException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
		
		//3 发送sql
		String sql = "insert into dept values(11,'保安部','沈阳')" ;
		
//		StringBuilder sql2 = new StringBuilder()
//				.append("insert into dept ")
//				.append("values(11,'技术部','大连')");
		
		//3 执行命令接口
		Statement ste = conn.createStatement();
		//4 执行
		int a = ste.executeUpdate(sql);
        if(a > 0) {
				System.out.println("成功");
			}else {
				System.out.println("失败");
		}
	}
}

```

删除：

```java
package com.cl.jdbc;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;

public class TestDelete {
	public static void main(String[] args) throws SQLException, ClassNotFoundException {
		Connection conn = null;
		Statement ste = null;
		try {
			//1 加载驱动
			Class.forName("oracle.jdbc.driver.OracleDriver");
		
			//2 建立连接
			conn = DriverManager.getConnection("jdbc:oracle:thin:@localhost:1521:orcl","scott","tiger");
			//设置不自动提交
			//conn.setAutoCommit(false);
			//3. 获得执行命令接口
			 ste = conn.createStatement();
			
			//4. 执行语句
			int a = ste.executeUpdate("delete from dept where deptno=70");
			// 5 解析
			if(a > 0) {
				System.out.println("成功");
			}else {
				System.out.println("失败");
			}
			
		}finally {
			// 6 关闭
			ste.close();
			conn.close();
		}
	}
}

```

##### 2.执行DQL

```java
package com.cl.jdbc;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;

public class TestQuery {
	public static void main(String[] args) throws SQLException, ClassNotFoundException {
		Connection conn = null;
		Statement ste = null;
		ResultSet a = null;
		try {
			//1 加载驱动
			Class.forName("oracle.jdbc.driver.OracleDriver");
		
			//2 建立连接
			conn = DriverManager.getConnection("jdbc:oracle:thin:@localhost:1521:orcl","scott","tiger");
			//设置不自动提交
			//conn.setAutoCommit(false);
			//3. 获得执行命令接口
			 ste = conn.createStatement();
			
			//4. 执行语句
			 a = ste.executeQuery("select * from dept");
			// 5 解析
			//行
			while(a.next()) {
				//列
				System.out.println(a.getInt(1) + "," + a.getString("dname") + "," + a.getString(3));
			}
			
			
		}finally {
			// 6 关闭
			a.close();
			ste.close();
			conn.close();
		}
	}
}

```



#### 3.4  关闭

```java
先创建的后关闭

	ResultSet
	Statement
	Connection
	
ste.close();
conn.close();
```



### 第四章 面向对象实现JDBC

#### 4.1 数据库的连接 DBUtil

1，2，6 提取，数据库连接类，公共类

```java
package com.cl.jdbc.common;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;

/**
 * 数据库连接
 * @author 86136
 *
 */
public class DBUtil {
	
	private static String url = "jdbc:oracle:thin:@localhost:1521:orcl";
	private static String username = "scott";
	private static  String pass = "tiger";
	
	/**
	 	* 静态代码块完成驱动载入
	 	* 只需要载入一次
	 */
	static {
		try {
			Class.forName("oracle.jdbc.driver.OracleDriver");
		} catch (ClassNotFoundException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
	}
	
	public static Connection getConn() {
		Connection conn = null;
		try {
			conn = DriverManager.getConnection(url,username,pass);
		} catch (SQLException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
		return conn;
	}
	
	public static void close(Connection c,Statement s,ResultSet r) {
		
		try {
			c.close();
			s.close();
			r.close();
		} catch (SQLException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
	}
}

```



#### 4.2  模块的面向对象实体封装

> pojo ： 普通的JAVA对象

```java
package com.cl.jdbc.emp;

import java.sql.Date;

/**
 * 实体类： 属性和表对应【个数，类型，变量名】
 * @author 86136
 *
 */
public class Emp {
	private int empno;
	private String ename;
	private double sal;
	private Date hiredate;
	public int getEmpno() {
		return empno;
	}
	public void setEmpno(int empno) {
		this.empno = empno;
	}
	public String getEname() {
		return ename;
	}
	public void setEname(String ename) {
		this.ename = ename;
	}
	public double getSal() {
		return sal;
	}
	public void setSal(double sal) {
		this.sal = sal;
	}
	public Date getHiredate() {
		return hiredate;
	}
	public void setHiredate(Date hiredate) {
		this.hiredate = hiredate;
	}
	public Emp(int empno, String ename, double sal, Date hiredate) {
		super();
		this.empno = empno;
		this.ename = ename;
		this.sal = sal;
		this.hiredate = hiredate;
	}
	public Emp(int empno, String ename, double sal) {
		super();
		this.empno = empno;
		this.ename = ename;
		this.sal = sal;
	}
	public Emp() {
		super();
	}
	@Override
	public String toString() {
		return "Emp [empno=" + empno + ", ename=" + ename + ", sal=" + sal + ", hiredate=" + hiredate + "]";
	}
	
	
}

```



#### 4.3  实体的DAO层

> DAO:  Data access object  数据访问对象
>
> 数据访问层【数据层】 ：  DAO层中存储对实体对象进行增删改查的方法。
>
> 细粒度的： 类中的方法只完成一个动作： CRUD 

接口设计：

```java
package com.cl.jdbc.emp.dao;

import java.util.ArrayList;

import com.cl.jdbc.emp.pojo.Emp;

/**
 * 设计层面接口
 * @author 86136
 *
 */
public interface IEmpDao {
	
	//public abstract 
	
	/**
	 * 增加员工
	 */
	int addEmp(Emp emp);
	
	/**
	 * 修改
	 */
	int updateEmp(Emp emp);
	
	/**
	 * 删除
	 */
	int delEmp(int empno);
	
	/**
	 * 查询单个
	 */
	Emp queryByNo(int empno);
	
	/**
	 * 查询所有
	 */
	ArrayList<Emp> queryAll();
	
}

```

实现类：

```java
package com.cl.jdbc.emp.dao;

import java.sql.Connection;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;
import java.util.ArrayList;

import com.cl.jdbc.common.DBUtil;
import com.cl.jdbc.emp.pojo.Emp;

public class EmpDaoImpl implements IEmpDao {

	@Override
	public int addEmp(Emp emp) {
		Connection conn = DBUtil.getConn();
		Statement ste = null;
		int a = 0;
		// 3 发送sql
		String sql = "insert into emp(empno,ename,sal,hiredate) values(" + emp.getEmpno() +  ",'"+emp.getEname()+"',"+emp.getSal()+",sysdate)";
		try {
			// 3 执行命令接口
			ste = conn.createStatement();
			// 4 执行
			a = ste.executeUpdate(sql);
			// 5 解析结果a
		}catch(SQLException e) {
			e.printStackTrace();
		}finally {
			// 6 关闭
			DBUtil.close(conn, ste);
		}

		return a;
	}

	@Override
	public int updateEmp(Emp emp) {
		// TODO Auto-generated method stub
		return 0;
	}

	@Override
	public int delEmp(int empno) {
		Connection conn = DBUtil.getConn();
		Statement ste = null;
		int a = 0;
		// 3 发送sql
		String sql = "delete from emp where empno=" + empno ;
		try {
			// 3 执行命令接口
			ste = conn.createStatement();
			// 4 执行
			a = ste.executeUpdate(sql);
			// 5 解析结果a
		}catch(SQLException e) {
			
		}finally {
			// 6 关闭
			DBUtil.close(conn, ste);
		}

		return a;
	}

	@Override
	public Emp queryByNo(int empno) {
		Connection conn = DBUtil.getConn();
		Statement ste =  null;
		ResultSet r = null;
		Emp e = null;
		try {
			//3 发送sql
			String sql = "select empno,ename,sal,hiredate from emp where empno=" + empno ;
				
			//3 执行命令接口
			ste = conn.createStatement();
			//4 执行
			r = ste.executeQuery(sql);
			//5 解析结果
			if(r.next()) {
				e = new Emp(r.getInt(1) , r.getString(2) , r.getDouble(3) , r.getDate(4));
				
			}
		}catch(SQLException ex) {
			
		}finally {
			//6 关闭
			DBUtil.close(conn, ste, r);
		}
		return e;
	}

	@Override
	public ArrayList<Emp> queryAll() {
		Connection conn = DBUtil.getConn();
		Statement ste =  null;
		ResultSet r = null;
		ArrayList<Emp> list = new ArrayList<Emp>();
		try {
			//3 发送sql
			String sql = "select empno,ename,sal,hiredate from emp" ;
				
			//3 执行命令接口
			ste = conn.createStatement();
			//4 执行
			r = ste.executeQuery(sql);
			//5 解析结果
			while(r.next()) {
				Emp e = new Emp(r.getInt(1) , r.getString(2) , r.getDouble(3) , r.getDate(4));
				list.add(e);
			}
		}catch(SQLException e) {
			
		}finally {
			//6 关闭
			DBUtil.close(conn, ste, r);
		}
		return list;
	}
}

```

#### 4.4 测试DAO

```java
public class Test {
	public static void main(String[] args) {
		EmpDaoImpl dao = new EmpDaoImpl();
		int a = dao.addEmp(null);
		
		System.out.println(a > 0 ? "成功" : "失败");
	}
}
```



#### 4.5 日期特殊处理

```java

java.sql.Date  extends java.util.Date  {
	

}

new java.util.Date(); //系统当前时间

// 将util.Date 转化成sql下Date


public class DateFormatter {
	
	public static java.sql.Date format(String str){
		java.sql.Date d = null;
		SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd");
		try {
			java.util.Date date = sdf.parse(str);
			d = new java.sql.Date(date.getTime());
		} catch (ParseException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
		return d;
	}
}

@Override
	public int addEmp(Emp emp) {
		Connection conn = DBUtil.getConn();
		Statement ste = null;
		int a = 0;
		// 3 发送sql
		String sql = "insert into emp(empno,ename,sal,hiredate) values(" + emp.getEmpno() +  ",'"+emp.getEname()+"',"+emp.getSal()+",to_date('"+emp.getHiredate()+"','yyyy-mm-dd'))";
		
		System.out.println(sql);
		try {
			// 3 执行命令接口
			ste = conn.createStatement();
			// 4 执行
			a = ste.executeUpdate(sql);
			// 5 解析结果a
		}catch(SQLException e) {
			e.printStackTrace();
		}finally {
			// 6 关闭
			DBUtil.close(conn, ste);
		}

		return a;
	}

测试：
    	int a = dao.addEmp(new Emp(9898, "Kelly", 6000,DateFormatter.format("2000-10-1")));
		System.out.println(a > 0 ? "success" : "error");
		
		for (Emp e : dao.queryAll()) {
			System.out.println(e);
		}
```



#### 4.6 预编译SQL

> PreparedStatement : 预编译的执行命令接口，是Statement的子接口
>
> 特点： 可以提前预先编译sql语句，分离java和sql代码
>
> 优点：
>
> 1. 提高sql语句的执行效率
> 2. java和sql完全分离，解耦，提高安全性
> 3. 防止sql注入，避免java的参数变量拼接入sql。
>
> 

##### 4.6.1 如何实现

```java
1. 执行命令的接口  PreparedStatement
//sql语句需要参数的位置使用?代替
String sql = "insert into emp(empno,ename,sal,hiredate) values(?,?,?,?)";
//预编译
PreparedStatement ste = conn.prepareStatement(sql);


2.给？赋值
ste.setXX(？的位置，值);  xx ？的数据类型   
ste.setInt(1, emp.getEmpno());
ste.setDouble(3, emp.getSal());
ste.setString(2, emp.getEname());
ste.setDate(4, emp.getHiredate());


3.执行,不带参数
  executeUpdate()
  executeQuery();
			
```





#### 4.7  公共DAO层

DML封装

```java
package com.cl.jdbc.common;

import java.sql.Connection;
import java.sql.PreparedStatement;
import java.sql.SQLException;

/**
 * DAO的深层封装
 * @author 86136
 *
 */
public class BaseDao {
	
	/**
	 *    完成所有模块的DML操作
	 * @param sql 外部传入sql
	 * @param params 给？赋值
	 * @return
	 */
	public int  exeDML(String sql,Object...params ) {
		Connection conn = DBUtil.getConn();
		PreparedStatement ste = null;
		int a = 0;
		try {
			// 3 执行命令接口
			ste = conn.prepareStatement(sql);	
			//给？赋值
			for (int i = 0; i < params.length; i++) {
				ste.setObject(i + 1, params[i]);
			}
			// 4 执行
			a = ste.executeUpdate();
			// 5 解析结果a
		}catch(SQLException e) {
			e.printStackTrace();
		}finally {
			// 6 关闭
			DBUtil.close(conn, ste);
		}

		return a;
	}
}

```

EmpDao:

```java
package com.cl.jdbc.emp.dao;

import java.sql.Connection;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;
import java.util.ArrayList;

import com.cl.jdbc.common.BaseDao;
import com.cl.jdbc.common.DBUtil;
import com.cl.jdbc.emp.pojo.Emp;

public class EmpDaoImpl extends BaseDao<Emp> implements IEmpDao {

	@Override
	public int addEmp(Emp emp) { 
		String sql = "insert into emp(empno,ename,sal,hiredate) values(?,?,?,?)";
		
		return exeDML(sql, emp.getEmpno(),emp.getEname(),emp.getSal(),emp.getHiredate());
	}

	@Override
	public int updateEmp(Emp emp) {
		// 3 发送sql
		String sql = "update emp set ename=?,sal=?,hiredate=? where empno=?";
		
		return exeDML(sql, emp.getEname(),emp.getSal(),emp.getHiredate(),emp.getEmpno());
		
	}

	@Override
	public int delEmp(int empno) {
		
		String sql = "delete from emp where empno=?";
		
		return exeDML(sql, empno);
	}


```

查询封装

结果集映射

```java
public interface RowMapper<T> {
	
	T getRow(ResultSet r);
}

```

员工实现映射

```java
public class EmpMapper implements RowMapper<Emp>{

	@Override
	public Emp getRow(ResultSet r) {
		Emp e = null;
		try {
			e = new Emp(r.getInt(1), r.getString(2), r.getDouble(3),r.getDate(4));
		} catch (SQLException e1) {
			// TODO Auto-generated catch block
			e1.printStackTrace();
		}
		return  e;
	}

}
```

BaseDao封装：

```java
public ArrayList<T> query(String sql,RowMapper<T> rw,Object...params){
		Connection conn = DBUtil.getConn();
		PreparedStatement ste =  null;
		ResultSet r = null;
		ArrayList<T> list = new ArrayList<T>();	
		try {
			ste = conn.prepareStatement(sql);
			if(params != null) {
				for (int i = 0; i < params.length; i++) {
					ste.setObject(i + 1, params[i]);
				}
			}
			
			r = ste.executeQuery();
			while(r.next()) {
				T t = rw.getRow(r);
				list.add(t);
			}
		}catch(SQLException ex) {
			
		}finally {
			//6 关闭
			DBUtil.close(conn, ste);
		}
		return list;
	}
```

EmpDaoImpl:

```java
@Override
	public Emp queryByNo(int empno) {
		String sql = "select empno,ename,sal,hiredate from emp where empno=?";
		List<Emp> l = query(sql, new EmpMapper(),empno);
		if( l != null) {
			return l.get(0);
		}
		
		return null;
	}

	@Override
	public ArrayList<Emp> queryAll() {
		
		String sql = "select empno,ename,sal,hiredate from emp";
		return query(sql, new EmpMapper());
	}
```



#### 4.8 模糊查询

DAO接口:

```java
	/**
	 * 按照员工姓名模糊查询
	 */
	ArrayList<Emp> queryEmpByName(String n);
```

DAO实现类：

```java
@Override
	public ArrayList<Emp> queryEmpByName(String n) {
		String sql = "select empno,ename,sal,hiredate from emp where ename like '%' || ? || '%'";
		return query(sql, rw, n);
	}
```

测试：

```java
EmpDaoImpl dao = new EmpDaoImpl();
for (Emp e : dao.queryEmpByName("小")) {
			System.out.println(e);
		}
```





#### 4.9 表连接查询

对象有关联： 员工包含部门 【一对一包含】

```java
package com.cl.jdbc.emp.pojo;

import java.sql.Date;

import com.cl.jdbc.dept.pojo.Dept;

/**
 * 实体类： 属性和表对应
 * @author 86136
 *
 */
public class Emp {
	private int empno;
	private String ename;
	private double sal;
	private Date hiredate;
	
	//对象包含
	private Dept dept;
	
	
	public Dept getDept() {
		return dept;
	}
	public void setDept(Dept dept) {
		this.dept = dept;
	}
	// ....
	public Emp(int empno, String ename, double sal, Dept dept) {
		super();
		this.empno = empno;
		this.ename = ename;
		this.sal = sal;
		this.dept = dept;
	}
	
}

```

DAO 接口：

```java
/**
	 * 传入员工编号，获得和员工姓名，薪资，部门名称和部门位置
	 */
	
Emp queryEmp_Dept(int empno);
```

DAO层实现类：

```java
	@Override
	public Emp queryEmp_Dept(int empno) {
		StringBuilder sql = new StringBuilder()
				.append("select e.empno,e.ename,e.sal,d.dname,d.loc ")
				.append("from emp e,dept d ")
				.append("where e.deptno=d.deptno and e.empno=?");
		
		
		RowMapper<Emp> rw2 = r -> {
			Emp emp = null;
			try {
				emp =new Emp(r.getInt(1), r.getString(2), r.getDouble(3),new Dept(r.getString(4), r.getString(5)));
			} catch (SQLException e) {
				// TODO Auto-generated catch block
				e.printStackTrace();
			}
			return emp;
		};
		
		ArrayList<Emp> list = query(sql.toString(),rw2,empno);
		
		return list.size() > 0 ? list.get(0) : null;
		
	}
```



#### 4.10 分页查询

> 对表中查询的数据进行分页
>
> 1. 表中总记录数
> 2. 一页显示几个 
> 3. 计算总页数  1 ~ n
> 4.  当前第几页  1   ORACLE  实现分页查询  ROWNUM伪列    Mysql实现分页查询  limit函数
> 5. 数据的起始下标值

分页相关的参数封装到类 ： Pager

```java
package com.cl.jdbc.common;
/**
 * 	页码相关信息
 * @author 86136
 *
 */
public class Pager {
	private int counts; // 总记录数
	private int pages; //总页数
	private int num = 6; //一页显示几个
	private int curr; //当前页码
	private int start ;//查询起始位置
	private int end; // 查询结束位置
	
	//创建页码
	public Pager(int curr) {
		
		this.curr = curr;
		
		//起始位置
		this.start =  (curr - 1) * num + 1;
		
		//终止位置
		this.end = start + num  - 1;
		
	}
	//设置总数
	public void setCounts(int counts) {
		this.counts = counts;
		//页码
		this.pages = counts % num == 0 ? counts / num : counts / num + 1;
	}
	
	public int getCounts() {
		return counts;
	}
	
	public int getPages() {
		return pages;
	}
	public void setPages(int pages) {
		this.pages = pages;
	}
	public int getNum() {
		return num;
	}
	public void setNum(int num) {
		this.num = num;
	}
	public int getCurr() {
		return curr;
	}
	public void setCurr(int curr) {
		this.curr = curr;
	}
	public int getStart() {
		return start;
	}
	public void setStart(int start) {
		this.start = start;
	}
	public int getEnd() {
		return end;
	}
	public void setEnd(int end) {
		this.end = end;
	}
	
}

```

DAO接口分页方法：

```java
	/**
	 * 分页查询
	 */
	ArrayList<Emp> queryAll(int s,int e);
	
	int getCounts();
```

BaseDao:

```java
	public Integer counts(String sql,Object...params) {
		Connection conn = DBUtil.getConn();
		PreparedStatement ste =  null;
		ResultSet r = null;
		int n = 0;
		try {
			ste = conn.prepareStatement(sql);
			if(params != null) {
				for (int i = 0; i < params.length; i++) {
					ste.setObject(i + 1, params[i]);
				}
			}
			
			r = ste.executeQuery();
			if(r.next()) {
				n = r.getInt(1);
			}

		}catch(SQLException ex) {
			ex.printStackTrace();
		}finally {
			//6 关闭
			DBUtil.close(conn, ste);
		}
		return n;
	}
```

实现类:

```java
@Override
	public ArrayList<Emp> queryAll(int s, int e) {
		StringBuilder sql = new StringBuilder()
				.append("SELECT empno,ename,sal,hiredate ")
				.append("FROM (SELECT ROWNUM r,emp.* FROM emp) e ")
				.append("WHERE e.r BETWEEN ? AND ?");
			
		return query(sql.toString(), rw, s,e);
	}

	@Override
	public int getCounts() {
		String sql = "select count(*) from emp";
		
		return counts(sql);
	}
```

测试：

```java
public class TestPager {
	public static void main(String[] args) {
		EmpDaoImpl dao = new EmpDaoImpl();
		//1 创建Pager
		
		Pager p = new Pager(2);
		
		//2 总数查询赋值
		p.setCounts(dao.getCounts());
		
		for (Emp e : dao.queryAll(p.getStart(), p.getEnd())) {
			System.out.println(e);
		}
	}
}
```



#### 4.11 业务逻辑层

> service ： 服务，业务。 
>
> business ： 商务    
>
> biz 
>
> 业务层粗粒度： 一个方法会做好几个DAO【一个方法完成好几个步骤】
>
> 业务层趋向于客户的需求，数据层趋向于数据库操作
>
> 
>
> 登录系统  login()    query()
>
> 注册     register()    add()
>
> 购物车购买  buy()     delete()  add()  
>
> 转账业务  transfer()    1. 查询转账账户是否存在  2. 查询当前账户余额  3 当前账户修改  4 转账账户修改 
>
> 事务： 一定在业务层



分页业务：

接口:

```java
public interface IEmpService {
	
	/**
	 * 分页查询
	 */
	
	ArrayList<Emp> queryByPager(Pager p);
	
}

```

实现类:

```java
public class EmpServiceImpl implements IEmpService{
	
	//对象包含
	IEmpDao dao = new EmpDaoImpl();
	
	@Override
	public ArrayList<Emp> queryByPager(Pager p) {
		//1. 需要查询原表总数
		int c = dao.getCounts();
		p.setCounts(c);
		
		//2 .调分页查询
		return dao.queryAll(p.getStart(), p.getEnd());
	}

}
```

测试类:

```java
public class TestPager {
	public static void main(String[] args) {
		
		IEmpService ser = new EmpServiceImpl();
		
		for (Emp e : ser.queryByPager(new Pager(2))) {
			System.out.println(e);
		}
	}
}
```



#### 4.12 项目分层

> 分为三层：  
>
> ​	表示层【视图层】： 界面 UI 控制台 ， HTML ...
>
> ​	业务层【功能】 ： 被UI界面调用，完成功能
>
>    数据层【CRUD】： 增删改查
>
> 目的 ： 高内聚  低耦合

![](img\2.png)

项目结构：

![](img\3.png)



数据分析： 

e-r图

教师表：表名 teacher

| 字段    | 类型         | 备注 |
| ------- | ------------ | ---- |
| tno     | number(6)    | 主键 |
| tname   | varchar2(20) | 非空 |
| tel     | varchar2(11) | 唯一 |
| tpass   | varchar2(6） |      |
| subject | varchar2(20) |      |
| role    | number(1)    |      |

```sql
CREATE TABLE teacher(
       tno NUMBER(6) PRIMARY KEY,
       tname VARCHAR2(20) NOT NULL,
       tel varchar2(11) UNIQUE,
       tpass VARCHAR2(6),
       subject VARCHAR2(20),
       ROLE NUMBER(1)
)
```

pojo:

```java
public class Teacher {
	private int tno;
	private String tname;
	private String tel;
	private String tpass;
	private String subject;
	private int role;
	public int getTno() {
		return tno;
	}
	public void setTno(int tno) {
		this.tno = tno;
	}
	public String getTname() {
		return tname;
	}
	public void setTname(String tname) {
		this.tname = tname;
	}
	public String getTel() {
		return tel;
	}
	public void setTel(String tel) {
		this.tel = tel;
	}
	public String getTpass() {
		return tpass;
	}
	public void setTpass(String tpass) {
		this.tpass = tpass;
	}
	public String getSubject() {
		return subject;
	}
	public void setSubject(String subject) {
		this.subject = subject;
	}
	public int getRole() {
		return role;
	}
	public void setRole(int role) {
		this.role = role;
	}
	public Teacher(int tno, String tname, String tel, String tpass, String subject, int role) {
		super();
		this.tno = tno;
		this.tname = tname;
		this.tel = tel;
		this.tpass = tpass;
		this.subject = subject;
		this.role = role;
	}
	public Teacher() {
		
	}
	public Teacher(int tno, String tpass) {
		super();
		this.tno = tno;
		this.tpass = tpass;
	}
	@Override
	public String toString() {
		return "Teacher [tno=" + tno + ", tname=" + tname + ", tel=" + tel + ", tpass=" + tpass + ", subject=" + subject
				+ ", role=" + role + "]";
	}
	
	
	
}
```

DAO层：

```java
public interface ITeacherDao {
	/**
	 * 查询
	 * @param tno
	 * @return
	 */
	Teacher queryByNo(int tno);
}

```

实现类：

```java
package com.cl.edu.dao;

import java.sql.ResultSet;
import java.sql.SQLException;
import java.util.ArrayList;

import com.cl.edu.common.BaseDao;
import com.cl.edu.common.RowMapper;
import com.cl.edu.pojo.Teacher;

public class TeacherDaoImpl extends BaseDao<Teacher> implements ITeacherDao{
	
	RowMapper<Teacher> t = new RowMapper<Teacher>() {

		@Override
		public Teacher getRow(ResultSet r) {
			Teacher tt = null;
			try {
				tt = new Teacher(r.getInt(1),r.getString(2),r.getString(3));
			} catch (SQLException e) {
				// TODO Auto-generated catch block
				e.printStackTrace();
			}
			return tt;
		}
	};
	

	@Override
	public Teacher queryByNo(int tno) {
		ArrayList<Teacher> list = query("select tno,tname,tpass from teacher where tno=?", t, tno);
	
		return list.size() > 0 ? list.get(0) : null;
	}

}

```

Service:

```java
public interface ITeacherService {
	
	/**
	 * 登录业务 功能
	 * @param 客户的登录信息
	 * @return int 0 成功  1 账号错误  2 密码错误
	 */
	
	public int login(Teacher t); 
}

```

实现类：

```java
package com.cl.edu.service;

import com.cl.edu.dao.ITeacherDao;
import com.cl.edu.dao.TeacherDaoImpl;
import com.cl.edu.pojo.Teacher;

public class TeacherServiceImpl implements ITeacherService{
	
	private ITeacherDao dao = new TeacherDaoImpl();
	/**
	 * t 用户输入填写
	 * teacher 数据库账户
	 */
	@Override
	public int login(Teacher t) {
		
		Teacher teacher = dao.queryByNo(t.getTno());
		if(teacher == null ) {
			//账号错误
			return 1;
		}else {
			if(teacher.getTpass().equals(t.getTpass())) {
				return 0;
			}else {
				return 2;
			}
		}
	}

}

```


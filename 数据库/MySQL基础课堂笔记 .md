#  今日内容

1. 数据库的基本概念


2. MySQL数据库软件
	1. 安装
	2. 卸载
	3. 配置

3. SQL


## **数据库的基本概念**
	1. 数据库的英文单词： DataBase 简称 ： DB
	2. 什么数据库？
		* 用于存储和管理数据的仓库。
	
	3. 数据库的特点：
		1. 持久化存储数据的。其实数据库就是一个文件系统
		2. 方便存储和管理数据
		3. 使用了统一的方式操作数据库 -- SQL


​	
​	4. 常见的数据库软件
​		* 参见《MySQL基础.pdf》


# MySQL数据库软件
```sql
1. 安装
	* 参见《MySQL基础.pdf》
2. 卸载
	1. 去mysql的安装目录找到my.ini文件
		* 复制 datadir="C:/ProgramData/MySQL/MySQL Server 5.5/Data/"
	2. 卸载MySQL
	3. 删除C:/ProgramData目录下的MySQL文件夹。
	
3. 配置
	* MySQL服务启动
		1. 手动。
		2. cmd--> services.msc 打开服务的窗口
		3. 使用管理员打开cmd
			* net start mysql : 启动mysql的服务
			* net stop mysql:关闭mysql服务
	* MySQL登录
		1. mysql -uroot -p密码
		2. mysql -hip -uroot -p连接目标的密码##ip就是比如127.0.0.1
		3. mysql --host=ip --user=root --password=连接目标的密码
	* MySQL退出
		1. exit
		2. quit

	* MySQL目录结构
		1. MySQL安装目录：basedir="D:/develop/MySQL/"
			* 配置文件 my.ini
		2. MySQL数据目录：datadir="C:/ProgramData/MySQL/MySQL Server 5.5/Data/"
			* 几个概念
				* 数据库：文件夹
				* 表：文件
				* 数据：数据
```

![image-20201105091656965](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201105091656965.png)

 

# 完整1

​	一、为什么要学习数据库
​	二、数据库的相关概念      
​		DBMS、DB、SQL
​	三、数据库存储数据的特点
​	四、初始MySQL
​		MySQL产品的介绍        
​		MySQL产品的安装          ★        
​		MySQL服务的启动和停止     ★
​		MySQL服务的登录和退出     ★      
​		MySQL的常见命令和语法规范      
​	五、DQL语言的学习   ★              
​		基础查询        ★             
​		条件查询  	   ★			
​		排序查询  	   ★				
​		常见函数        ★               
​		分组函数        ★              
​		分组查询		   ★			
​		连接查询	 	★			
​		子查询       √                  
​		分页查询       ★              
​		union联合查询	√			
​		

	六、DML语言的学习    ★             
		插入语句						
		修改语句						
		删除语句						
	七、DDL语言的学习  
		库和表的管理	 √				
		常见数据类型介绍  √          
		常见约束  	  √			
	八、TCL语言的学习
		事务和事务处理                 
	九、视图的讲解           √
	十、变量                      
	十一、存储过程和函数   
	十二、流程控制结构       

## 	一、为什么要学习数据库

##数据库的好处
	1.持久化数据到本地
	2.可以实现结构化查询，方便管理
	

## 二、数据库的相关概念 

##数据库相关概念
	1、DB：数据库，保存一组有组织的数据的容器
	2、DBMS：数据库管理系统，又称为数据库软件（产品），用于管理DB中的数据
	3、SQL:结构化查询语言，用于和DBMS通信的语言

## 三、数据库存储数据的特点

##数据库存储数据的特点
	1、将数据放到表中，表再放到库中
	2、一个数据库中可以有多个表，每个表都有一个的名字，用来标识自己。表名具有唯一性。
	3、表具有一些特性，这些特性定义了数据在表中如何存储，类似java中 “类”的设计。
	4、表由列组成，我们也称为字段。所有表都是由一个或多个列组成的，每一列类似java 中的”属性”
	5、表中的数据是按行存储的，每一行类似于java中的“对象”。

## 	四、初始MySQL

### 1.MySQL产品的介绍和安装

###MySQL服务的启动和停止
	方式一：计算机——右击管理——服务
	方式二：通过管理员身份运行
	net start 服务名（启动服务）
	net stop 服务名（停止服务）


###MySQL服务的登录和退出   
	方式一：通过mysql自带的客户端
	只限于root用户

	方式二：通过windows自带的客户端
	登录：
	mysql 【-h主机名 -P端口号 】-u用户名 -p密码
	
	退出：
	exit或ctrl+C

​	
​	
​	

### 2.MySQL的常见命令 

	1.查看当前所有的数据库
	show databases;
	2.打开指定的库
	use 库名
	3.查看当前库的所有表
	show tables;
	4.查看其它库的所有表
	show tables from 库名;
	5.创建表
	create table 表名(
	
		列名 列类型,
		列名 列类型，
		。。。
	);
	6.查看表结构
	desc 表名;


	7.查看服务器的版本
	方式一：登录到mysql服务端
	select version();
	方式二：没有登录到mysql服务端
	mysql --version
	或
	mysql --V



### 3.MySQL的语法规范

​	1.不区分大小写,但建议关键字大写，表名、列名小写
​	2.每条命令最好用分号结尾
​	3.每条命令根据需要，可以进行缩进 或换行
​	4.注释
​		单行注释：#注释文字
​		单行注释：-- 注释文字
​		多行注释：/* 注释文字  */
​	
​	
​	

### 4.SQL的语言分类

​	DQL（Data Query Language）：数据查询语言
​		select 
​	DML(Data Manipulate Language):数据操作语言
​		insert 、update、delete
​	DDL（Data Define Languge）：数据定义语言
​		create、drop、alter
​	TCL（Transaction Control Language）：事务控制语言
​		commit、rollback
​	



### 4.SQL的常见命令

```sql
show databases； 查看所有的数据库
use 库名； 打开指定 的库
show tables ; 显示库中的所有表
show tables from 库名;显示指定库中的所有表
create table 表名(
	字段名 字段类型,	
	字段名 字段类型
); 创建表

desc 表名; 查看指定表的结构
select * from 表名;显示表中的所有数据
```



## 五、DQL语言的学习

### 进阶1：基础查询

​	语法：
​

```sql
	SELECT  要查询的东西  FROM  表名;
```



```SQL
类似于Java中 :System.out.println(要打印的东西);
特点：
①通过select查询完的结果 ，是一个虚拟的表格，不是真实存在
② 要查询的东西 可以是常量值、可以是表达式、可以是字段、可以是函数
```

起别名：

```sql
SELECT 100%98 AS 结果;

SELECT last_name AS 姓 , first_name AS 名 FROM employees;
# AS 可以省略

SELECT salary AS "out put" FROM employees;
#有空格别名

#去重
SELECT DISTINCT department_id FROM employees;

##################  字符串如何拼接起来   #############
# + 的左右
# 查询员工姓和名连接成一个字段，并显示为 姓名
SELECT last_name+first_name AS 姓名 FROM employees;#这样不对

/*
Java中的+号
（1）运算符（数值）
（2）连接符（字符串）

mysql的+号
仅仅一个功能，运算符

select 100+90;两个操作数都是数值型，则做加法运算
select '123'+90;其中一方为字符型，试图将字符型数值转换成数值型
		如果转换成功，则继续做加法运算
		如果转换失败，则将字符型数值转换成0
select 'john'+90;

select null+0;只要一方为null，结果必为null

*/
#利用concat函数
SELECT CONCAT('a','b','c') AS 结果;
SELECT CONCAT(last_name,'  ',first_name) AS 姓名
FROM employees;

#替换null
SELECT IFNULL(commission_pct,0) AS 奖金率,commission_pct FROM employees;
```







### 进阶2：条件查询

​	条件查询：根据条件过滤原始表的数据，查询到想要的数据
​	语法：
​	select 
​		要查询的字段|表达式|常量值|函数
​	from 
​		表
​	where 
​		条件 ;

```sql
分类：
一、条件表达式
	示例：salary>10000
	条件运算符：
	> < >= <= = != <>

二、逻辑表达式
示例：salary>10000 && salary<20000

逻辑运算符：

	and（&&）:两个条件如果同时成立，结果为true，否则为false
	or(||)：两个条件只要有一个成立，结果为true，否则为false
	not(!)：如果条件成立，则not后为false，否则为true

三、模糊查询
示例：last_name like 'a%'
```







```sql
#进阶2：条件查询
/*语法
	select 
		查询列表
	from 
		表名
	where
		筛选条件
		
分类：
（1）按条件表达式（<、>、=、!=、<>、>=、<=）
（2）按逻辑表达式筛选（逻辑运算符: && || !）
（3）模糊查询
	like 
	1）一般和通配符搭配使用，通配符： %  表示任意多个字符，包含0个字符
					  _  表示一个字符
					  escape 转译符
	between and
	1)可以提高语言的简洁度
	2)包含临界值
	3)两个临界值不要调换顺序
	in 
	is null
*/

#按条件表达式查询
#案例1：查询工资大于12000的员工
SELECT * FROM employees WHERE salary>12000;

SELECT last_name FROM employees WHERE department_id!=90;

#按逻辑表达式查询
SELECT 
  CONCAT(last_name, '  ',first_name) AS 姓名,
  salary 
FROM
  employees 
WHERE salary > 10000 && salary < 20000;


SELECT 
  CONCAT(last_name, '  ',first_name) AS 姓名,
  salary 
FROM
  employees 
WHERE salary > 10000 AND salary < 20000;


#模糊查询
#(1)like
#案例：查询员工名中包含字符a的员工信息
SELECT * FROM employees WHERE last_name LIKE '%a%';
#转译 ESCAPE
SELECT last_name FROM employees WHERE last_name LIKE '_\_%';
SELECT last_name FROM employees WHERE last_name LIKE '_$_%' ESCAPE '$';

#(2)between and
#案例：查询员工编号在100到120之间的
SELECT * FROM employees WHERE employee_id>=100&&employee_id<=120;

SELECT * FROM employees WHERE employee_id BETWEEN 100 AND 120; 

#(3)in
#案例：查询员工的工种编号十 IT_PROG AD_VP AD_PRES 的一个员工名和工种编号
SELECT last_name, job_id FROM employees WHERE job_id = 'IT_PROT' OR job_id='AD_PRES';

SELECT last_name, job_id FROM employees WHERE job_id IN( 'IT_PROT' , 'AD_PRES');



#(4) is null
#案例：查询没有奖金的员工名和奖金率
SELECT last_name,commission_pct FROM employees WHERE commission_pct = NULL; #错误 ，=不能判断null

SELECT last_name,commission_pct FROM employees WHERE commission_pct IS NULL;

SELECT last_name,commission_pct FROM employees WHERE commission_pct IS NOT NULL;







 
```

**注意：**

- is null : 仅仅可以判断null值
- <=>:既可以判断null值，又可以判断普通的数值

#### 练习

经典面试题：

试问：

```sql
select * from employees;
和
select * from employees where commission_pct like '%%' and last_name like '%%';
结果一样吗？并说明原因
不一样！
如果判断的字段有null值（or可以），like不到null


```





### 进阶3：排序查询	

​	

```sql
语法：
select
	要查询的东西
from
	表
where 
	条件

order by 排序的字段|表达式|函数|别名 【asc|desc】
```

#### 	注意

- asc代表的是升序，desc代表的是降序（如果不写，默认是升序）
- order by子句中可以支持单个字段，多个字段、表达式、函数、别名
- order by子句一般是放在查询语句的最后面，limit子句除外

```sql
# is null
#案例：查询没有奖金的员工名和奖金率
SELECT last_name,commission_pct FROM employees WHERE commission_pct = NULL; #错误 ，=不能判断null

SELECT last_name,commission_pct FROM employees WHERE commission_pct IS NULL;

SELECT last_name,commission_pct FROM employees WHERE commission_pct IS NOT NULL;
```

```sql
/*
引入：
	select * from employees;
语法：
	select 查询列表
	from 表
	【where 筛选条件】
	order by 排序列表 asc|desc
*/

SELECT last_name,salarys FROM employees ORDER BY salary ASC;

SELECT salary*12*(1+IFNULL(commission_pct,0)) 年薪 
FROM employees
ORDER BY salary*12*(1+IFNULL(commission_pct,0)) ASC;

#主要排序和次要排序


SELECT last_name,salary FROM employees ORDER BY salary ASC , job_id ASC;
```



### 进阶4：常见函数

**常见函数**

	**功能**：类似于java的方法：将一组逻辑语句封装在方法中，对外暴露方法名
	**好处**：1、隐藏了实现细节 2、提高代码重用性
	**调用**：select 函数么（实参列表） 【from 表】；
	**特点**：
		1）函数名
		2）函数功能
	**分类**：
		1）单行函数
		如concat、length、ifnull等
		2）分组函数
		
		功能：做统计使用，又称为统计函数、聚合函数、组函数

*/	





#### 4.1字符控制函数

![image-20201009204511236](D:\h后端\imgs\image-20201009204511236.png)





#### 4.2数字函数

![image-20201009204541327](D:\h后端\imgs\image-20201009204541327.png)





#### 4.3日期函数

![image-20201009204555223](D:\h后端\imgs\image-20201009204555223.png)

![image-20201009204612815](D:\h后端\imgs\image-20201009204612815.png)



#### 4.4其他函数

```sql
SELECT VERSION();  #查看版本号
SELECT DATABASE();   #查看当前数据库 ，注意不带s
SELECT USER();    #当前用户
```



#### 4.5流程控制函数

##### 1.if函数： if else 的效果

```sql
SELECT IF(10>5,'大','小');


SELECT last_name ,commission_pct , IF(commission_pct IS NULL,'无奖金','有奖金') FROM employees ;

```



2.case函数的使用一 ： switch case的效果

java中 

```java
switch(变量表达式){

	case 常量1： 语句1： break;

	...

	default: 语句n ； break

}
```



MYSQL中（**等值判断**）

```sql
case 要判断的字段或表达十
when 常量1 then 要显示的值1或语句1；
when 常量1 then 要显示的值2或语句2；
...
else 要显示的值n或语句n；
end



例子：
SELECT salary AS 工资 ,department_id,

CASE  department_id
WHEN 30 THEN salary*1.1
WHEN 40 THEN salary*1.2
WHEN 50 THEN salary*1.3
ELSE salary
END AS 新工资
FROM employees;


```

（**区间判断**）

```mysql
case 
when 条件1 then 要显示的值1或语句1
when 条件2 then 要显示的值2或语句2
...
else 要显示的值n或语句n
end


# case 函数使用2 类似java中if else  区间判断

SELECT salary ,CASE
WHEN salary>20000 THEN 'A'
WHEN salary>15000 THEN 'B'
WHEN salary>10000 THEN 'C'
ELSE 'D'
END AS 工资级别
FROM employees;
```





一、单行函数
​	1、字符函数
​		concat拼接
​		substr截取子串
​		upper转换成大写
​		lower转换成小写
​		trim去前后指定的空格和字符
​		ltrim去左边空格
​		rtrim去右边空格
​		replace替换
​		lpad左填充
​		rpad右填充
​		instr返回子串第一次出现的索引
​		length 获取字节个数
​		

```sql
2、数学函数
	round 四舍五入
	rand 随机数
	floor向下取整
	ceil向上取整
	mod取余
	truncate截断
3、日期函数
	now当前系统日期+时间
	curdate当前系统日期
	curtime当前系统时间
	str_to_date 将字符转换成日期
	date_format将日期转换成字符
4、流程控制函数
	if 处理双分支
	case语句 处理多分支
		情况1：处理等值判断
		情况2：处理条件判断
	
5、其他函数
	version版本
	database当前库
	user当前连接用户
```

​	

#### 【注】java中switch与mysql中swicth的区别

```java
java中
    switch(变量或表达式) {
        case 1: 语句1 ; break;
        case 2: 语句2 ; break;
            ...
        default: 语句n ; break;
    }
```



```mysql
mysql中（等值判断）
case 要判断的字段或表达式
when 常量1 then 要显示的值1或者语句1；
when 常量2 then 要显示的值2或者语句2；
...
else 要显示的值n或者语句n；
end



（区间判断）
case 
when 常量1 then 要显示的值1或者语句1；
when 常量2 then 要显示的值2或者语句2；
...
else 要显示的值n或者语句n；
end




#case 函数使用1（类似java中switch   等值判断）
SELECT salary AS 工资 ,department_id,

CASE  department_id
WHEN 30 THEN salary*1.1
WHEN 40 THEN salary*1.2
WHEN 50 THEN salary*1.3
ELSE salary
END AS 新工资
FROM employees;

# case 函数使用2 类似java中if else  区间判断

SELECT salary ,
CASE
WHEN salary>20000 THEN 'A'
WHEN salary>15000 THEN 'B'
WHEN salary>10000 THEN 'C'
ELSE 'D'
END AS 工资级别
FROM employees;
```





5.分组函数


```sql
	sum 求和
	max 最大值
	min 最小值
	avg 平均值
	count 计数

	特点：
	1、以上五个分组函数都忽略null值，除了count(*)
	2、sum和avg一般用于处理数值型
		max、min、count可以处理任何数据类型
    3、都可以搭配distinct使用，用于统计去重后的结果
	4、count的参数可以支持：
		字段、*、常量值，一般放1

	   建议使用 count(*)
```













### 进阶5：分组查询

#### 	5.1分组函数

```sql
#二、分组函数
/*
功能：用于统计使用，又称为聚合函数或统计函数或组函数

分类：
sum 求和 、 avg 平均值 、max 最大值 、 min 最小值 、 count 计算个数

2、参数支持哪些类型
	1、sum、avg一般用于处理数值型
	   max、min、count可以处理任何类型
	2、是否忽略null值
		忽略了null！！
	3、可以和distinct搭配实现去重的运算
	4、count函数的单独介绍
	5、和分组函数一同查询的字段有限制
		
*/

SELECT SUM(salary) FROM employees;
#1
SELECT SUM(last_name) ,AVG(last_name) FROM employees;##错误，结果为0
SELECT MAX(last_name) ,MIN(last_name) FROM employees;##这样可以比较，还ok
#2
SELECT SUM(commission_pct),AVG(commission_pct),SUM(commission_pct)/35,SUM(commission_pct)/107
FROM employees;
#3
SELECT SUM(DISTINCT salary) ,SUM(salary) FROM employees;
#4
SELECT COUNT(salary) FROM employees;

SELECT COUNT(*) FROM employees;

SELECT COUNT(1) FROM employees;

#效率
#MYISAM存储引擎下， count(*)的效率高
#INNODB存储引擎下， count(*)和count(1)的效率差不多，但比count(字段)要高一些

#5
SELECT AVG(salary) , employee_id FROM employees;#没有意义，avg返回只有一位

```

#### 5.2分组查询

语法：
	select 查询的字段，分组函数
	from 表
	group by 分组的字段
![image-20201010211406848](D:\后端\mySQL\image-20201010211406848.png)
	[**注意**]GROUP BY 后面的条件判断可以用having！！！！！！！！！！！







```sql
#进阶5 ： 分组查询
/*
语法：
	select 分组函数、列（要求出现再group by的后面）
	from 表
	【where 筛选条件】
	group by 分组的列表
	【order by 子句】
注意
	查询列表必须特殊，要求是分组函数和group by后出现的字段
	
*/
```

##### 分组后的筛选

```sql
特点：
1、分组查询中的筛选条件分为两类
		    针对的表	        位置			      关键字
分组前筛选：	 原始表		    group by的前面		  where
分组后筛选：	分组后的结果集	     group by的后面        having

1）分组函数做条件肯定放在having子句中
2）能用分组前筛选的，就尽量分组前筛选sql

2、group by子句支持单个字段分组，多个字段分组（多个字段逗号隔开，没有顺序要求），表达式或函数（用的较少）
3、也可以添加排序（排序放在整个分组查询最后）


```





### 进阶6：多表连接查询

	笛卡尔乘积：如果连接条件省略或无效则会出现
	解决办法：添加上连接条件

有笛卡尔乘积现象，解决办法：**添加上连接条件**

![image-20201012211329906](D:\h后端\imgs\image-20201012211329906.png)



**含义：**又称多表查询，当查询的字段来自于多个表时，就会用到连接查询

笛卡尔乘积现象：表1 有m行，表2有n行，结果=m*n行

发生原因：没有有效的连接条件

如何避免：添加有效的连接条件



**分类：**

- 按年代分类：sql92标准（仅仅支持内连接）

  ​		   			**sql99标准【推荐】**（支持内连接+外连接（左外+右外）+交叉连接）

- 按功能分类：内连接（等值连接，非等值连接，自连接），

​						      外连接（左外连接，右外连接，全外连接），

​					      	交叉连接







#### 1、传统模式下的连接 ：等值连接——非等值连接

##### 1.等值连接

![image-20201020210914174](D:\h后端\imgs\image-20201020210914174.png)

2.非等值连接

![image-20201020211927851](D:\h后端\imgs\image-20201020211927851.png)






```SQL
1.等值连接的结果 = 多个表的交集
2.n表连接，至少需要n-1个连接条件
3.多个表不分主次，没有顺序要求
4.一般为表起别名，提高阅读性和性能


SELECT NAEM,boyName
FROM boys,beauty
WHERE beauty.boyfriend_id = boys.id %等值连接


```

#### 2、sql99语法：通过join关键字实现连接

分类：

**内连接**：inner

外连接

- **左外**：left [outer]
- **右外**：right [outer]
- 全外：full [outer]

交叉连接:cross

```sql
含义：1999年推出的sql语法
支持：
等值连接、非等值连接 （内连接）
外连接
交叉连接

语法：

select 字段，...
from 表1
【inner|left outer|right outer|cross】join 表2 on  连接条件
【inner|left outer|right outer|cross】join 表3 on  连接条件
【where 筛选条件】
【group by 分组字段】
【having 分组后的筛选条件】
【order by 排序的字段或表达式】

好处：语句上，连接条件和筛选条件实现了分离，简洁明了！
```

#### 3、外连接

应用场景：用于查询一个表中有，另一个表没有的记录

特点：

1、外连接的查询结果为主表中的所有记录

- 如果从表中有和它匹配的，则显示匹配的值
- 如果从表中没有和它匹配的，则显示null
- 外连接查询结果=内连接结果+主表中有而从表没有的记录

2、左外连接：left join左边的是主表

​      右外连接：right join右边的是主表

3、左外和右外交换两个表的顺序，可以实现同样的效果

4、全外连接=内连接的结果+表1中有但表2没有的+表2中有但表1没有的



#### 4、交叉连接

其实就是笛卡尔乘积

```sql
SELECT b.* , bo.*
FROM beauty b
CROSS JOIN boys bo；
```



#### 5、自连接（内连接一种）

案例：查询员工名和直接上级的名称

sql99

```sql
SELECT e.last_name,m.last_name
FROM employees e
JOIN employees m ON e.`manager_id`=m.`employee_id`;
```

sql92


```sql
SELECT e.last_name,m.last_name
FROM employees e,employees m 
WHERE e.`manager_id`=m.`employee_id`;
```





#### 6、总结

![image-20201022202215179](D:\h后端\imgs\image-20201022202215179.png)

![image-20201022202245704](D:\h后端\imgs\image-20201022202245704.png)

![image-20201022202326465](D:\h后端\imgs\image-20201022202326465.png)





### 进阶7：子查询

含义：

```sql
一条查询语句中又嵌套了另一条完整的select语句，其中被嵌套的select语句，称为子查询或内查询
在外面的查询语句，称为主查询或外查询
```

特点：

```sql
1、子查询都放在小括号内
2、子查询可以放在from后面、select后面、where后面、having后面，但一般放在条件的右侧
3、子查询优先于主查询执行，主查询使用了子查询的执行结果
4、子查询根据查询结果的行数不同分为以下两类：
① 单行子查询
	结果集只有一行
	一般搭配单行操作符使用：> < = <> >= <= 
	非法使用子查询的情况：
	a、子查询的结果为一组值
	b、子查询的结果为空
	
② 多行子查询
	结果集有多行
	一般搭配多行操作符使用：any、all、in、not in
	in： 属于子查询结果中的任意一个就行
	any和all往往可以用其他查询代替
```



![](D:\h后端\imgs\image-20201022210446415.png)









1.放在where或having后面

1）标量子查询（单行子查询）

![image-20201026202610398](D:\h后端\imgs\image-20201026202610398.png)



```sql
#案例1：谁的工资比Abel高
#①查询Abel的工资
SELECT salary
FROM employees
WHERE last_name = 'Abel';
#②查询员工的信息，满足 salary>①结果
SELECT *
from employees
where salary > (
    
	SELECT salary
	FROM employees
	WHERE last_name = 'Abel';
    
)


#案例4：查询最低工资大于50号部门最低工资的部门id和其最低工资
SELECT MIN(salary) , department_id
FROM employees
GROUP BY department_id
HAVING MIN(salary) > (
	SELECT MIN(salary)
	FROM employees
	WHERE department_id = 50
)
```



#### 2）列子查询（多行子查询）

![image-20201026204041090](D:\h后端\imgs\image-20201026204041090.png)

```sql
#2.列子查询（多行子查询）
#案例1：返回locatian_id是1400或1700的部门中的所有员工姓名

#①查询location_id是1400或1700的部门编号
SELECT DISTINCT department_id
FROM departments
WHERE location_id IN (1400,1700);

#查询员工姓名，要求部门号是①列表中的某一个
SELECT last_name
FROM employees
WHERE department_id IN(
	SELECT DISTINCT department_id
	FROM departments
	WHERE location_id IN (1400,1700)	
);



#案例2：返回其他工种中比job_id为‘IT_DPOG’部门任一工资低的员工的员工号、姓名、job_id以及salary

#①查询job_id为‘IT_PROG’部门任一工资

SELECT DISTINCT salary 
FROM employees
WHERE job_id = 'IT_PROG';

#②查询员工号、姓名、job_id以及salary,salary<(①)的任意结果
SELECT employee_id ,last_name,job_id,salary
FROM employees
WHERE salary <ANY(
	SELECT DISTINCT salary 
	FROM employees
	WHERE job_id = 'IT_PROG'
) AND job_id<>'IT_PROG';
#any很多时候可以替换
SELECT employee_id ,last_name,job_id,salary
FROM employees
WHERE salary <(
	SELECT DISTINCT MAX(salary) 
	FROM employees
	WHERE job_id = 'IT_PROG'
) AND job_id<>'IT_PROG';


```



#### 3）行字查询（多列子查询）

```sql
#行子查询（结果集一行多列或多行多列）
#比较啰嗦，用的较少，了解即可

#案例：查询员工编号最小并且工资最高的员工信息

#①查询最小的员工编号
SELECT	MIN(employee_id)
FROM employees;

#②查询最高的工资
SELECT MAX(salary)
FROM employees;

#③查询员工信息
SELECT *
FROM employees
WHERE employee_id = (
	SELECT	MIN(employee_id)
	FROM employees
) AND salary = (
	SELECT MAX(salary)
	FROM employees
);

#合体！
SELECT *
FROM employees
WHERE (employee_id,salary) = (
	SELECT	MIN(employee_id),MAX(salary)
	FROM employees
) 
```



#### 2.放在select后面的子查询：

select后面只能标量子查询（**一行一列**）

```sql
#案例：查询每个部门的员工个数
SELECT d.*,(
	SELECT	COUNT(*)
	FROM employees e
	WHERE e.department_id = d.`department_id`
)
FROM departments d; 



#案例2：查询员工号=102的部门名
#连接查询
SELECT (
	SELECT department_name
	FROM departments d
	INNER JOIN employees e
	ON d.department_id = e.department_id
	WHERE e.employee_id=102
)；
```



#### 3.放在from后面



```sql
#案例：查询每个部门的平均工资的工资等级

#查询每个部门的平均工资
SELECT AVG(salary)
FROM employees
GROUP BY department_id;

#②连接①的结果集和job_grades表，筛选条件平均工资  between_lowest_sal and highest_sal
SELECT ag_dep.* , g.grade_level
FROM (
	SELECT AVG(salary)
	FROM employees
	GROUP BY department_id;
) ag_dep
INNER JOIN job_grades g
ON ag_dep.ag BETWEEN lowest_sal AND highest_sal;

```



#### 4.放在exists后面的子查询（相关子查询）

```sql
/*
	语法：
	exists（完整的查询语句）
	结果：
	1或者0
*/

SELECT EXISTS(
	SELECT
	employee_id
	FROM 
	employees
);#返回Boolean类型，只关心有没有

SELECT department_name
FROM departments d
WHERE EXISTS(
	SELECT *
	FROM employees e
	WHERE e.`department_id`=d.`department_id`
);
```















**特点**：

- 子查询放在小括号内
- 子查询一般放在条件的右侧
- 标量子查询，一般搭配着单行操作符使用（>  <  >=  <=  = <> ）
- 列子查询，一般搭配着多行操作符使用（IN  ANY/SOME ALL）
- 子查询的执行优先于主查询执行，主查询的条件用到了子查询的结果













### 进阶8：分页查询

应用场景：

```sql
实际的web项目中需要根据用户的需求提交对应的分页查询的sql语句
```

语法：

```sql
select 字段|表达式,...
from 表
【join type join 表2
on 连接条件】 
【where 条件】
【group by 分组字段】
【having 条件】
【order by 排序的字段】
limit 起始的条目索引，条目数;（offset,size）
#offset的起始索引从0开始
```

练习：

```sql
#案例1：查询前五条员工信息
SELECT * FROM employees LIMIT 0,5;

SELECT * FROM employees LIMIT 5;

#案例2：查询第11条----第25条
SELECT * FROM employees LIMIT 10,15;

#案例3：有奖金的员工信息，并且工资较高的前10名显示出来
SELECT *
FROM employees
WHERE commission_pct IS NOT NULL
ORDER BY salary DESC
LIMIT 0 , 10;


```

特点：

```sql
1.起始条目索引从0开始

2.limit子句放在查询语句的最后

3.公式：select * from  表 limit （page-1）*sizePerPage,sizePerPage
假如:
每页显示条目数sizePerPage
要显示的页数 page
```

### 进阶9：联合查询

引入：
	union 联合、合并

语法：

```sql
select 字段|常量|表达式|函数 【from 表】 【where 条件】 union 【all】
select 字段|常量|表达式|函数 【from 表】 【where 条件】 union 【all】
select 字段|常量|表达式|函数 【from 表】 【where 条件】 union  【all】
.....
select 字段|常量|表达式|函数 【from 表】 【where 条件】
```

特点：

	1、多条查询语句的查询的列数必须是一致的
	2、多条查询语句的查询的列的类型几乎相同
	3、union代表去重，union all代表不去重


##DML语言

###插入

语法：
	insert into 表名(字段名，...)
	values(值1，...);

特点：

	1、字段类型和值类型一致或兼容，而且一一对应
	2、可以为空的字段，可以不用插入值，或用null填充
	3、不可以为空的字段，必须插入值
	4、字段个数和值的个数必须一致
	5、字段可以省略，但默认所有字段，并且顺序和表中的存储顺序一致

###修改

修改单表语法：

	update 表名 set 字段=新值,字段=新值
	【where 条件】

修改多表语法：

	update 表1 别名1,表2 别名2
	set 字段=新值，字段=新值
	where 连接条件
	and 筛选条件


###删除

方式1：delete语句 

单表的删除： ★
	delete from 表名 【where 筛选条件】

多表的删除：
	delete 别名1，别名2
	from 表1 别名1，表2 别名2
	where 连接条件
	and 筛选条件;


方式2：truncate语句

	truncate table 表名


两种方式的区别【面试题】
	

	#1.truncate不能加where条件，而delete可以加where条件
	
	#2.truncate的效率高一丢丢
	
	#3.truncate 删除带自增长的列的表后，如果再插入数据，数据从1开始
	#delete 删除带自增长列的表后，如果再插入数据，数据从上一次的断点处开始
	
	#4.truncate删除不能回滚，delete删除可以回滚


##DDL语句
###库和表的管理
库的管理：

	一、创建库
	create database 库名
	二、删除库
	drop database 库名

表的管理：
	#1.创建表
	

	CREATE TABLE IF NOT EXISTS stuinfo(
		stuId INT,
		stuName VARCHAR(20),
		gender CHAR,
		bornDate DATETIME


​	
​	);
​	
​	DESC studentinfo;
​	#2.修改表 alter
​	语法：ALTER TABLE 表名 ADD|MODIFY|DROP|CHANGE COLUMN 字段名 【字段类型】;
​	
​	#①修改字段名
​	ALTER TABLE studentinfo CHANGE  COLUMN sex gender CHAR;
​	
​	#②修改表名
​	ALTER TABLE stuinfo RENAME [TO]  studentinfo;
​	#③修改字段类型和列级约束
​	ALTER TABLE studentinfo MODIFY COLUMN borndate DATE ;
​	
​	#④添加字段
​	
​	ALTER TABLE studentinfo ADD COLUMN email VARCHAR(20) first;
​	#⑤删除字段
​	ALTER TABLE studentinfo DROP COLUMN email;


​	
​	#3.删除表
​	
​	DROP TABLE [IF EXISTS] studentinfo;


​	


###常见类型

	整型：
		
	小数：
		浮点型
		定点型
	字符型：
	日期型：
	Blob类型：



###常见约束

	NOT NULL
	DEFAULT
	UNIQUE
	CHECK
	PRIMARY KEY
	FOREIGN KEY

##数据库事务
###含义
	通过一组逻辑操作单元（一组DML——sql语句），将数据从一种状态切换到另外一种状态

###特点
	（ACID）
	原子性：要么都执行，要么都回滚
	一致性：保证数据的状态操作前和操作后保持一致
	隔离性：多个事务同时操作相同数据库的同一个数据时，一个事务的执行不受另外一个事务的干扰
	持久性：一个事务一旦提交，则数据将持久化到本地，除非其他事务对其进行修改

相关步骤：

	1、开启事务
	2、编写事务的一组逻辑操作单元（多条sql语句）
	3、提交事务或回滚事务

###事务的分类：

隐式事务，没有明显的开启和结束事务的标志

	比如
	insert、update、delete语句本身就是一个事务


显式事务，具有明显的开启和结束事务的标志

		1、开启事务
		取消自动提交事务的功能
		
		2、编写事务的一组逻辑操作单元（多条sql语句）
		insert
		update
		delete
		
		3、提交事务或回滚事务

###使用到的关键字

	set autocommit=0;
	start transaction;
	commit;
	rollback;
	
	savepoint  断点
	commit to 断点
	rollback to 断点


###事务的隔离级别:

事务并发问题如何发生？

	当多个事务同时操作同一个数据库的相同数据时

事务的并发问题有哪些？

	脏读：一个事务读取到了另外一个事务未提交的数据
	不可重复读：同一个事务中，多次读取到的数据不一致
	幻读：一个事务读取数据时，另外一个事务进行更新，导致第一个事务读取到了没有更新的数据

如何避免事务的并发问题？

	通过设置事务的隔离级别
	1、READ UNCOMMITTED
	2、READ COMMITTED 可以避免脏读
	3、REPEATABLE READ 可以避免脏读、不可重复读和一部分幻读
	4、SERIALIZABLE可以避免脏读、不可重复读和幻读

设置隔离级别：

	set session|global  transaction isolation level 隔离级别名;

查看隔离级别：

	select @@tx_isolation;



##视图
含义：理解成一张虚拟的表

视图和表的区别：
	

		使用方式	占用物理空间
	
	视图	完全相同	不占用，仅仅保存的是sql逻辑
	
	表	完全相同	占用

视图的好处：


	1、sql语句提高重用性，效率高
	2、和表实现了分离，提高了安全性

###视图的创建
	语法：
	CREATE VIEW  视图名
	AS
	查询语句;
###视图的增删改查
	1、查看视图的数据 ★
	

	SELECT * FROM my_v4;
	SELECT * FROM my_v1 WHERE last_name='Partners';
	
	2、插入视图的数据
	INSERT INTO my_v4(last_name,department_id) VALUES('虚竹',90);
	
	3、修改视图的数据
	
	UPDATE my_v4 SET last_name ='梦姑' WHERE last_name='虚竹';


​	
​	4、删除视图的数据
​	DELETE FROM my_v4;
###某些视图不能更新
​	包含以下关键字的sql语句：分组函数、distinct、group  by、having、union或者union all
​	常量视图
​	Select中包含子查询
​	join
​	from一个不能更新的视图
​	where子句的子查询引用了from子句中的表
###视图逻辑的更新
​	#方式一：
​	CREATE OR REPLACE VIEW test_v7
​	AS
​	SELECT last_name FROM employees
​	WHERE employee_id>100;
​	
​	#方式二:
​	ALTER VIEW test_v7
​	AS
​	SELECT employee_id FROM employees;
​	
​	SELECT * FROM test_v7;
###视图的删除
​	DROP VIEW test_v1,test_v2,test_v3;
###视图结构的查看	
​	DESC test_v7;
​	SHOW CREATE VIEW test_v7;

##存储过程

含义：一组经过预先编译的sql语句的集合
好处：

	1、提高了sql语句的重用性，减少了开发程序员的压力
	2、提高了效率
	3、减少了传输次数

分类：

	1、无返回无参
	2、仅仅带in类型，无返回有参
	3、仅仅带out类型，有返回无参
	4、既带in又带out，有返回有参
	5、带inout，有返回有参
	注意：in、out、inout都可以在一个存储过程中带多个

###创建存储过程
语法：

	create procedure 存储过程名(in|out|inout 参数名  参数类型,...)
	begin
		存储过程体
	
	end

类似于方法：

	修饰符 返回类型 方法名(参数类型 参数名,...){
	
		方法体;
	}

注意

	1、需要设置新的结束标记
	delimiter 新的结束标记
	示例：
	delimiter $
	
	CREATE PROCEDURE 存储过程名(IN|OUT|INOUT 参数名  参数类型,...)
	BEGIN
		sql语句1;
		sql语句2;
	
	END $
	
	2、存储过程体中可以有多条sql语句，如果仅仅一条sql语句，则可以省略begin end
	
	3、参数前面的符号的意思
	in:该参数只能作为输入 （该参数不能做返回值）
	out：该参数只能作为输出（该参数只能做返回值）
	inout：既能做输入又能做输出


#调用存储过程
	call 存储过程名(实参列表)
##函数


###创建函数

学过的函数：LENGTH、SUBSTR、CONCAT等
语法：

	CREATE FUNCTION 函数名(参数名 参数类型,...) RETURNS 返回类型
	BEGIN
		函数体
	
	END

###调用函数
	SELECT 函数名（实参列表）





###函数和存储过程的区别

			关键字		调用语法	返回值			应用场景
	函数		FUNCTION	SELECT 函数()	只能是一个		一般用于查询结果为一个值并返回时，当有返回值而且仅仅一个
	存储过程	PROCEDURE	CALL 存储过程()	可以有0个或多个		一般用于更新


##流程控制结构

###系统变量
一、全局变量

作用域：针对于所有会话（连接）有效，但不能跨重启

	查看所有全局变量
	SHOW GLOBAL VARIABLES;
	查看满足条件的部分系统变量
	SHOW GLOBAL VARIABLES LIKE '%char%';
	查看指定的系统变量的值
	SELECT @@global.autocommit;
	为某个系统变量赋值
	SET @@global.autocommit=0;
	SET GLOBAL autocommit=0;

二、会话变量

作用域：针对于当前会话（连接）有效

	查看所有会话变量
	SHOW SESSION VARIABLES;
	查看满足条件的部分会话变量
	SHOW SESSION VARIABLES LIKE '%char%';
	查看指定的会话变量的值
	SELECT @@autocommit;
	SELECT @@session.tx_isolation;
	为某个会话变量赋值
	SET @@session.tx_isolation='read-uncommitted';
	SET SESSION tx_isolation='read-committed';

###自定义变量
一、用户变量

声明并初始化：

	SET @变量名=值;
	SET @变量名:=值;
	SELECT @变量名:=值;

赋值：

	方式一：一般用于赋简单的值
	SET 变量名=值;
	SET 变量名:=值;
	SELECT 变量名:=值;


	方式二：一般用于赋表 中的字段值
	SELECT 字段名或表达式 INTO 变量
	FROM 表;

使用：

	select @变量名;

二、局部变量

声明：

	declare 变量名 类型 【default 值】;

赋值：

	方式一：一般用于赋简单的值
	SET 变量名=值;
	SET 变量名:=值;
	SELECT 变量名:=值;


	方式二：一般用于赋表 中的字段值
	SELECT 字段名或表达式 INTO 变量
	FROM 表;

使用：

	select 变量名



二者的区别：

			作用域			定义位置		语法

用户变量	当前会话		会话的任何地方		加@符号，不用指定类型
局部变量	定义它的BEGIN END中 	BEGIN END的第一句话	一般不用加@,需要指定类型

###分支
一、if函数
	语法：if(条件，值1，值2)
	特点：可以用在任何位置

二、case语句

语法：

	情况一：类似于switch
	case 表达式
	when 值1 then 结果1或语句1(如果是语句，需要加分号) 
	when 值2 then 结果2或语句2(如果是语句，需要加分号)
	...
	else 结果n或语句n(如果是语句，需要加分号)
	end 【case】（如果是放在begin end中需要加上case，如果放在select后面不需要）
	
	情况二：类似于多重if
	case 
	when 条件1 then 结果1或语句1(如果是语句，需要加分号) 
	when 条件2 then 结果2或语句2(如果是语句，需要加分号)
	...
	else 结果n或语句n(如果是语句，需要加分号)
	end 【case】（如果是放在begin end中需要加上case，如果放在select后面不需要）


特点：
	可以用在任何位置

三、if elseif语句

语法：

	if 情况1 then 语句1;
	elseif 情况2 then 语句2;
	...
	else 语句n;
	end if;

特点：
	只能用在begin end中！！！！！！！！！！！！！！！


三者比较：
			应用场合
	if函数		简单双分支
	case结构	等值判断 的多分支
	if结构		区间判断 的多分支


###循环

语法：


	【标签：】WHILE 循环条件  DO
		循环体
	END WHILE 【标签】;

特点：

	只能放在BEGIN END里面
	
	如果要搭配leave跳转语句，需要使用标签，否则可以不用标签
	
	leave类似于java中的break语句，跳出所在循环！！！







































# SQL

```sql
1.什么是SQL？
	Structured Query Language：结构化查询语言
	其实就是定义了操作所有关系型数据库的规则。每一种数据库操作的方式存在不一样的地方，称为“方言”。
	
2.SQL通用语法
	1. SQL 语句可以单行或多行书写，以分号结尾。
	2. 可使用空格和缩进来增强语句的可读性。
	3. MySQL 数据库的 SQL 语句不区分大小写，关键字建议使用大写。
	4. 3 种注释
		* 单行注释: -- 注释内容 或 # 注释内容(mysql 特有) 
		* 多行注释: /* 注释 */
	
3. SQL分类
	1) DDL(Data Definition Language)数据定义语言
		用来定义数据库对象：数据库，表，列等。关键字：create, drop,alter 等
	2) DML(Data Manipulation Language)数据操作语言
		用来对数据库中表的数据进行增删改。关键字：insert, delete, update 等
	3) DQL(Data Query Language)数据查询语言
		用来查询数据库中表的记录(数据)。关键字：select, where 等
	4) DCL(Data Control Language)数据控制语言(了解)
		用来定义数据库的访问权限和安全级别，及创建用户。关键字：GRANT， REVOKE 等
```

![image-20201105093222413](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201105093222413.png)







## DDL:操作数据库、表

### 1.操作数据库：CRUD

```sql
1. C(Create):创建
   * 创建数据库：
     * create database 数据库名称;
   * 创建数据库，判断不存在，再创建：
     * create database if not exists 数据库名称;
   * 创建数据库，并指定字符集
     * create database 数据库名称 character set 字符集名;

   * 练习： 创建db4数据库，判断是否存在，并制定字符集为gbk
     * create database if not exists db4 character set gbk;
2. R(Retrieve)：查询
   * 查询所有数据库的名称:
     * show databases;
   * 查询某个数据库的字符集(默认utf8):查询某个数据库的创建语句
     * show create database 数据库名称;
3. U(Update):修改
   * 修改数据库的字符集
     * alter database 数据库名称 character set 字符集名称;
4. D(Delete):删除
   * 删除数据库
     * drop database 数据库名称;
   * 判断数据库存在，存在再删除
     * drop database if exists 数据库名称;
5. 使用数据库
   * 查询当前正在使用的数据库名称
     * select database();
   * 使用数据库
     * use 数据库名称;
```



### 2. 操作表：CRUD

```
1.C(Create):创建

1. 语法：
   create table 表名(
   		列名1 数据类型1,
   		列名2 数据类型2,
   		....
   		列名n 数据类型n
   	);

    * 注意：最后一列，不需要加逗号（,）

      * 数据库类型：

      1. int：整数类型
         * age int,
      2. double:小数类型
         * score double(5,2)
      3. date:日期，只包含年月日，yyyy-MM-dd
      4. datetime:日期，包含年月日时分秒	 yyyy-MM-dd HH:mm:ss
      5. timestamp:时间错类型	包含年月日时分秒	 yyyy-MM-dd HH:mm:ss	
         * 如果将来不给这个字段赋值，或赋值为null，则默认使用当前的系统时间，来自动赋值

      6. varchar：字符串
         * name varchar(20):姓名最大20个字符
         * zhangsan 8个字符  张三 2个字符


```

![image-20201105111723653](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201105111723653.png)


```sql
		* 创建表
			create table student(
				id int,
				name varchar(32),
				age int ,
				score double(4,1),
				birthday date,
				insert_time timestamp
			);
		* 复制表：
			* create table 表名 like 被复制的表名;	  	
	2. R(Retrieve)：查询
		* 查询某个数据库中所有的表名称
			* show tables;
		* 查询表结构
			* desc 表名;
	3. U(Update):修改
		1. 修改表名
			alter table 表名 rename to 新的表名;
		2. 修改表的字符集
			alter table 表名 character set 字符集名称;
		3. 添加一列
			alter table 表名 add 列名 数据类型;
		4. 修改列名称 类型
			alter table 表名 change 列名 新列别 新数据类型;
			alter table 表名 modify 列名 新数据类型;
		5. 删除列
			alter table 表名 drop 列名;
	4. D(Delete):删除
		* drop table 表名;
		* drop table  if exists 表名 ;
```

* 客户端图形化工具：SQLYog

## DML：增删改表中数据

```sql
1. 添加数据：
	* 语法：
		* insert into 表名(列名1,列名2,...列名n) values(值1,值2,...值n);
		（记住加''）
	* 注意：
		1. 列名和值要一一对应。
		2. 如果表名后，不定义列名，则默认给所有列添加值
			insert into 表名 values(值1,值2,...值n);
		3. 除了数字类型，其他类型需要使用引号(单双都可以)引起来
2. 删除数据：
	* 语法：
		* delete from 表名 [where 条件]
	* 注意：
		1. 如果不加条件，则删除表中所有记录。
		2. 如果要删除所有记录
			1. delete from 表名; -- 不推荐使用。有多少条记录就会执行多少次删除操作
			2. TRUNCATE TABLE 表名; -- 推荐使用，效率更高 先删除表，然后再创建一张一样的表。
3. 修改数据：
	* 语法：
		* update 表名 set 列名1 = 值1, 列名2 = 值2,... [where 条件];

	* 注意：
		1. 如果不加任何条件，则会将表中所有记录全部修改。
```



## DQL：查询表中的记录

### 1.语法

```sql
* select * from 表名;

1. 语法：
	select
		字段列表
	from
		表名列表
	where
		条件列表
	group by
		分组字段
	having
		分组之后的条件
	order by
		排序
	limit
		分页限定
```

### 2.基础查询

```
2.基础查询

1. 多个字段的查询
   select 字段名1，字段名2... from 表名；
   * 注意：
     * 如果查询所有字段，则可以使用*来替代字段列表。
2. 去除重复：
   * distinct
3. 计算列
   * 一般可以使用四则运算计算一些列的值。（一般只会进行数值型的计算）
   * ifnull(表达式1,表达式2)：null参与的运算，计算结果都为null
     * 表达式1：哪个字段需要判断是否为null
     * 如果该字段为null后的替换值。
4. 起别名：
   * as：as也可以省略


```

### 3.条件查询


```sql
3. 条件查询
	1. where子句后跟条件
	2. 运算符
		* > 、< 、<= 、>= 、= 、<>
		* BETWEEN...AND  
		* IN( 集合) 
		* LIKE：模糊查询
			* 占位符：
				* _:单个任意字符
				* %：多个任意字符
		* IS NULL  
		* and  或 &&
		* or  或 || 
		* not  或 !
		
			-- 查询年龄大于20岁

			SELECT * FROM student WHERE age > 20;
			
			SELECT * FROM student WHERE age >= 20;
			
			-- 查询年龄等于20岁
			SELECT * FROM student WHERE age = 20;
			
			-- 查询年龄不等于20岁
			SELECT * FROM student WHERE age != 20;
			SELECT * FROM student WHERE age <> 20;
			
			-- 查询年龄大于等于20 小于等于30
			
			SELECT * FROM student WHERE age >= 20 &&  age <=30;
			SELECT * FROM student WHERE age >= 20 AND  age <=30;
			SELECT * FROM student WHERE age BETWEEN 20 AND 30;
			
			-- 查询年龄22岁，18岁，25岁的信息
			SELECT * FROM student WHERE age = 22 OR age = 18 OR age = 25
			SELECT * FROM student WHERE age IN (22,18,25);
			
			-- 查询英语成绩为null
			SELECT * FROM student WHERE english = NULL; -- 不对的。null值不能使用 = （!=） 判断
			
			SELECT * FROM student WHERE english IS NULL;
			
			-- 查询英语成绩不为null
			SELECT * FROM student WHERE english  IS NOT NULL;
```

 

```sql
			-- 查询姓马的有哪些？ like
			SELECT * FROM student WHERE NAME LIKE '马%';
			-- 查询姓名第二个字是化的人
			
			SELECT * FROM student WHERE NAME LIKE "_化%";
			
			-- 查询姓名是3个字的人
			SELECT * FROM student WHERE NAME LIKE '___';
```


​				
​				-- 查询姓名中包含德的人
​				SELECT * FROM student WHERE NAME LIKE '%德%';





	1. DQL:查询语句
		1. 排序查询
		2. 聚合函数
		3. 分组查询
		4. 分页查询
	
	2. 约束
	3. 多表之间的关系
	4. 范式
	5. 数据库的备份和还原

### 4.排序查询

```sql
4. 排序查询
	* 语法：order by 子句
		* order by 排序字段1 排序方式1 ，  排序字段2 排序方式2...

	* 排序方式：
		* ASC：升序，默认的。
		* DESC：降序。

	* 注意：
		* 如果有多个排序条件，则当前边的条件值一样时，才会判断第二条件。
```



### 5.聚合函数

```sql
5.聚合函数：将一列数据作为一个整体，进行纵向的计算。

1. count：计算个数
   1. 一般选择非空的列：主键
   2. count(*)
2. max：计算最大值
3. min：计算最小值
4. sum：计算和
5. avg：计算平均值

	* 注意：聚合函数的计算，排除null值。
		解决方案：
			1. 选择不包含非空的列进行计算
			2. IFNULL函数
			
			
（ifnull）函数来处理特殊情况。
ifnull(a,b)函数解释：
如果value1不是空，结果返回a
如果value1是空，结果返回b
		
```

### 6. 分组查询:


```sql

6. 分组查询:
	1. 语法：group by 分组字段；
	2. 注意：
		1. 分组之后查询的字段：分组字段、聚合函数！！！！！！
		2. where 和 having 的区别？
			1. where 在分组之前进行限定，如果不满足条件，则不参与分组。having在分组之后进行限定，如果不满足结果，则不会被查询出来
			2. where 后不可以跟聚合函数，having可以进行聚合函数的判断。

		-- 按照性别分组。分别查询男、女同学的平均分

		SELECT sex , AVG(math) FROM student GROUP BY sex;
		
		-- 按照性别分组。分别查询男、女同学的平均分,人数
		
		SELECT sex , AVG(math),COUNT(id) FROM student GROUP BY sex;
		
		--  按照性别分组。分别查询男、女同学的平均分,人数 要求：分数低于70分的人，不参与分组
		SELECT sex , AVG(math),COUNT(id) FROM student WHERE math > 70 GROUP BY sex;
		
		--  按照性别分组。分别查询男、女同学的平均分,人数 要求：分数低于70分的人，不参与分组,分组之后。人数要大于2个人
		SELECT sex , AVG(math),COUNT(id) FROM student WHERE math > 70 GROUP BY sex HAVING COUNT(id) > 2;
		
		SELECT sex , AVG(math),COUNT(id) 人数 FROM student WHERE math > 70 GROUP BY sex HAVING 人数 > 2;
```

### 7.分页查询

```sql
7.分页查询
	1. 语法：limit 开始的索引,每页查询的条数;
	2. 公式：开始的索引 = （当前的页码 - 1） * 每页显示的条数
		-- 每页显示3条记录 

		SELECT * FROM student LIMIT 0,3; -- 第1页
		
		SELECT * FROM student LIMIT 3,3; -- 第2页
		
		SELECT * FROM student LIMIT 6,3; -- 第3页

	3. limit 是一个MySQL"方言"
```

### 尚硅谷进阶8：分页查询

应用场景：

```sql
实际的web项目中需要根据用户的需求提交对应的分页查询的sql语句
```

语法：

```sql
select 字段|表达式,...
from 表
【join type join 表2
on 连接条件】 
【where 条件】
【group by 分组字段】
【having 条件】
【order by 排序的字段】
limit 起始的条目索引，条目数;（offset,size）
#offset的起始索引从0开始
```

练习：

```sql
#案例1：查询前五条员工信息
SELECT * FROM employees LIMIT 0,5;

SELECT * FROM employees LIMIT 5;

#案例2：查询第11条----第25条
SELECT * FROM employees LIMIT 10,15;

#案例3：有奖金的员工信息，并且工资较高的前10名显示出来
SELECT *
FROM employees
WHERE commission_pct IS NOT NULL
ORDER BY salary DESC
LIMIT 0 , 10;


```

特点：

```sql
1.起始条目索引从0开始

2.limit子句放在查询语句的最后

3.公式：select * from  表 limit （page-1）*sizePerPage,sizePerPage
假如:
每页显示条目数sizePerPage
要显示的页数 page
```





## 约束

* 概念： 对表中的数据进行限定，保证数据的正确性、有效性和完整性。	
* 分类：
	1. 主键约束：primary key
	2. 非空约束：not null
	3. 唯一约束：unique
	4. 外键约束：foreign key



### 1.非空约束：

​	not null，某一列的值不能为null

```sql
1. 创建表时添加约束
   CREATE TABLE stu(
   	id INT,
   	NAME VARCHAR(20) NOT NULL -- name为非空
   );
2. 创建表完后，添加非空约束
   ALTER TABLE stu MODIFY NAME VARCHAR(20) NOT NULL;

3. 删除name的非空约束
   ALTER TABLE stu MODIFY NAME VARCHAR(20);
```



### 2.唯一约束：

```sql
唯一约束：unique，某一列的值不能重复

1. 注意：
   * 唯一约束可以有NULL值，但是只能有一条记录为null
2. 在创建表时，添加唯一约束
   CREATE TABLE stu(
   	id INT,
   	phone_number VARCHAR(20) UNIQUE -- 手机号
   );
3. 删除唯一约束
   ALTER TABLE stu DROP INDEX phone_number;
4. 在表创建完后，添加唯一约束
   ALTER TABLE stu MODIFY phone_number VARCHAR(20) UNIQUE;
```





### 3.主键约束：(非空且唯一)

```sql
* 主键约束：primary key。
	1. 注意：
		1. 含义：非空且唯一
		2. 一张表只能有一个字段为主键
		3. 主键就是表中记录的唯一标识

	2. 在创建表时，添加主键约束
		create table stu(
			id int primary key,-- 给id添加主键约束
			name varchar(20)
		);

	3. 删除主键
		-- 错误 alter table stu modify id int ;
		ALTER TABLE stu DROP PRIMARY KEY;

	4. 创建完表后，添加主键
		ALTER TABLE stu MODIFY id INT PRIMARY KEY;

	5. 自动增长：
		1.  概念：如果某一列是数值类型的，使用 auto_increment 可以来完成值得自动增长

		2. 在创建表时，添加主键约束，并且完成主键自增长
		create table stu(
			id int primary key auto_increment,-- 给id添加主键约束
			name varchar(20)
		);
		3. 删除自动增长
		ALTER TABLE stu MODIFY id INT;
		4. 添加自动增长
		ALTER TABLE stu MODIFY id INT AUTO_INCREMENT;
```



### 4.外键约束：


```sql
* 外键约束：foreign key,让表于表产生关系，从而保证数据的正确性。
	1. 在创建表时，可以添加外键
		* 语法：
			create table 表名(
				....
				外键列
				constraint 外键名称 foreign key (外键列名称) references 主表名称(主表列名称)
			);

	2. 删除外键
		ALTER TABLE 表名 DROP FOREIGN KEY 外键名称;

	3. 创建表之后，添加外键
		ALTER TABLE 表名 ADD CONSTRAINT 外键名称 FOREIGN KEY (外键字段名称) REFERENCES 主表名称(主表列名称);
		
	4. 级联操作
		1. 添加级联操作
			语法：ALTER TABLE 表名 ADD CONSTRAINT 外键名称 
			FOREIGN KEY (外键字段名称) REFERENCES 主表名称(主表列名称) ON UPDATE CASCADE ON DELETE CASCADE  ;
		2. 分类：
			1. 级联更新：ON UPDATE CASCADE 
			2. 级联删除：ON DELETE CASCADE 
```



## 数据库的设计

### 1. 多表之间的关系

```sql
1. 多表之间的关系
	1. 分类：
		1. 一对一(了解)：
			* 如：人和身份证
			* 分析：一个人只有一个身份证，一个身份证只能对应一个人
		2. 一对多(多对一)：
			* 如：部门和员工
			* 分析：一个部门有多个员工，一个员工只能对应一个部门
		3. 多对多：
			* 如：学生和课程
			* 分析：一个学生可以选择很多门课程，一个课程也可以被很多学生选择
	2. 实现关系：
		1. 一对多(多对一)：
			* 如：部门和员工
			* 实现方式：在多的一方建立外键，指向一的一方的主键。
		2. 多对多：
			* 如：学生和课程
			* 实现方式：多对多关系实现需要借助第三张中间表。中间表至少包含两个字段，这两个字段作为第三张表的外键，分别指向两张表的主键
		3. 一对一(了解)：
			* 如：人和身份证
			* 实现方式：一对一关系实现，可以在任意一方添加唯一外键指向另一方的主键。

	3. 案例
		-- 创建旅游线路分类表 tab_category
		-- cid 旅游线路分类主键，自动增长
		-- cname 旅游线路分类名称非空，唯一，字符串 100
		CREATE TABLE tab_category (
			cid INT PRIMARY KEY AUTO_INCREMENT,
			cname VARCHAR(100) NOT NULL UNIQUE
		);
		
		-- 创建旅游线路表 tab_route
		/*
		rid 旅游线路主键，自动增长
		rname 旅游线路名称非空，唯一，字符串 100
		price 价格
		rdate 上架时间，日期类型
		cid 外键，所属分类
		*/
		CREATE TABLE tab_route(
			rid INT PRIMARY KEY AUTO_INCREMENT,
			rname VARCHAR(100) NOT NULL UNIQUE,
			price DOUBLE,
			rdate DATE,
			cid INT,
			FOREIGN KEY (cid) REFERENCES tab_category(cid)
		);
		
		/*创建用户表 tab_user
		uid 用户主键，自增长
		username 用户名长度 100，唯一，非空
		password 密码长度 30，非空
		name 真实姓名长度 100
		birthday 生日
		sex 性别，定长字符串 1
		telephone 手机号，字符串 11
		email 邮箱，字符串长度 100
		*/
		CREATE TABLE tab_user (
			uid INT PRIMARY KEY AUTO_INCREMENT,
			username VARCHAR(100) UNIQUE NOT NULL,
			PASSWORD VARCHAR(30) NOT NULL,
			NAME VARCHAR(100),
			birthday DATE,
			sex CHAR(1) DEFAULT '男',
			telephone VARCHAR(11),
			email VARCHAR(100)
		);
		
		/*
		创建收藏表 tab_favorite
		rid 旅游线路 id，外键
		date 收藏时间
		uid 用户 id，外键
		rid 和 uid 不能重复，设置复合主键，同一个用户不能收藏同一个线路两次
		*/
		CREATE TABLE tab_favorite (
			rid INT, -- 线路id
			DATE DATETIME,
			uid INT, -- 用户id
			-- 创建复合主键
			PRIMARY KEY(rid,uid), -- 联合主键
			FOREIGN KEY (rid) REFERENCES tab_route(rid),
			FOREIGN KEY(uid) REFERENCES tab_user(uid)
		);
```





一对多：在多的一方建立外键，指向一的一方的主键。

![image-20201106164251835](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201106164251835.png)

 

多对多：多对多关系实现需要借助第三张中间表。中间表至少包含两个字段，这两个字段作为第三张

![image-20201106164922452](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201106164922452.png)





一对一：一对一关系实现，可以在任意一方添加唯一外键指向另一方的主键。

![ ](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201106165131323.png)





### 2.数据库设计的范式



概念：设计数据库时，需要遵循的一些规范。要遵循后边的范式要求，必须先遵循前边的所有范式要求

​		      设计关系数据库时，遵从不同的规范要求，设计出合理的关系型数据库，这些不同的规范要求被称为不同的范式，各种范式呈递次规范，越高的范式数据库冗余越小。
​	         目前关系数据库有六种范式：**第一范式（1NF）、第二范式（2NF）、第三范式（3NF）、巴斯-科德范式（BCNF）、第四范式(4NF）和第五范式（5NF，又称完美范式）**。







**第一范式**：每一列都是不可分割的原子数据项

![image-20201108104147078](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201108104147078.png)

```sql
	* 分类：
		1. 第一范式（1NF）：每一列都是不可分割的原子数据项
		2. 第二范式（2NF）：在1NF的基础上，非码属性必须完全依赖于码（在1NF基础上消除非主属性对主码的部分函数依赖）
			* 几个概念：
				1. 函数依赖：A-->B,如果通过A属性(属性组)的值，可以确定唯一B属性的值。则称B依赖于A
					例如：学号-->姓名。  （学号，课程名称） --> 分数
				2. 完全函数依赖：A-->B， 如果A是一个属性组，则B属性值得确定需要依赖于A属性组中所有的属性值。
					例如：（学号，课程名称） --> 分数
				3. 部分函数依赖：A-->B， 如果A是一个属性组，则B属性值得确定只需要依赖于A属性组中某一些值即可。
					例如：（学号，课程名称） -- > 姓名
				4. 传递函数依赖：A-->B, B -- >C . 如果通过A属性(属性组)的值，可以确定唯一B属性的值，在通过B属性（属性组）的值可以确定唯一C属性的值，则称 C 传递函数依赖于A
					例如：学号-->系名，系名-->系主任
				5. 码：如果在一张表中，一个属性或属性组，被其他所有属性所完全依赖，则称这个属性(属性组)为该表的码
					例如：该表中码为：（学号，课程名称）
					* 主属性：码属性组中的所有属性
					* 非主属性：除过码属性组的属性
					
		3. 第三范式（3NF）：在2NF基础上，任何非主属性不依赖于其它非主属性（在2NF基础上消除传递依赖）
```

**第二范式**：在1NF基础上消除非主属性对主码的部分函数依赖

![image-20201108104702561](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201108104702561.png)



**第三范式**：在2NF基础上消除传递依赖

![image-20201108104937791](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201108104937791.png)





**注意：即消除原子项，部分依赖，传递依赖**





## 数据库的备份和还原 

	1. 命令行：
		* 语法：
			* 备份： mysqldump -u用户名 -p密码 数据库名称 > 保存的路径
			* 还原：
				1. 登录数据库
				2. 创建数据库
				3. 使用数据库
				4. 执行文件。source 文件路径
	2. 图形化工具：







# 今日内容

1. 多表查询

2. 事务

3. DCL

# 多表查询：

表格：

```sql
* 查询语法：
	select
		列名列表
	from
		表名列表
	where....
* 准备sql
	# 创建部门表
	CREATE TABLE dept(
		id INT PRIMARY KEY AUTO_INCREMENT,
		NAME VARCHAR(20)
	);
	INSERT INTO dept (NAME) VALUES ('开发部'),('市场部'),('财务部');
	# 创建员工表
	CREATE TABLE emp (
		id INT PRIMARY KEY AUTO_INCREMENT,
		NAME VARCHAR(10),
		gender CHAR(1), -- 性别
		salary DOUBLE, -- 工资
		join_date DATE, -- 入职日期
		dept_id INT,
		FOREIGN KEY (dept_id) REFERENCES dept(id) -- 外键，关联部门表(部门表的主键)
	);
	INSERT INTO emp(NAME,gender,salary,join_date,dept_id) VALUES('孙悟空','男',7200,'2013-02-24',1);
	INSERT INTO emp(NAME,gender,salary,join_date,dept_id) VALUES('猪八戒','男',3600,'2010-12-02',2);
	INSERT INTO emp(NAME,gender,salary,join_date,dept_id) VALUES('唐僧','男',9000,'2008-08-08',2);
	INSERT INTO emp(NAME,gender,salary,join_date,dept_id) VALUES('白骨精','女',5000,'2015-10-07',3);
	INSERT INTO emp(NAME,gender,salary,join_date,dept_id) VALUES('蜘蛛精','女',4500,'2011-03-14',1);
```

## 笛卡尔积：

* 笛卡尔积：
	* 有两个集合A,B .取这两个集合的所有组成情况。
	* 要完成多表查询，需要消除无用的数据



## 99语法

```sql
含义：1999年推出的sql语法
支持：
等值连接、非等值连接 （内连接）
外连接
交叉连接

语法：

select 字段，...
from 表1
【（inner）|left outer|right outer|cross】join 表2 on  连接条件
【inner|left outer|right outer|cross】join 表3 on  连接条件
【where 筛选条件】
【group by 分组字段】
【having 分组后的筛选条件】
【order by 排序的字段或表达式】

好处：语句上，连接条件和筛选条件实现了分离，简洁明了！
```





##  多表查询的分类：

### 1.内连接查询：

查交集部分

![image-20201108112438150](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201108112438150.png)

#### 1. 隐式内连接：

```sql
1. 内连接查询：
		1. 隐式内连接：使用where条件消除无用数据
			* 例子：
			-- 查询所有员工信息和对应的部门信息

			SELECT * FROM emp,dept WHERE emp.`dept_id` = dept.`id`;
			
			-- 查询员工表的名称，性别。部门表的名称
			SELECT emp.name,emp.gender,dept.name FROM emp,dept WHERE emp.`dept_id` = dept.`id`;
			
			SELECT 
				t1.name, -- 员工表的姓名
				t1.gender,-- 员工表的性别
				t2.name -- 部门表的名称
			FROM
				emp t1,
				dept t2
			WHERE 
				t1.`dept_id` = t2.`id`;
```

#### 	2. 显式内连接：

```sql
		2. 显式内连接：
			* 语法： select 字段列表 from 表名1 [inner] join 表名2 on 条件
			* 例如：
				* SELECT * FROM emp INNER JOIN dept ON emp.`dept_id` = dept.`id`;	
				* SELECT * FROM emp JOIN dept ON emp.`dept_id` = dept.`id`;	
```

		3. 内连接查询：
			1. 从哪些表中查询数据
			2. 条件是什么
			3. 查询哪些字段




### 2. 外链接查询：

#### 1. 左外连接：

![image-20201108112452828](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201108112452828.png)

```sql
2. 外链接查询：
		1. 左外连接：
			* 语法：select 字段列表 from 表1 left [outer] join 表2 on 条件；
			* 查询的是左表所有数据以及其交集部分。
			* 例子：
				-- 查询所有员工信息，如果员工有部门，则查询部门名称，没有部门，则不显示部门名称
				SELECT 	t1.*,t2.`name` FROM emp t1 LEFT JOIN dept t2 ON t1.`dept_id` = t2.`id`;
```

#### 2. 右外连接：

```sql
2. 右外连接：
			* 语法：select 字段列表 from 表1 right [outer] join 表2 on 条件；
			* 查询的是右表所有数据以及其交集部分。
			* 例子：
				SELECT 	* FROM dept t2 RIGHT JOIN emp t1 ON t1.`dept_id` = t2.`id`;
```

#### 3.全外连接

全外连接=内连接的结果+表1中有但表2没有的+表2中有但表1没有的







# 尚硅谷多表连接

### 进阶6：多表连接查询

	笛卡尔乘积：如果连接条件省略或无效则会出现
	解决办法：添加上连接条件

有笛卡尔乘积现象，解决办法：**添加上连接条件**

![image-20201012211329906](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201012211329906.png)



**含义：**又称多表查询，当查询的字段来自于多个表时，就会用到连接查询

笛卡尔乘积现象：表1 有m行，表2有n行，结果=m*n行

发生原因：没有有效的连接条件

如何避免：添加有效的连接条件



**分类：**

- 按年代分类：sql92标准（仅仅支持内连接）

  ​		   			**sql99标准【推荐】**（支持内连接+外连接（左外+右外）+交叉连接）

- 按功能分类：内连接（等值连接，非等值连接，自连接），

​						      外连接（左外连接，右外连接，全外连接），

​					      	交叉连接







#### 1、传统模式下的连接 ：等值连接——非等值连接

##### 1.等值连接

![image-20201020210914174](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201020210914174.png)

2.非等值连接

![image-20201020211927851](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201020211927851.png)






```SQL
1.等值连接的结果 = 多个表的交集
2.n表连接，至少需要n-1个连接条件
3.多个表不分主次，没有顺序要求
4.一般为表起别名，提高阅读性和性能


SELECT NAEM,boyName
FROM boys,beauty
WHERE beauty.boyfriend_id = boys.id %等值连接


```

#### 2、sql99语法：通过join关键字实现连接

分类：

**内连接**：inner

外连接

- **左外**：left [outer]
- **右外**：right [outer]
- 全外：full [outer]

交叉连接:cross

```sql
含义：1999年推出的sql语法
支持：
等值连接、非等值连接 （内连接）
外连接
交叉连接

语法：

select 字段，...
from 表1
【inner|left outer|right outer|cross】join 表2 on  连接条件
【inner|left outer|right outer|cross】join 表3 on  连接条件
【where 筛选条件】
【group by 分组字段】
【having 分组后的筛选条件】
【order by 排序的字段或表达式】

好处：语句上，连接条件和筛选条件实现了分离，简洁明了！
```

#### 3、外连接

应用场景：用于查询一个表中有，另一个表没有的记录

特点：

1、外连接的查询结果为主表中的所有记录

- 如果从表中有和它匹配的，则显示匹配的值
- 如果从表中没有和它匹配的，则显示null
- 外连接查询结果=内连接结果+主表中有而从表没有的记录

2、左外连接：left join左边的是主表

​      右外连接：right join右边的是主表

3、左外和右外交换两个表的顺序，可以实现同样的效果

4、全外连接=内连接的结果+表1中有但表2没有的+表2中有但表1没有的



#### 4、交叉连接

其实就是笛卡尔乘积

```sql
SELECT b.* , bo.*
FROM beauty b
CROSS JOIN boys bo；
```



#### 5、自连接（内连接一种）

案例：查询员工名和直接上级的名称

sql99

```sql
SELECT e.last_name,m.last_name
FROM employees e
JOIN employees m ON e.`manager_id`=m.`employee_id`;
```

sql92


```sql
SELECT e.last_name,m.last_name
FROM employees e,employees m 
WHERE e.`manager_id`=m.`employee_id`;
```





#### 6、总结

![image-20201022202215179](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201022202215179.png)

![image-20201022202245704](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201022202245704.png)

![image-20201022202326465](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201022202326465.png)











# 子查询：

* 概念：查询中嵌套查询，称嵌套查询为子查询。

```sql
		* 概念：查询中嵌套查询，称嵌套查询为子查询。
			-- 查询工资最高的员工信息
			-- 1 查询最高的工资是多少 9000
			SELECT MAX(salary) FROM emp;
			
			-- 2 查询员工信息，并且工资等于9000的
			SELECT * FROM emp WHERE emp.`salary` = 9000;
			
			-- 一条sql就完成这个操作。子查询
			SELECT * FROM emp WHERE emp.`salary` = (SELECT MAX(salary) FROM emp);
```



子查询不同情况：

## 1. 子查询的结果是单行单列的：

```sql
1. 子查询的结果是单行单列的：
				* 子查询可以作为条件，使用运算符去判断。 运算符： > >= < <= =
				* 
				-- 查询员工工资小于平均工资的人
				SELECT * FROM emp WHERE emp.salary < (SELECT AVG(salary) FROM emp);
```

## 2. 子查询的结果是多行单列的：

```sql
2. 子查询的结果是多行单列的：
				* 子查询可以作为条件，使用运算符in来判断
				-- 查询'财务部'和'市场部'所有的员工信息
				SELECT id FROM dept WHERE NAME = '财务部' OR NAME = '市场部';
				SELECT * FROM emp WHERE dept_id = 3 OR dept_id = 2;
				-- 子查询
				SELECT * FROM emp WHERE dept_id IN (SELECT id FROM dept WHERE NAME = '财务部' OR NAME = '市场部');
```

## 3. 子查询的结果是多行多列的：

子查询可以作为一张虚拟表参与查询

```sql
3. 子查询的结果是多行多列的：
				* 子查询可以作为一张虚拟表参与查询
				-- 查询员工入职日期是2011-11-11日之后的员工信息和部门信息
				-- 子查询
				SELECT * FROM dept t1 ,(SELECT * FROM emp WHERE emp.`join_date` > '2011-11-11') t2
				WHERE t1.id = t2.dept_id;
				
				-- 普通内连接
				SELECT * FROM emp t1,dept t2 WHERE t1.`dept_id` = t2.`id` AND t1.`join_date` >  '2011-11-11'
```









```sql
	* 多表查询练习

			-- 部门表
			CREATE TABLE dept (
			  id INT PRIMARY KEY PRIMARY KEY, -- 部门id
			  dname VARCHAR(50), -- 部门名称
			  loc VARCHAR(50) -- 部门所在地
			);
			
			-- 添加4个部门
			INSERT INTO dept(id,dname,loc) VALUES 
			(10,'教研部','北京'),
			(20,'学工部','上海'),
			(30,'销售部','广州'),
			(40,'财务部','深圳');
```


​				
​				

				-- 职务表，职务名称，职务描述
				CREATE TABLE job (
				  id INT PRIMARY KEY,
				  jname VARCHAR(20),
				  description VARCHAR(50)
				);
				
				-- 添加4个职务
				INSERT INTO job (id, jname, description) VALUES
				(1, '董事长', '管理整个公司，接单'),
				(2, '经理', '管理部门员工'),
				(3, '销售员', '向客人推销产品'),
				(4, '文员', '使用办公软件');


​				
​				

				-- 员工表
				CREATE TABLE emp (
				  id INT PRIMARY KEY, -- 员工id
				  ename VARCHAR(50), -- 员工姓名
				  job_id INT, -- 职务id
				  mgr INT , -- 上级领导
				  joindate DATE, -- 入职日期
				  salary DECIMAL(7,2), -- 工资
				  bonus DECIMAL(7,2), -- 奖金
				  dept_id INT, -- 所在部门编号
				  CONSTRAINT emp_jobid_ref_job_id_fk FOREIGN KEY (job_id) REFERENCES job (id),
				  CONSTRAINT emp_deptid_ref_dept_id_fk FOREIGN KEY (dept_id) REFERENCES dept (id)
				);
				
				-- 添加员工
				INSERT INTO emp(id,ename,job_id,mgr,joindate,salary,bonus,dept_id) VALUES 
				(1001,'孙悟空',4,1004,'2000-12-17','8000.00',NULL,20),
				(1002,'卢俊义',3,1006,'2001-02-20','16000.00','3000.00',30),
				(1003,'林冲',3,1006,'2001-02-22','12500.00','5000.00',30),
				(1004,'唐僧',2,1009,'2001-04-02','29750.00',NULL,20),
				(1005,'李逵',4,1006,'2001-09-28','12500.00','14000.00',30),
				(1006,'宋江',2,1009,'2001-05-01','28500.00',NULL,30),
				(1007,'刘备',2,1009,'2001-09-01','24500.00',NULL,10),
				(1008,'猪八戒',4,1004,'2007-04-19','30000.00',NULL,20),
				(1009,'罗贯中',1,NULL,'2001-11-17','50000.00',NULL,10),
				(1010,'吴用',3,1006,'2001-09-08','15000.00','0.00',30),
				(1011,'沙僧',4,1004,'2007-05-23','11000.00',NULL,20),
				(1012,'李逵',4,1006,'2001-12-03','9500.00',NULL,30),
				(1013,'小白龙',4,1004,'2001-12-03','30000.00',NULL,20),
				(1014,'关羽',4,1007,'2002-01-23','13000.00',NULL,10);


​				
​				

				-- 工资等级表
				CREATE TABLE salarygrade (
				  grade INT PRIMARY KEY,   -- 级别
				  losalary INT,  -- 最低工资
				  hisalary INT -- 最高工资
				);
				
				-- 添加5个工资等级
				INSERT INTO salarygrade(grade,losalary,hisalary) VALUES 
				(1,7000,12000),
				(2,12010,14000),
				(3,14010,20000),
				(4,20010,30000),
				(5,30010,99990);
				
				-- 需求：
				
				-- 1.查询所有员工信息。查询员工编号，员工姓名，工资，职务名称，职务描述
				/*
					分析：
						1.员工编号，员工姓名，工资，需要查询emp表  职务名称，职务描述 需要查询job表
						2.查询条件 emp.job_id = job.id
				
				*/
				SELECT 
					t1.`id`, -- 员工编号
					t1.`ename`, -- 员工姓名
					t1.`salary`,-- 工资
					t2.`jname`, -- 职务名称
					t2.`description` -- 职务描述
				FROM 
					emp t1, job t2
				WHERE 
					t1.`job_id` = t2.`id`;


​				
​				

				-- 2.查询员工编号，员工姓名，工资，职务名称，职务描述，部门名称，部门位置
				/*
					分析：
						1. 员工编号，员工姓名，工资 emp  职务名称，职务描述 job  部门名称，部门位置 dept
						2. 条件： emp.job_id = job.id and emp.dept_id = dept.id
				*/
				
				SELECT 
					t1.`id`, -- 员工编号
					t1.`ename`, -- 员工姓名
					t1.`salary`,-- 工资
					t2.`jname`, -- 职务名称
					t2.`description`, -- 职务描述
					t3.`dname`, -- 部门名称
					t3.`loc` -- 部门位置
				FROM 
					emp t1, job t2,dept t3
				WHERE 
					t1.`job_id` = t2.`id` AND t1.`dept_id` = t3.`id`;
				   
				-- 3.查询员工姓名，工资，工资等级
				/*
					分析：
						1.员工姓名，工资 emp  工资等级 salarygrade
						2.条件 emp.salary >= salarygrade.losalary and emp.salary <= salarygrade.hisalary
							emp.salary BETWEEN salarygrade.losalary and salarygrade.hisalary
				*/
				SELECT 
					t1.ename ,
					t1.`salary`,
					t2.*
				FROM emp t1, salarygrade t2
				WHERE t1.`salary` BETWEEN t2.`losalary` AND t2.`hisalary`;


​				
​				

```mysql
			-- 4.查询员工姓名，工资，职务名称，职务描述，部门名称，部门位置，工资等级
			/*
				分析：
1. 员工姓名，工资 emp ， 职务名称，职务描述 job 部门名称，部门位置，dept  工资等级 salarygrade
2. 条件： emp.job_id = job.id and emp.dept_id = dept.id and emp.salary BETWEEN salarygrade.losalary and salarygrade.hisalary
						
			*/
			SELECT 
				t1.`ename`,
				t1.`salary`,
				t2.`jname`,
				t2.`description`,
				t3.`dname`,
				t3.`loc`,
				t4.`grade`
			FROM 
				emp t1,job t2,dept t3,salarygrade t4
			WHERE 
				t1.`job_id` = t2.`id` 
				AND t1.`dept_id` = t3.`id`
				AND t1.`salary` BETWEEN t4.`losalary` AND t4.`hisalary`;
```


​				
​				

				-- 5.查询出部门编号、部门名称、部门位置、部门人数
				
				/*
					分析：
						1.部门编号、部门名称、部门位置 dept 表。 部门人数 emp表
						2.使用分组查询。按照emp.dept_id完成分组，查询count(id)
						3.使用子查询将第2步的查询结果和dept表进行关联查询
						
				*/
				SELECT 
					t1.`id`,t1.`dname`,t1.`loc` , t2.total
				FROM 
					dept t1,
					(SELECT
						dept_id,COUNT(id) total
					FROM 
						emp
					GROUP BY dept_id) t2
				WHERE t1.`id` = t2.dept_id;


​				

				-- 6.查询所有员工的姓名及其直接上级的姓名,没有领导的员工也需要查询
				
				/*
					分析：
						1.姓名 emp， 直接上级的姓名 emp
							* emp表的id 和 mgr 是自关联
						2.条件 emp.id = emp.mgr
						3.查询左表的所有数据，和 交集数据
							* 使用左外连接查询
					
				*/
				/*
				select
					t1.ename,
					t1.mgr,
					t2.`id`,
					t2.ename
				from emp t1, emp t2
				where t1.mgr = t2.`id`;
				
				*/
				
				SELECT 
					t1.ename,
					t1.mgr,
					t2.`id`,
					t2.`ename`
				FROM emp t1
				LEFT JOIN emp t2
				ON t1.`mgr` = t2.`id`;

# 尚硅谷子查询

### 进阶7：子查询

含义：

```sql
一条查询语句中又嵌套了另一条完整的select语句，其中被嵌套的select语句，称为子查询或内查询
在外面的查询语句，称为主查询或外查询
```

特点：

```sql
1、子查询都放在小括号内
2、子查询可以放在from后面、select后面、where后面、having后面，但一般放在条件的右侧
3、子查询优先于主查询执行，主查询使用了子查询的执行结果
4、子查询根据查询结果的行数不同分为以下两类：
① 单行子查询
	结果集只有一行
	一般搭配单行操作符使用：> < = <> >= <= 
	非法使用子查询的情况：
	a、子查询的结果为一组值
	b、子查询的结果为空
	
② 多行子查询
	结果集有多行
	一般搭配多行操作符使用：any、all、in、not in
	in： 属于子查询结果中的任意一个就行
	any和all往往可以用其他查询代替
```



![](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201022210446415.png)









1.放在where或having后面

1）标量子查询（单行子查询）

![image-20201026202610398](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201026202610398.png)



```sql
#案例1：谁的工资比Abel高
#①查询Abel的工资
SELECT salary
FROM employees
WHERE last_name = 'Abel';
#②查询员工的信息，满足 salary>①结果
SELECT *
from employees
where salary > (
    
	SELECT salary
	FROM employees
	WHERE last_name = 'Abel';
    
)


#案例4：查询最低工资大于50号部门最低工资的部门id和其最低工资
SELECT MIN(salary) , department_id
FROM employees
GROUP BY department_id
HAVING MIN(salary) > (
	SELECT MIN(salary)
	FROM employees
	WHERE department_id = 50
)
```



#### 2）列子查询（多行子查询）

![image-20201026204041090](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201026204041090.png)

```sql
#2.列子查询（多行子查询）
#案例1：返回locatian_id是1400或1700的部门中的所有员工姓名

#①查询location_id是1400或1700的部门编号
SELECT DISTINCT department_id
FROM departments
WHERE location_id IN (1400,1700);

#查询员工姓名，要求部门号是①列表中的某一个
SELECT last_name
FROM employees
WHERE department_id IN(
	SELECT DISTINCT department_id
	FROM departments
	WHERE location_id IN (1400,1700)	
);



#案例2：返回其他工种中比job_id为‘IT_DPOG’部门任一工资低的员工的员工号、姓名、job_id以及salary

#①查询job_id为‘IT_PROG’部门任一工资

SELECT DISTINCT salary 
FROM employees
WHERE job_id = 'IT_PROG';

#②查询员工号、姓名、job_id以及salary,salary<(①)的任意结果
SELECT employee_id ,last_name,job_id,salary
FROM employees
WHERE salary <ANY(
	SELECT DISTINCT salary 
	FROM employees
	WHERE job_id = 'IT_PROG'
) AND job_id<>'IT_PROG';
#any很多时候可以替换
SELECT employee_id ,last_name,job_id,salary
FROM employees
WHERE salary <(
	SELECT DISTINCT MAX(salary) 
	FROM employees
	WHERE job_id = 'IT_PROG'
) AND job_id<>'IT_PROG';


```



#### 3）行字查询（多列子查询）

```sql
#行子查询（结果集一行多列或多行多列）
#比较啰嗦，用的较少，了解即可

#案例：查询员工编号最小并且工资最高的员工信息

#①查询最小的员工编号
SELECT	MIN(employee_id)
FROM employees;

#②查询最高的工资
SELECT MAX(salary)
FROM employees;

#③查询员工信息
SELECT *
FROM employees
WHERE employee_id = (
	SELECT	MIN(employee_id)
	FROM employees
) AND salary = (
	SELECT MAX(salary)
	FROM employees
);

#合体！
SELECT *
FROM employees
WHERE (employee_id,salary) = (
	SELECT	MIN(employee_id),MAX(salary)
	FROM employees
) 
```



#### 2.放在select后面的子查询：

select后面只能标量子查询（**一行一列**）

```sql
#案例：查询每个部门的员工个数
SELECT d.*,(
	SELECT	COUNT(*)
	FROM employees e
	WHERE e.department_id = d.`department_id`
)
FROM departments d; 



#案例2：查询员工号=102的部门名
#连接查询
SELECT (
	SELECT department_name
	FROM departments d
	INNER JOIN employees e
	ON d.department_id = e.department_id
	WHERE e.employee_id=102
)；
```



#### 3.放在from后面



```sql
#案例：查询每个部门的平均工资的工资等级

#查询每个部门的平均工资
SELECT AVG(salary)
FROM employees
GROUP BY department_id;

#②连接①的结果集和job_grades表，筛选条件平均工资  between_lowest_sal and highest_sal
SELECT ag_dep.* , g.grade_level
FROM (
	SELECT AVG(salary)
	FROM employees
	GROUP BY department_id;
) ag_dep
INNER JOIN job_grades g
ON ag_dep.ag BETWEEN lowest_sal AND highest_sal;

```



#### 4.放在exists后面的子查询（相关子查询）

```sql
/*
	语法：
	exists（完整的查询语句）
	结果：
	1或者0
*/

SELECT EXISTS(
	SELECT
	employee_id
	FROM 
	employees
);#返回Boolean类型，只关心有没有

SELECT department_name
FROM departments d
WHERE EXISTS(
	SELECT *
	FROM employees e
	WHERE e.`department_id`=d.`department_id`
);
```















**特点**：

- 子查询放在小括号内
- 子查询一般放在条件的右侧
- 标量子查询，一般搭配着单行操作符使用（>  <  >=  <=  = <> ）
- 列子查询，一般搭配着多行操作符使用（IN  ANY/SOME ALL）
- 子查询的执行优先于主查询执行，主查询的条件用到了子查询的结果







# 事务

## 1. 事务的基本介绍

如果一个包含多个步骤的业务操作，被事务管理，那么这些操作要么同时成功，要么同时失败。

![image-20201108144935537](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201108144935537.png)

操作：
1. 开启事务： start transaction;、
2. 回滚：rollback;
3. 提交：commit;

```sql
1. 事务的基本介绍
	1. 概念：
		*  如果一个包含多个步骤的业务操作，被事务管理，那么这些操作要么同时成功，要么同时失败。
		
	2. 操作：
		1. 开启事务： start transaction;
		2. 回滚：rollback;
		3. 提交：commit;
	3. 例子：
		CREATE TABLE account (
			id INT PRIMARY KEY AUTO_INCREMENT,
			NAME VARCHAR(10),
			balance DOUBLE
		);
		-- 添加数据
		INSERT INTO account (NAME, balance) VALUES ('zhangsan', 1000), ('lisi', 1000);	
```

```sql
		SELECT * FROM account;
		UPDATE account SET balance = 1000;
		-- 张三给李四转账 500 元
				
		-- 0. 开启事务
		START TRANSACTION;
		-- 1. 张三账户 -500
		
		UPDATE account SET balance = balance - 500 WHERE NAME = 'zhangsan';
		-- 2. 李四账户 +500
		-- 出错了...
		UPDATE account SET balance = balance + 500 WHERE NAME = 'lisi';
		
		-- 发现执行没有问题，提交事务
		COMMIT;
		
		-- 发现出问题了，回滚事务
		ROLLBACK;

 	4. MySQL数据库中事务默认自动提交
     	
      * 事务提交的两种方式：
        * 自动提交：
          * mysql就是自动提交的
            * 一条DML(增删改)语句会自动提交一次事务。
          * 手动提交：
            * Oracle 数据库默认是手动提交事务
            * 需要先开启事务，再提交
        * 修改事务的默认提交方式：
          * 查看事务的默认提交方式：SELECT @@autocommit; -- 1 代表自动提交  0 代表手动提交
          * 修改默认提交方式： set @@autocommit = 0;
```





## 2.事务的四大特征：

1. 原子性：是不可分割的最小操作单位，要么同时成功，要么同时失败。
2. 持久性：当事务提交或回滚后，数据库会持久化的保存数据。
3. 隔离性：多个事务之间。相互独立。
4. 一致性：事务操作前后，数据总量不变





## 3. （了解）


```sql
3. 事务的隔离级别（了解）
	* 概念：多个事务之间隔离的，相互独立的。但是如果多个事务操作同一批数据，则会引发一些问题，设置不同的隔离级别就可以解决这些问题。
	* 存在问题：
		1. 脏读：一个事务，读取到另一个事务中没有提交的数据
		2. 不可重复读(虚读)：在同一个事务中，两次读取到的数据不一样。
		3. 幻读：一个事务操作(DML)数据表中所有记录，另一个事务添加了一条数据，则第一个事务查询不到自己的修改。
	* 隔离级别：
		1. read uncommitted：读未提交
			* 产生的问题：脏读、不可重复读、幻读
		2. read committed：读已提交 （Oracle）
			* 产生的问题：不可重复读、幻读
		3. repeatable read：可重复读 （MySQL默认）
			* 产生的问题：幻读
		4. serializable：串行化
			* 可以解决所有的问题

		* 注意：隔离级别从小到大安全性越来越高，但是效率越来越低
		* 数据库查询隔离级别：
			* select @@tx_isolation;
		* 数据库设置隔离级别：
			* set global transaction isolation level  级别字符串;

	* 演示：
		set global transaction isolation level read uncommitted;
		start transaction;
		-- 转账操作
		update account set balance = balance - 500 where id = 1;
		update account set balance = balance + 500 where id = 2;
```



# DCL

SQL分类：

1.DDL：操作数据库和表

2.DML：增删改表中数据

3.DQL：查询表中数据

4.DCL：管理用户，授权





DBA：数据库管理员

DCL：管理用户，授权



## 1. 管理用户

### 1. 添加用户：

```sql
语法：CREATE USER '用户名'@'主机名' IDENTIFIED BY '密码';
```



### 2.删除用户：

```sql
语法：DROP USER '用户名'@'主机名';
```



### 3.修改用户密码：

```sql
		UPDATE USER SET PASSWORD = PASSWORD('新密码') WHERE USER = '用户名';
		
		
		 UPDATE USER SET PASSWORD = PASSWORD('abc') WHERE USER = 'lisi';
			
		SET PASSWORD FOR '用户名'@'主机名' = PASSWORD('新密码');
		SET PASSWORD FOR 'root'@'localhost' = PASSWORD('123');

		* mysql中忘记了root用户的密码？
			1. cmd -- > net stop mysql 停止mysql服务
				* 需要管理员运行该cmd

			2. 使用无验证方式启动mysql服务： mysqld --skip-grant-tables
			3. 打开新的cmd窗口,直接输入mysql命令，敲回车。就可以登录成功
			4. use mysql;
			5. update user set password = password('你的新密码') where user = 'root';
			6. 关闭两个窗口
			7. 打开任务管理器，手动结束mysqld.exe 的进程
			8. 启动mysql服务
			9. 使用新密码登录。
```





###  4.查询用户：

```sql
4. 查询用户：
		-- 1. 切换到mysql数据库
		USE myql;
		-- 2. 查询user表
		SELECT * FROM USER;
			
		* 通配符： % 表示可以在任意主机使用用户登录数据库
```



## 2.权限管理：

### 1.查询权限：

```sql
-- 查询权限
		SHOW GRANTS FOR '用户名'@'主机名';
		SHOW GRANTS FOR 'lisi'@'%';
```



### 2.授予权限：

```sql
		-- 授予权限
		grant 权限列表 on 数据库名.表名 to '用户名'@'主机名';
		-- 给张三用户授予所有权限，在任意数据库任意表上
		GRANT SELECT ON db3.account TO 'lisi'@'%';
		GRANT ALL ON *.* TO 'zhangsan'@'localhost';
```



### 3.撤销权限:

```sql
3. 撤销权限：
		-- 撤销权限：
		revoke 权限列表 on 数据库名.表名 from '用户名'@'主机名';
		REVOKE UPDATE ON db3.`account` FROM 'lisi'@'%';
```




# 今日内容

	1. JDBC基本概念
	2. 快速入门
	3. 对JDBC中各个接口和类详解



# JDBC：

## 1.概念：

​					Java DataBase Connectivity  Java 数据库连接， Java语言操作数据库

**JDBC本质**：其实是官方（sun公司）定义的一套操作所有关系型数据库的规则，即接口。各个数据库厂商去实现这套接口，提供数据库驱动jar包。我们可以使用这套接口（JDBC）编程，真正执行的代码是驱动jar包中的实现类。

例如：

```java
Person接口  Worker类   Person p = new Worker();

p.eat();
```



![image-20201108165428370](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201108165428370.png)







## 2.快速入门：

* 步骤：

   1.导入驱动jar包 mysql-connector-java-5.1.37-bin.jar
            1.复制mysql-connector-java-5.1.37-bin.jar到项目的libs目录下
   	     2.右键-->Add As Library

   2.注册驱动

   3.获取数据库连接对象 Connection

   4.定义sql

   5.获取执行sql语句的对象 Statement

   6.执行sql，接受返回结果

   7.处理结果

   8.释放资源

```sql
* 代码实现：
	  	//1. 导入驱动jar包
        //2.注册驱动
        Class.forName("com.mysql.jdbc.Driver");
        //3.获取数据库连接对象
        Connection conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/db3", "root", "password");
        //4.定义sql语句
        String sql = "update account set balance = 500 where id = 1";
        //5.获取执行sql的对象 Statement
        Statement stmt = conn.createStatement();
        //6.执行sql
        int count = stmt.executeUpdate(sql);
        //7.处理结果
        System.out.println(count);
        //8.释放资源
        stmt.close();
        conn.close();
```



## 3.详解各个对象：

#### 1. DriverManager：驱动管理对象

##### 1. 注册驱动：告诉程序该使用哪一个数据库驱动jar

```mysql
1. DriverManager：驱动管理对象
		* 功能：
		1. 注册驱动：告诉程序该使用哪一个数据库驱动jar
			static void registerDriver(Driver driver) :注册与给定的驱动程序 DriverManager 。 
			写代码使用：  Class.forName("com.mysql.jdbc.Driver");
			通过查看源码发现：在com.mysql.jdbc.Driver类中存在静态代码块
			 static {
				     try {
				         java.sql.DriverManager.registerDriver(new Driver());
				      } catch (SQLException E) {
				         throw new RuntimeException("Can't register driver!");
				      }
					}
	
```

注意：mysql5之后的驱动jar包可以省略注册驱动的步骤。

##### 2. 获取数据库连接：

```sql
2. 获取数据库连接：
	* 方法：static Connection getConnection(String url, String user, String password) 
	* 参数：
		* url：指定连接的路径
			* 语法：jdbc:mysql://ip地址(域名):端口号/数据库名称
			* 例子：jdbc:mysql://localhost:3306/db3
			* 细节：如果连接的是本机mysql服务器，并且mysql服务默认端口是3306，则url可以简写为：jdbc:mysql:///数据库名称
			* user：用户名
			* password：密码 
```



#### 2.Connection：数据库连接对象

```sql
2. Connection：数据库连接对象
		1. 功能：
			1. 获取执行sql 的对象
				* Statement createStatement()
				* PreparedStatement prepareStatement(String sql)  
			2. 管理事务：
				* 开启事务：setAutoCommit(boolean autoCommit) ：调用该方法设置参数为false，即开启事务
				* 提交事务：commit() 
				* 回滚事务：rollback() 
```

#### 3.Statement：执行sql的对象

```sql
3. Statement：执行sql的对象
		1. 执行sql
			1. boolean execute(String sql) ：可以执行任意的sql 了解 
			2. int executeUpdate(String sql) ：执行DML（insert、update、delete）语句、DDL(create，alter、drop)语句
				* 返回值：影响的行数，可以通过这个影响的行数判断DML语句是否执行成功 返回值>0的则执行成功，反之，则失败。
			3. ResultSet executeQuery(String sql)  ：执行DQL（select)语句
		2. 练习：
			1. account表 添加一条记录
			2. account表 修改记录
			3. account表 删除一条记录

			代码：
				Statement stmt = null;
		        Connection conn = null;
		        try {
		            //1. 注册驱动
		            Class.forName("com.mysql.jdbc.Driver");
		            //2. 定义sql
		            String sql = "insert into account values(null,'王五',3000)";
		            //3.获取Connection对象
		            conn = DriverManager.getConnection("jdbc:mysql:///db3", "root", "root");
		            //4.获取执行sql的对象 Statement
		            stmt = conn.createStatement();
		            //5.执行sql
		            int count = stmt.executeUpdate(sql);//影响的行数
		            //6.处理结果
		            System.out.println(count);
		            if(count > 0){
		                System.out.println("添加成功！");
		            }else{
		                System.out.println("添加失败！");
		            }
		
		        } catch (ClassNotFoundException e) {
		            e.printStackTrace();
		        } catch (SQLException e) {
		            e.printStackTrace();
		        }finally {
		            //stmt.close();
		            //7. 释放资源
		            //避免空指针异常
		            if(stmt != null){
		                try {
		                    stmt.close();
		                } catch (SQLException e) {
		                    e.printStackTrace();
		                }
		            }
		
		            if(conn != null){
		                try {
		                    conn.close();
		                } catch (SQLException e) {
		                    e.printStackTrace();
		                }
		            }
		        }
			
```



#### 4.ResultSet：结果集对象,封装查询结果

boolean next(): 游标向下移动一行，判断当前行是否是最后一行末尾(是否有数据)，如果是，则返回false，如果不是则返回true
* getXxx(参数):获取数据
		* Xxx：代表数据类型   如： int getInt() ,	String getString()
		* 参数：
			1. int：代表列的编号,从1开始   如： getString(1)
			2. String：代表列名称。 如： getDouble("balance")
	
	* 注意：
		* 使用步骤：
			1. 游标向下移动一行
			2. 判断是否有数据
			3. 获取数据

```sql
			//循环判断游标是否是最后一行末尾。
	            while(rs.next()){
	                //获取数据
	                //6.2 获取数据
	                int id = rs.getInt(1);
	                String name = rs.getString("name");
	                double balance = rs.getDouble(3);
	
	                System.out.println(id + "---" + name + "---" + balance);
	            }

		* 练习：
			* 定义一个方法，查询emp表的数据将其封装为对象，然后装载集合，返回。
				1. 定义Emp类
				2. 定义方法 public List<Emp> findAll(){}
				3. 实现方法 select * from emp;
```







# 抽取JDBC工具类 ： JDBCUtils



* 目的：简化书写
* 分析：

1.注册驱动也抽取

2.抽取一个方法获取连接对象

​	* 需求：不想传递参数（麻烦），还得保证工具类的通用性。

 * 解决：**配置文件**

   ```sql
   	jdbc.properties
   		url=
   		user=
   		password=
   ```

3.抽取一个方法释放资源

 **代码实现：**


```java
* 代码实现：
	public class JDBCUtils {
    private static String url;
    private static String user;
    private static String password;
    private static String driver;
    /**
     * 文件的读取，只需要读取一次即可拿到这些值。使用静态代码块
     */
    static{
        //读取资源文件，获取值。

        try {
            //1. 创建Properties集合类。
            Properties pro = new Properties();

            //获取src路径下的文件的方式--->ClassLoader 类加载器
            ClassLoader classLoader = JDBCUtils.class.getClassLoader();
            URL res  = classLoader.getResource("jdbc.properties");
            String path = res.getPath();
            System.out.println(path);///D:/IdeaProjects/itcast/out/production/day04_jdbc/jdbc.properties
            //2. 加载文件
           // pro.load(new FileReader("D:\\IdeaProjects\\itcast\\day04_jdbc\\src\\jdbc.properties"));
            pro.load(new FileReader(path));

            //3. 获取数据，赋值
            url = pro.getProperty("url");
            user = pro.getProperty("user");
            password = pro.getProperty("password");
            driver = pro.getProperty("driver");
            //4. 注册驱动
            Class.forName(driver);
        } catch (IOException e) {
            e.printStackTrace();
        } catch (ClassNotFoundException e) {
            e.printStackTrace();
        }
    }
```


​	

```java
    /**
     * 获取连接
     * @return 连接对象
     */
    public static Connection getConnection() throws SQLException {

        return DriverManager.getConnection(url, user, password);
    }

    /**
     * 释放资源
     * @param stmt
     * @param conn
     */
    public static void close(Statement stmt,Connection conn){
        if( stmt != null){
            try {
                stmt.close();
            } catch (SQLException e) {
                e.printStackTrace();
            }
        }

        if( conn != null){
            try {
                conn.close();
            } catch (SQLException e) {
                e.printStackTrace();
            }
        }
    }
	
    /**
     * 释放资源
     * @param stmt
     * @param conn
     */
    public static void close(ResultSet rs,Statement stmt, Connection conn){
        if( rs != null){
            try {
                rs.close();
            } catch (SQLException e) {
                e.printStackTrace();
            }
        }

        if( stmt != null){
            try {
                stmt.close();
            } catch (SQLException e) {
                e.printStackTrace();
            }
        }

        if( conn != null){
            try {
                conn.close();
            } catch (SQLException e) {
                e.printStackTrace();
            }
        }
    }

}

```

​	

## 练习：

需求：
1. 通过键盘录入用户名和密码
2. 判断用户是否登录成功
	* select * from user where username = "" and password = "";
	* 如果这个sql有查询结果，则成功，反之，则失败



```java
	* 步骤：
		1. 创建数据库表 user
			CREATE TABLE USER(
				id INT PRIMARY KEY AUTO_INCREMENT,
				username VARCHAR(32),
				PASSWORD VARCHAR(32)
			
			);

			INSERT INTO USER VALUES(NULL,'zhangsan','123');
			INSERT INTO USER VALUES(NULL,'lisi','234');

		2. 代码实现：
			public class JDBCDemo9 {

			    public static void main(String[] args) {
			        //1.键盘录入，接受用户名和密码
			        Scanner sc = new Scanner(System.in);
			        System.out.println("请输入用户名：");
			        String username = sc.nextLine();
			        System.out.println("请输入密码：");
			        String password = sc.nextLine();
			        //2.调用方法
			        boolean flag = new JDBCDemo9().login(username, password);
			        //3.判断结果，输出不同语句
			        if(flag){
			            //登录成功
			            System.out.println("登录成功！");
			        }else{
			            System.out.println("用户名或密码错误！");
			        }
                }
```


​				  


​				
​				

```java
			    /**
			     * 登录方法
			     */
			    public boolean login(String username ,String password){
			        if(username == null || password == null){
			            return false;
			        }
			        //连接数据库判断是否登录成功
			        Connection conn = null;
			        Statement stmt =  null;
			        ResultSet rs = null;
			        //1.获取连接
			        try {
			            conn =  JDBCUtils.getConnection();
			            //2.定义sql
			            String sql = "select * from user where username = '"+username+"' and password = '"+password+"' ";
			            //3.获取执行sql的对象
			            stmt = conn.createStatement();
			            //4.执行查询
			            rs = stmt.executeQuery(sql);
			            //5.判断
			           /* if(rs.next()){//如果有下一行，则返回true
			                return true;
			            }else{
			                return false;
			            }*/
			           return rs.next();//如果有下一行，则返回true
			
			        } catch (SQLException e) {
			            e.printStackTrace();
			        }finally {
			            JDBCUtils.close(rs,stmt,conn);
			        }
                    return false;
			    }
			}
```


​				

## SQL注入问题

####  5.PreparedStatement：执行sql的对象

```java
5. PreparedStatement：执行sql的对象
		1. SQL注入问题：在拼接sql时，有一些sql的特殊关键字参与字符串的拼接。会造成安全性问题
			1. 输入用户随便，输入密码：a' or 'a' = 'a
			2. sql：select * from user where username = 'fhdsjkf' and password = 'a' or 'a' = 'a' 

		2. 解决sql注入问题：使用PreparedStatement对象来解决
		3. 预编译的SQL：参数使用?作为占位符
		4. 步骤：
			1. 导入驱动jar包 mysql-connector-java-5.1.37-bin.jar
			2. 注册驱动
			3. 获取数据库连接对象 Connection
			4. 定义sql
				* 注意：sql的参数使用？作为占位符。 如：
    			select * from user where username = ? and password = ?;
			5. 获取执行sql语句的对象 
                PreparedStatement  Connection.prepareStatement(String sql) 
			6. 给？赋值：
				* 方法： setXxx(参数1,参数2)
					* 参数1：？的位置编号 从1 开始
					* 参数2：？的值
			7. 执行sql，接受返回结果，不需要传递sql语句
			8. 处理结果
			9. 释放资源

		5. 注意：后期都会使用PreparedStatement来完成增删改查的所有操作
			1. 可以防止SQL注入
			2. 效率更高
```

![image-20201111194035155](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201111194035155.png)















# JDBC控制事务：

1. 事务：一个包含多个步骤的业务操作。如果这个业务操作被事务管理，则这多个步骤要么同时成功，要么同时失败。
2. 操作：
	1. 开启事务
	2. 提交事务
	3. 回滚事务
3. 使用Connection对象来管理事务
	* 开启事务：setAutoCommit(boolean autoCommit) ：调用该方法设置参数为false，即开启事务
		
		* 在执行sql之前开启事务
		
		  ```java
		  //开启事务
		  	            conn.setAutoCommit(false);
		  ```
		
	* 提交事务：commit() 
		
		* 当所有sql都执行完提交事务
		
		  ```java
		  //提交事务
		  	            conn.commit();
		  ```
		
	* 回滚事务：rollback() 
		
		* 在catch中回滚事务（因为有异常）
		
		  ```java
		  try {
		  	     if(conn != null) {
		  	         conn.rollback();
		  	       }
		  }
		  ```
		
		  



```java
4. 代码：
	public class JDBCDemo10 {

	    public static void main(String[] args) {
	        Connection conn = null;
	        PreparedStatement pstmt1 = null;
	        PreparedStatement pstmt2 = null;
	
	        try {
	            //1.获取连接
	            conn = JDBCUtils.getConnection();
	            //开启事务
	            conn.setAutoCommit(false);
	
	            //2.定义sql
	            //2.1 张三 - 500
	            String sql1 = "update account set balance = balance - ? where id = ?";
	            //2.2 李四 + 500
	            String sql2 = "update account set balance = balance + ? where id = ?";
	            //3.获取执行sql对象
	            pstmt1 = conn.prepareStatement(sql1);
	            pstmt2 = conn.prepareStatement(sql2);
	            //4. 设置参数
	            pstmt1.setDouble(1,500);
	            pstmt1.setInt(2,1);
	
	            pstmt2.setDouble(1,500);
	            pstmt2.setInt(2,2);
	            //5.执行sql
	            pstmt1.executeUpdate();
	            // 手动制造异常
	            int i = 3/0;
	
	            pstmt2.executeUpdate();
	            //提交事务
	            conn.commit();
	        } catch (Exception e) {
	            //事务回滚
	            try {
	                if(conn != null) {
	                    conn.rollback();
	                }
	            } catch (SQLException e1) {
	                e1.printStackTrace();
	            }
	            e.printStackTrace();
	        }finally {
	            JDBCUtils.close(pstmt1,conn);
	            JDBCUtils.close(pstmt2,null);
	        }
	  }
	
}
```


​		



# 今日内容

	1. 数据库连接池
	
	2. Spring JDBC : JDBC Template





# 数据库连接池

## **1.概念：**

​	其实就是一个容器(集合)，存放数据库连接的容器。
​    当系统初始化好后，容器被创建，容器中会申请一些连接对象，当用户来访问数据库时，从容器中获取连接对象，用户访问完之后，会将连接对象归还给容器。

![image-20201111202439989](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201111202439989.png)





## **2.好处：**

1. 节约资源
2. 用户访问高效



## **3.实现：**

1. 标准接口：DataSource   javax.sql包下的
	1. 方法：
		* 获取连接：getConnection()
		* **归还连接：Connection.close()**。如果连接对象Connection是从连接池中获取的，那么调用Connection.close()方法，则不会再关闭连接了。而是归还连接

2. 一般我们不去实现它，有数据库厂商来实现
	1. C3P0：数据库连接池技术
	2. Druid：数据库连接池实现技术，由阿里巴巴提供的



## **4.C3P0：数据库连接池技术**

* 步骤：
	1. 导入jar包 (两个) c3p0-0.9.5.2.jar mchange-commons-java-0.2.12.jar ，
		* 不要忘记导入数据库驱动jar包
	2. 定义配置文件：
		* 名称： c3p0.properties 或者 c3p0-config.xml
		* 路径：直接将文件放在src目录下即可。

	3. 创建核心对象 数据库连接池对象 ComboPooledDataSource
	4. 获取连接： getConnection
* 代码：
	 //1.创建数据库连接池对象
     DataSource ds  = new ComboPooledDataSource();
     //2. 获取连接对象
     Connection conn = ds.getConnection();



## 5.Druid：数据库连接池实现技术，由阿里巴巴提供的

1. 步骤：
	1. 导入jar包 druid-1.0.9.jar
	2. 定义配置文件：
		* 是properties形式的
		* 可以叫任意名称，可以放在任意目录下
	3. 加载配置文件。Properties
	4. 获取数据库连接池对象：通过工厂来来获取  DruidDataSourceFactory
	5. 获取连接：getConnection
* 代码：
	
   ```java
   //3.加载配置文件
     Properties pro = new Properties();
     InputStream is = 		      DruidDemo.class.getClassLoader().getResourceAsStream("druid.properties");
     pro.load(is);
     //4.获取连接池对象
     DataSource ds = DruidDataSourceFactory.createDataSource(pro);
     //5.获取连接
     Connection conn = ds.getConnection();
   ```
   
   
2. 定义工具类
	1. 定义一个类 JDBCUtils
	2. 提供静态代码块加载配置文件，初始化连接池对象
	3. 提供方法
		1. 获取连接方法：通过数据库连接池获取连接
		2. 释放资源
		3. 获取连接池的方法






```java
	* 代码：
		public class JDBCUtils {

		    //1.定义成员变量 DataSource
		    private static DataSource ds ;
		
		    static{
		        try {
		            //1.加载配置文件
		            Properties pro = new Properties();
		            pro.load(JDBCUtils.class.getClassLoader().getResourceAsStream("druid.properties"));
		            //2.获取DataSource
		            ds = DruidDataSourceFactory.createDataSource(pro);
		        } catch (IOException e) {
		            e.printStackTrace();
		        } catch (Exception e) {
		            e.printStackTrace();
		        }
		    }
		
		    /**
		     * 获取连接
		     */
		    public static Connection getConnection() throws SQLException {
		        return ds.getConnection();
		    }
		
		    /**
		     * 释放资源
		     */
		    public static void close(Statement stmt,Connection conn){
		       /* if(stmt != null){
		            try {
		                stmt.close();
		            } catch (SQLException e) {
		                e.printStackTrace();
		            }
		        }
		
		        if(conn != null){
		            try {
		                conn.close();//归还连接
		            } catch (SQLException e) {
		                e.printStackTrace();
		            }
		        }*/
		
		       close(null,stmt,conn);
		    }
```


​			

			    public static void close(ResultSet rs , Statement stmt, Connection conn){
	
			        if(rs != null){
			            try {
			                rs.close();
			            } catch (SQLException e) {
			                e.printStackTrace();
			            }
			        }		

```java
		        if(stmt != null){
		            try {
		                stmt.close();
		            } catch (SQLException e) {
		                e.printStackTrace();
		            }
		        }
		
		        if(conn != null){
		            try {
		                conn.close();//归还连接
		            } catch (SQLException e) {
		                e.printStackTrace();
		            }
		        }
		    }
		
		    /**
		     * 获取连接池方法
		     */
		
		    public static DataSource getDataSource(){
		        return  ds;
		    }
		
		}
```



# Spring JDBC

 Spring框架对JDBC的简单封装。提供了一个JDBCTemplate对象简化JDBC的开发

**步骤：**

1. 导入jar包

2. 创建JdbcTemplate对象。依赖于数据源DataSource

  ```java
  JdbcTemplate template = new JdbcTemplate(ds);
  ```

  

3. 调用JdbcTemplate的方法来完成CRUD的操作

  **update():**执行DML语句。增、删、改语句

  **queryForMap():**查询结果将结果集封装为map集合，将列名作为key，将值作为value 将这条记录封装为一个map集合

  注意：这个方法查询的结果集长度只能是1

  **queryForList():**查询结果将结果集封装为list集合

  * 注意：将每一条记录封装为一个Map集合，再将Map集合装载到List集合中

  **query():**查询结果，将结果封装为JavaBean对象

  * query的参数：RowMapper
  	* 一般我们使用**BeanPropertyRowMapper**实现类。可以完成数据到JavaBean的自动封装
  	* **new BeanPropertyRowMapper<类型>(类型.class)**

  **queryForObject：**查询结果，将结果封装为对象

  * 一般用于聚合函数的查询



入门：

![image-20201111211731618](D:\java学习\1.Java基础\06.集合\14.【List、Set】\14.【List、Set】-笔记\就业班-day03-List、Set、数据结构、Collections\img\image-20201111211731618.png)





```java
4. 练习：
		* 需求：
			1. 修改1号数据的 salary 为 10000
			2. 添加一条记录
			3. 删除刚才添加的记录
			4. 查询id为1的记录，将其封装为Map集合
			5. 查询所有记录，将其封装为List
			6. 查询所有记录，将其封装为Emp对象的List集合
			7. 查询总记录数

		* 代码：
			
			import cn.itcast.domain.Emp;
			import cn.itcast.utils.JDBCUtils;
			import org.junit.Test;
			import org.springframework.jdbc.core.BeanPropertyRowMapper;
			import org.springframework.jdbc.core.JdbcTemplate;
			import org.springframework.jdbc.core.RowMapper;
			
			import java.sql.Date;
			import java.sql.ResultSet;
			import java.sql.SQLException;
			import java.util.List;
			import java.util.Map;
			
			public class JdbcTemplateDemo2 {
			
			    //Junit单元测试，可以让方法独立执行
```


​				

```java
			    //1. 获取JDBCTemplate对象
			    private JdbcTemplate template = new JdbcTemplate(JDBCUtils.getDataSource());
			    /**
			     * 1. 修改1号数据的 salary 为 10000
			     */
			    @Test
			    public void test1(){
			
			        //2. 定义sql
			        String sql = "update emp set salary = 10000 where id = 1001";
			        //3. 执行sql
			        int count = template.update(sql);
			        System.out.println(count);
			    }
			
			    /**
			     * 2. 添加一条记录
			     */
			    @Test
			    public void test2(){
			        String sql = "insert into emp(id,ename,dept_id) values(?,?,?)";
			        int count = template.update(sql, 1015, "郭靖", 10);
			        System.out.println(count);
			
			    }
			
			    /**
			     * 3.删除刚才添加的记录
			     */
			    @Test
			    public void test3(){
			        String sql = "delete from emp where id = ?";
			        int count = template.update(sql, 1015);
			        System.out.println(count);
			    }
			
			    /**
			     * 4.查询id为1001的记录，将其封装为Map集合
			     * 注意：这个方法查询的结果集长度只能是1
			     */
			    @Test
			    public void test4(){
			        String sql = "select * from emp where id = ? or id = ?";
			        Map<String, Object> map = template.queryForMap(sql, 1001,1002);
			        System.out.println(map);
			        //{id=1001, ename=孙悟空, job_id=4, mgr=1004, joindate=2000-12-17, salary=10000.00, bonus=null, dept_id=20}
			
			    }
			
			    /**
			     * 5. 查询所有记录，将其封装为List
			     */
			    @Test
			    public void test5(){
			        String sql = "select * from emp";
			        List<Map<String, Object>> list = template.queryForList(sql);
			
			        for (Map<String, Object> stringObjectMap : list) {
			            System.out.println(stringObjectMap);
			        }
			    }
			
			    /**
			     * 6. 查询所有记录，将其封装为Emp对象的List集合
			     */
			
			    @Test
			    public void test6(){
			        String sql = "select * from emp";
			        List<Emp> list = template.query(sql, new RowMapper<Emp>() {
			
			            @Override
			            public Emp mapRow(ResultSet rs, int i) throws SQLException {
			                Emp emp = new Emp();
			                int id = rs.getInt("id");
			                String ename = rs.getString("ename");
			                int job_id = rs.getInt("job_id");
			                int mgr = rs.getInt("mgr");
			                Date joindate = rs.getDate("joindate");
			                double salary = rs.getDouble("salary");
			                double bonus = rs.getDouble("bonus");
			                int dept_id = rs.getInt("dept_id");
			
			                emp.setId(id);
			                emp.setEname(ename);
			                emp.setJob_id(job_id);
			                emp.setMgr(mgr);
			                emp.setJoindate(joindate);
			                emp.setSalary(salary);
			                emp.setBonus(bonus);
			                emp.setDept_id(dept_id);
			
			                return emp;
			            }
			        });
```


​				

```java
			        for (Emp emp : list) {
			            System.out.println(emp);
			        }
			    }
			
			    /**
			     * 6. 查询所有记录，将其封装为Emp对象的List集合
			     */
			
			    @Test
			    public void test6_2(){
			        String sql = "select * from emp";
			        List<Emp> list = template.query(sql, new BeanPropertyRowMapper<Emp>(Emp.class));
			        for (Emp emp : list) {
			            System.out.println(emp);
			        }
			    }
			
			    /**
			     * 7. 查询总记录数
			     */
			
			    @Test
			    public void test7(){
			        String sql = "select count(id) from emp";
			        Long total = template.queryForObject(sql, Long.class);
			        System.out.println(total);
			    }
			
			}
```


​			
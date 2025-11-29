# mysql 笔记

## class 1 ：终端操作MySQL

### 终端启动MySQL服务

```cmd
net start mysql80
```

### 终端停止MySQL服务

```cmd
net stop mysql80
```

### 终端登录mysql

命令：mysql -u "用户名" -p "密码"

```cmd
mysql -u root -p root
```

## class 2 : Navicat操作MySQL

### 创建数据库

```mysql
create database name if not exists database_name;
```

### 删除数据库

```mysql
drop database name if not exists database_name ;
```

### 打开数据库

```mysql
use database_name;
```

### 查看数据库

```mysql
show DATABASES;
```

### 查看字符集

```mysql
show CHARACTER SET;
```

### 创建数据库同时设置编码和校对规则

```mysql
CREATE DATABASE if not EXISTS haha CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci;
```

### 查看校对规则

```mysql
show VARIABLES like "CHARACTER_set_database";
```

### 查看数据库的校对规则

```mysql
show VARIABLES like "collation_server";
```

### 查看特定数据库的校对规则

```mysql
show CREATE DATABASE table_name;
```

### 查看表的校对规则

```mysql
show CREATE TABLE table_name;
```

### 创建表

```mysql
CREATE table table_name
(
colum_name1 VARCHAR(4) primary key,
colum_name2 VARCHAR(3)
);
```

### 修改表名

```mysql
alter table table_name1 rename to table_name2;
```

### 添加列主键

```mysql
alter table table_name2 add PRIMARY key(colum_name);
```

### 添加列

```mysql
alter table table_name2 add colum_name3 int null;
```

### 修改列类型

```mysql
alter table table_name2 MODIFY colum_name3 char(4) null;
```

### 删除列

```mysql
alter table table_name2 drop colum_name3;
```

### 删除表

```mysql
drop TABLE if EXISTS table_name;
```

## class 3 : 字段约束

### 单字段主键

方法一: 定义列级主键

```mysql
CREATE TABLE customers (      
cid char (6) primary key,   
ctruename  varchar(30) not null,
cpassword  varchar(30) not null,
csex  char(2),
caddress  varchar(50) ,
cmobile   varchar(11) ,
cemail  varchar(50) ,
cregisterdate  datetime
);
```

方法二: 定义表级主键

```mysql
CREATE TABLE customers (      
cid             char (6)       not null,   
ctruename       varchar(30)    not null,
cpassword       varchar(30)   not null,
csex            char(2)       not null,
caddress         varchar(50) ,
cmobile         varchar(11)    not null,
cemail          varchar(50) ,
cregisterdate     datetime      not null,
Primary Key(cid)
);
```

### 复合主键: 多个字段联合组成，只能定义为表的完整性约束。

```mysql
CREATE TABLE orderdetails(      
oid  char (14),
gid  char(6) ,
odprice  float,
odnumber int,
primary key(oid,gid)
);
```

### 自动增长约束

```mysql
CREATE TABLE users (
     id INT  AUTO_INCREMENT,
    username VARCHAR(50) ,
    email VARCHAR(100) ,
    PRIMARY KEY (id)
);
```

### 非空约束

```mysql
CREATE TABLE category
(
  caid  char(2)  primary key,
   caname varchar not null,
   cadeleted bit  
);
```

### 检查约束 

方法一：列级check约束

```mysql
CREATE TABLE salary
 (
    id INT primary key,
    name varchar(25),
    deptId int,
    salary float check(salary>0 and salary<50000)
  );


```

方法二: 表级check约束

```mysql
CREATE TABLE  student
    (
    stuno char(6) NOT NULL,
    sex char(2),
    check(sex  in ('男','女'))
    );
```

### 唯一约束

方法一： 列级唯一约束

```mysql
create table category (
caid char(2)  primary key,
caname varchar(20)   not null unique,
cadeleted bit  not null
);
```

方法二: 标记唯一约束

```mysql
create table category (
caid  char(2)  primary key,
caname  varchar(20)   not null,
cadeleted  bit  not null,
unique(caname)
);
```

### 默认值约束

```mysql
CREATE TABLE category
(
  caid  char(2)  primary key,
   caname varchar(20),
   cadeleted bit  default 0
);

```

### 外键约束 ： 必须先创建好customers表并且以cid列为主键

```mysql
CREATE TABLE orders (      
oid     char(14)    PRIMARY KEY,
cid     char(6)      not null,
odate   datetime     not null,
osum   float        not null,
ostatus  char(1)      not null,
FOREIGN KEY(cid)  REFERENCES customers(cid)
);    
```

### 综合案例

```mysql
在一张表中设置各种约束：
CREATE TABLE employees (
    employee_id INT NOT NULL AUTO_INCREMENT,      -- 主键约束 + 自动递增
    first_name VARCHAR(50) NOT NULL,             -- 非空约束
    last_name VARCHAR(50) NOT NULL,              -- 非空约束
    email VARCHAR(100) NOT NULL UNIQUE,          -- 唯一约束 + 非空约束
    hire_date DATE DEFAULT (CURRENT_DATE),       -- 默认约束
    salary  DECIMAL(10, 2) NOT NULL,              -- 非空约束
        PRIMARY KEY (employee_id)                    -- 主键约束
);
```

## class 4 ： 数据管理(增，删，查，改)

### 添加记录

插入单条记录 :  

```mysql
INSERT INTO table_name(id) VALUES (1);
```

所有字段插入数据

```mysql
insert into table_name values(1);
```

向指定列插入数据

```mysql
INSERT INTO table_name(col_name,col_name2...col_name3) VALUES (value1,value2.. value3);
```

### 修改记录

修改id为1的名字

```
UPDATE table_name
SET col_name=value, col_name1=value1,…col_name2=value2
where id = 1
```

修改全部名字

```mysql
UPDATE table_name
SET col_name=value, col_name1=value1,…col_name2=value2;
```

### 删除记录

删除id为1的列

```mysql
DELETE FROM table_name where id = 1;
```

方法一： 删除表中所有数据

```mysql
DELETE FROM table_name;
```

方法二： 删除表中所有数据

```mysql
truncate table;
```

### delete 和 truncate 的区别:

1.truncate 不带任何条件（包括where ，order by,limit等） 语法只有一条： TRUNCATE [TABLE] **tbl_name** 而delete可以。

2.truncate 不能一次删除多个表的数据，而delete可以。

3.runcate不能带条件，所以可以看出truncate 属于表级别删除，一次行删除表中所有数据，而不能指定某行而delete可以。

4.truncate 会删掉自增的值，而delete 会保留.

5.delete 是属于dml语句，truncate是属于ddl 删除，因此，delete 作用与事务，删除时会进入回滚段中，在没有设置自动提交的前提下，还以rollback 操作进行回滚，而truncate则不可回滚。

6.delete 是一条一条删除，日志会记录每行数据的删除记录，而truncate 只记录TRUNCATE TABLE 通过释放存储表数据所用的数据页来删除数据，并且只在事务日志中记录页的释放。

7.对于由 FOREIGN KEY 约束引用的表，不能使用 TRUNCATE TABLE，而应使用不带 WHERE 子句的 DELETE 语句。由于 TRUNCATE TABLE 不记录在日志中，所以它不能激活触发器。

8.truncate比delete 快，大量数据时切不考虑事务时，可用truncate.

9.truncate比delete 快，大量数据时切不考虑事务时，可用truncate.

### 4 种SQL语言:

| 类别    |           英文全称           |      核心作用      |                常用语句                |
| ------- | :--------------------------: | :----------------: | :------------------------------------: |
| DDL     |   Data Definition Language   | 定义数据库对象结构 | `CREATE`, `ALTER`, `DROP`, `TRUNCATE`  |
| **DML** |  Data Manipulation Language  | 操作数据库中的数据 | `INSERT`, `UPDATE`, `DELETE`, `SELECT` |
| **DCL** |    Data Control Language     |    管理用户权限    |           `GRANT`, `REVOKE`            |
| **TCL** | Transaction Control Language |    管理事务流程    |   `COMMIT`, `ROLLBACK`, `SAVEPOINT`    |

### 单表查询和条件查询

查询book表

```mysql
SELECT * from book;
```

查询book表的id字段和书名字段,并用别名命名列

```mysql
SELECT bookid, bookname as 书名 from book;
```

去掉重复的typeid值

```mysql
SELECT DISTINCT typeid from book;
```

查询readerid大于20的读者

```mysql
SELECT readername from reader where readerid > 20;
```

查询读者id为0016的读者

```mysql
SELECT readername from reader where readerid = 0016;
```

查询book表typeid在1-5之间的书名

```mysql
SELECT bookname from book where typeid BETWEEN 1 and 5;
```

 查询没有写typeid的作者

```mysql
SELECT bookauthor from book where typeid is null;
```

查询包含程序的书名称

```mysql
SELECT bookname from book where bookname like '%程序%';
```

查询姓张的作者

```mysql
SELECT bookauthor from book where bookauthor like "张%";
```

 查询名字以轩结尾的作者

```mysql
SELECT bookauthor from book where bookauthor like "%轩";
```

*查询名字为黄XX作者的书名*

```mysql
SELECT bookname from book where bookauthor like "黄__";
```

### 排序

查询书籍表中书籍名称和书籍价格并按价格从高到低排列

```mysql
select gname,gprice from goods order by gprice desc;
```

查询书籍表中书籍名称和书籍价格并按价格从低到高排列

```mysql
select gname,gprice from goods order by gprice asc;
```

查询书籍表价格30元以上的书籍类别、书籍名称和书籍价格，要求类别升序排列，如果类别相同，再按价格降序排列

```mysql
select gtypeid,gname,gprice 
from goods 
where gprice>30 
order by gtypeid asc,gprice desc;
```

### 限制行数

查找商品表中价格最靠前的从第3条记录开始的3条记录的名称和价格 

```mysql
SELECT gname AS"书名",  gprice AS"价格"
FROM goods
ORDER BY gprice desc 
LIMIT 2,3;
```

注意：偏移量初始行为0

### 聚合函数

查询书籍表中的书籍的数量，书籍价格的最大值、最小值、平均值和总库存数

```sql
select count(*) as 书籍总数, avg(Bprice) as 平均价格, MAX(Bprice) as 最高价格, min(Bprice) as 最小价格, sum(Bnumber) as 书本数量 from book;
```

### 分组查询

对书籍表中的书籍按照书籍类别分类，统计各类书籍的数量和均价。

```sql
select Btypeid, count(*) as 数量, avg(Bprice) as 平均价格 
from books
group by Btypeid;
```

对书籍表中的书籍按照书籍类别进行统计，查找书籍类别为“05”的书籍的数量和均价。 

注意:  使用having进行过滤查找,需要是聚合函数后的字段,不能是原始字段

```sql
select Btypeid,count(*) as 数量, avg(Bprice) as 平均价格
from books
group by Btypeid
having Btypeid='05';
```

```sql
select Btypeid,count(*) as 数量, avg(Bprice) as 均价
from books
where Btypeid='05'
group by Btypeid;
```

对书籍表中的书籍按照书籍类别进行统计，查找平均价格大于30的书籍的数量和均价。

```sql
select Btypeid, count(*) as 数量, avg(Bprice) as 平均价格
from books
where Bprice > 30
group by Btypeid;
```

对书籍表中的书籍按照书籍类别分类统计，按照均价从高到低排序。 

```sql
select Btypeid, avg(Bprice) as 平均价格 
from books	
group by Btypeid 
order by 平均价格 desc;
```

显示每个分组中的字段,对书籍表中的书籍按照书籍类别分类统计，同时显示出每组中书籍的名称和每组中书籍的个数。

```sql
select Btypeid,GROUP_CONCAT(Bname) Bnames,COUNT(Bname) number
FROM books 
GROUP BY Btypeid;
```

### 内连接

查询书籍类别编号、书籍类别名称及其书籍的相关信息。

```sql
select caid, caname, Bid, Bname, Btypeid 
from category,books
where caid = Btypeid;
```

```sql
select category.caid, category.caname, books.Bid, books.Bname, books.Btypeid 
from category,books
where category.caid = books.Btypeid;
```

查询书籍类别id为03的书籍类别编号、名称及其书籍的相关信息。

```sql
select caid, caname, Bid, Bname
from category, books
where caid = "03" and caid = Btypeid;
```

查询书籍类别编号、书籍类别名称及其书籍的相关信息。(join...on)	

```sql
select caid, caname, Bid, Bname
from category join books
on caid = Btypeid;
```

查询书籍类别为03的书籍类别编号、名称及其书籍的相关信息。

```sql
select caid, caname, Bid, Bname
from category join books
on caid = Btypeid and caid  = "03";
```

### 子查询

查询价格高于 “现代遗传学”的书籍的书籍号、书籍名称和书籍单价，并按价格从高到低排序。

```sql
select Bid, Bname, Bprice
from books
where Bprice > (select Bprice from books where Bname = '现代遗传学')
order by Bprice desc;
```

查询书籍类别是“软件开发”的所有书籍信息，包括书籍名称和书籍价格。

```sql
select Bname, Bprice, Btypeid 
from books
where Btypeid = (select caid from category where caname = '软件开发');
```

```sql
select Bname, Bprice, Btypeid 
from books
join category
on books.Btypeid = category.caid and category.caname = "软件开发"
```



















# class 1

// 此处为第一次上课做笔记的记录

第一范式：不能有重复列
	必须最小单元格
	要有唯一标识
第二范式：非主键列必须完全依赖于主键列   x---->y 可以传递依赖

第三范式:满足第二范式
	非主键列要依赖于非主键列  不能传递依赖
	
创建索引代码格式：	

create index (索引名) on 表名(列[长度][升序/降序])

创建视图格式（即虚拟一个表）
create view 视图名
as 
select .....(和平常的子查询语句一样，构建一个视图，类似一个子表，定制每个顾客的信息)

# class2

set name名 # 定义一个变量名复制（可以计算）
select name名  # 查询   select (select语句,例如where限制)
---- 理解：封装函数 (输入函数)-----
DELIMITER // #创建临时结束符 #一定要大写
CREATE PROCEDURE pro_querybypublisher(in publisher VARCHAR(20), in price int) #创建存储过程
BEGIN #开始
	SELECT * from goods
	where publisher = gpublisher and price < gprice; # select语句 
end // #  以 // 结束
DELIMITER ; # 恢复结束符 ；
call pro_querybypublisher('湖南教育出版社',50) #调用函数

输出函数 

用select ... into ... # 把...赋值给...
调用时需要:
初始化变量名 @变量名 = 0
call 存储名（@变量名)
select @变量名

# class 3 

if...else语句 （判断语句）
DELIMITER //
CREATE PROCEDURE checkreader(IN reader_id VARCHAR(10)# 输入参数)  注：输入参数传值进存储过程 ,输出参数是在存储过程传回值
begin	
		declare a VARCHAR(50) DEFAULt null;
    SELECT readerid INTO a FROM reader 
		WHERE readerid = reader_id;
    if a  is null THEN
       SELECT '没有此读者！';
    ELSE
        SELECT * FROM reader WHERE readerid = reader_id;
    END IF; # 结束if语句
END //
DELIMITER ;
call checkreader('0018'); #调用存储
call checkreader('00'); #调用存储
drop PROCEDURE checkreader; #删除存储

开始事务  回滚事务
DELIMITER //
CREATE PROCEDURE up_booktype(in u_bookid varchar(50))
begin
DECLARE a varchar(50); # 声明变量
start TRANSACTION;  #开始事务
	SELECT typeid into a from book 
	where typeid = u_bookid; # 判断book表里的typeid和输入参数是否一致，不一致为空
	update book set typeid = u_bookid # 修改记录，把book表里typeid修改成传入输数
	where bookid = 'TH/2345';
if a = u_bookid  then  # 判断book表里的typeid和输入参数是否一致
	SELECT '提交事务';
	COMMIT; # 提交事务
else
	SELECT '回滚事务';
	ROLLBACK; #回滚事务
end if; # 结束if语句
END //
DELIMITER ;
CALL up_booktype(30);
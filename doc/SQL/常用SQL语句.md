### 常用SQL语句 

#### SQL是用于访问和处理数据库的标准的计算机语言，分为数据定义语言、操作语言、查询语言及控制语言。

| 数据定义语言 | 数据操作语言 | 数据查询语言 | 数据控制语言 | 
| :---: | :---: | :---: | :---: | 
| DDL(Data Definition Language) | DML(Data Manipulation Language) | DQL(Data Query Language) |  DCL(Data Control Language) | 

  * DDL 数据定义语言

  1. 操作库 

``` 
      -- 创建库
      create database db;
      -- 创建库是否存在，不存在则创建 
      create database if not exists db;
      -- 查看所有库
      show databases;
      -- 查看db库的定义信息 
      show create database db;
      -- 修改数据库字符信息
      alter database db character set utf8;
      -- 删除数据库
      drop database db;
  ``` 

  2. 操作表 

``` 
      -- 创建表 
      create table person(
        id int,
        name varchar(32),
        age int,
        score double(4,1),
        birthday date,
        time timestamp
      );
      -- 查看表结构
      desc 表名
      -- 查看创建表的SQL语句
      show create table 表名
      -- 修改表名
      alter table 表名 rename to 新的表名
      -- 添加一列
      alter table 表名 add 列名 数据类型
      -- 删除列
      alter table 表名 drop 列名
      -- 删除表
      alter table 表名
      alter table if exists 表名;

``` 

  * DML 数据操作语言 

  1. 增加 insert into

``` 
    -- 插入表全部数据
    insert into 表名(列名1,列名2,...列名n) values(值1,值2,...值n) 
    -- 只插入值
    insert into 表名 values(值1,值2,...值n)
    -- 插入部分值
    insert into 表名(列名1,列名2) values(值1,值2)

``` 

  2. 删除 delete  

``` 
    -- 删除表中数据
    delete from 表名 where 列名=值
    -- 删除表中所有数据
    delete from 表名
    -- 删除表中所有数据(高效 先删除表然后再创建一张一样的表)
    truncate table 表名
``` 

  3. 修改 update  

``` 
    -- 不带条件修改
    update 表名 set 列名=值
    -- 待条件修改
    update 表名 set 列名=值 where 列名=值

``` 

  * DQL 数据库查询语言 

  1. 基础关键字 

    between...and 在什么之间 和IN(集合)
``` 
    -- 查询成绩大于等于80小于等于90
    select * from gradesheet  where grade>=80 and grade<=90
    select * from gradesheet between 80 and 90
    -- 查询成绩是80 85 90的数据
    select * from gradesheet where grade=80 or grade=85 or grade=90
    select * from gradesheet where grade in(80,85,90)

``` 
    * is null 为null值 或者 is not null 
    * like 模糊查询
    * distinct  去除重复项 

``` 
    -- 查询英语成绩不为null
    select * from gradesheet where english is not null
    
    _:单个任意字符
    %:多个任意字符
    -- 查询姓王的有哪些
    select * from namesheet where name like '马%'
    -- 查询第二个字是维的人
    select * from namesheet where  name like '_维%'
    -- 查询名字是两个字的人
    select * from namesheet where name like '__'
    -- 查询名字有辉的人
    select * from namesheet where name like '%辉%'
    -- 关键词distinct用于返回唯一不同的值
    select distinct 列名 from * namesheet

``` 
  2. 排序查询 order by 

  注意：如果有多个排序字段，则当前面的条件一样时，才会判断第二个条件。

``` 
    --默认升序asc  (降序DESC)
    select * from student order by grade
    select * from student order by grade DESC 
    
``` 

  3. 聚合函数：将一列数据作为一个整体，进行纵向计算  

``` 
    -- count:计算个数
    -- max:计算最大值
    -- min:计算最小值
    -- sum:计算和
    -- avg:计算平均数

``` 

  4. 分组查询 group by 

  group by 分组字段

  注意：分组后查询的字段：分组字段 聚合函数

``` 
    -- 按照性别分组分别查询男女同学的平均分
    select sex,AVG(math) * from student group by sex
    -- 按照性别分组分别查询男女同学的平均分和人数
    select sex,AVG(math),count(id) from student group by sex
    -- 按照性别进行分组查询男女同学的平均分人数，要求分数低于70分的人不参与分组
    select sex,AVG(math),count(id) from student where math>70 group by sex
    -- 

``` 

  5. 分页查询 

``` 

``` 

  6. 内连接查询  

    1. 隐式内连接：使用where条件消除无用数据  
``` 
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

    2. 显式内连接 

``` 

``` 

  7. 外连接查询  

``` 

``` 

  8. 子查询：查询种嵌套查询  

``` 

``` 

  * DCL 

1. 操作库 

``` 

``` 

1. 操作库 

``` 

``` 

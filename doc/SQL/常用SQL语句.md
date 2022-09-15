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

    ``` 

  2. 删除 delete  

    ``` 

    ``` 

  3. 修改 update  

    ``` 

    ``` 

  * DQL 

  1. 操作库 

    ``` 

    ``` 

  2. 操作库 

    ``` 

    ``` 

  2. 操作库 

    ``` 

    ``` 

  2. 操作库 

    ``` 

    ``` 

  2. 操作库 

    ``` 

    ``` 

  2. 操作库 

    ``` 

    ``` 

  2. 操作库 

    ``` 

    ``` 

  2. 操作库 

    ``` 

    ``` 

  * DCL 

1. 操作库 

  ``` 

  ``` 

1. 操作库 

  ``` 

  ``` 

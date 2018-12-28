- 在CentOS7安装好Mysql
- 连接到Mysql服务器：
```
[root@host]# mysql -u root -p
Enter password:*******
```
- xshell终端测试
```
mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
+--------------------+
3 rows in set (0.01 sec)

mysql> create database gc;
Query OK, 1 row affected (0.00 sec)

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| gc                 |
| mysql              |
| performance_schema |
+--------------------+
4 rows in set (0.00 sec)

mysql> drop database gc;
Query OK, 0 rows affected (0.00 sec)

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
+--------------------+
3 rows in set (0.00 sec)

#创建数据库
mysql> create database gc;
Query OK, 1 row affected (0.00 sec)

#使用数据库
mysql> use gc
Database changed

#显示数据库钟存在的tables
mysql> show tables;
Empty set (0.00 sec)

#创建表 account
mysql> CREATE TABLE account(                                                                         
    ->     id bigint(20),
    ->     createTmie datetime,
    ->     ip varchar(255),
    ->     mobile varchar(255),
    ->     nickname varchar(255),
    ->     passwd varchar(255),
    ->     username varchar(255),
    ->     avatar varchar(255),
    ->     brief text,
    ->     job varchar(255),
    ->     location varchar(255),
    ->     qq varchar(255),
    ->     gender int(11),
    ->     city varchar(255),
    ->     province varchar(255)
    ->     );
Query OK, 0 rows affected (0.01 sec)

#显示当前使用的数据库中的所有表
mysql> show tables;
+--------------+
| Tables_in_gc |
+--------------+
| account      |
+--------------+
1 row in set (0.00 sec)

#创建表 account1
mysql> CREATE TABLE account1(                                                                         
    ->     id bigint(20),
    ->     createTmie datetime,
    ->     ip varchar(255),
    ->     mobile varchar(255),
    ->     nickname varchar(255),
    ->     passwd varchar(255),
    ->     username varchar(255),
    ->     avatar varchar(255),
    ->     brief text,
    ->     job varchar(255),
    ->     location varchar(255),
    ->     qq varchar(255),
    ->     gender int(11),
    ->     city varchar(255),
    ->     province varchar(255)
    ->     );
Query OK, 0 rows affected (0.01 sec)

#显示当前使用的数据库中的所有表
mysql> show tables;
+--------------+
| Tables_in_gc |
+--------------+
| account      |
| account1     |
+--------------+
2 rows in set (0.00 sec)

#describe
mysql> describe account;
+------------+--------------+------+-----+---------+-------+
| Field      | Type         | Null | Key | Default | Extra |
+------------+--------------+------+-----+---------+-------+
| id         | bigint(20)   | YES  |     | NULL    |       |
| createTmie | datetime     | YES  |     | NULL    |       |
| ip         | varchar(255) | YES  |     | NULL    |       |
| mobile     | varchar(255) | YES  |     | NULL    |       |
| nickname   | varchar(255) | YES  |     | NULL    |       |
| passwd     | varchar(255) | YES  |     | NULL    |       |
| username   | varchar(255) | YES  |     | NULL    |       |
| avatar     | varchar(255) | YES  |     | NULL    |       |
| brief      | text         | YES  |     | NULL    |       |
| job        | varchar(255) | YES  |     | NULL    |       |
| location   | varchar(255) | YES  |     | NULL    |       |
| qq         | varchar(255) | YES  |     | NULL    |       |
| gender     | int(11)      | YES  |     | NULL    |       |
| city       | varchar(255) | YES  |     | NULL    |       |
| province   | varchar(255) | YES  |     | NULL    |       |
+------------+--------------+------+-----+---------+-------+
15 rows in set (0.03 sec)

#删除表
mysql> drop table account1;
Query OK, 0 rows affected (0.01 sec)

#显示删除后剩下的表格
mysql> show tables;
+--------------+
| Tables_in_gc |
+--------------+
| account      |
+--------------+
1 row in set (0.00 sec)


```

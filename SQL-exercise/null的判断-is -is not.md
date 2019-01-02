- null的判断-is -is not

```
select * from table_name where col_name is null

select * from table_name where col_name is not null
```

---
- 例

```
#登陆连接到Mysql服务器
[root@centos7 ~]# mysql -u root -p
Enter password:*******
```

```
mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| gc                 |
| mysql              |
| performance_schema |
+--------------------+
4 rows in set (0.28 sec)

mysql> use gc
Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A

Database changed
mysql> show tables;
+--------------+
| Tables_in_gc |
+--------------+
| book         |
| newaccount   |
+--------------+
2 rows in set (0.00 sec)

mysql> select * from book;
+------+-------+---------+
| id   | title | content |
+------+-------+---------+
|    1 | t hah | content |
| NULL | NULL  | c       |
|    3 | t     | c       |
+------+-------+---------+
3 rows in set (0.28 sec)

mysql> select * from book where id = null;
Empty set (0.00 sec)

mysql> select * from book where id is null;
+------+-------+---------+
| id   | title | content |
+------+-------+---------+
| NULL | NULL  | c       |
+------+-------+---------+
1 row in set (0.00 sec)

mysql> select * from book where id is not null;
+------+-------+---------+
| id   | title | content |
+------+-------+---------+
|    1 | t hah | content |
|    3 | t     | c       |
+------+-------+---------+
2 rows in set (0.00 sec)

```

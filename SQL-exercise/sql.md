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

```

### distinct(精确的)

---

```
select distinct col_name from table_name;
```
- 例子:

```
select distinct title from book;
```
- select distinct 去掉重复查询结果

```
mysql> select distinct title from book;
+--------+
| title  |
+--------+
| t hah  |
| NULL   |
| t      |
| title1 |
+--------+
4 rows in set (0.01 sec)


mysql> select distinct title,content from book;
+--------+---------+
| title  | content |
+--------+---------+
| t hah  | content |
| NULL   | c       |
| t      | c       |
| title1 | NULL    |
| t      | NULL    |
+--------+---------+
5 rows in set (0.00 sec)

```

---

```
mysql> show tables;
+--------------+
| Tables_in_gc |
+--------------+
| book         |
| newaccount   |
+--------------+
2 rows in set (0.00 sec)

mysql> select title from book;
+-------+
| title |
+-------+
| t hah |
| NULL  |
| t     |
+-------+
3 rows in set (0.00 sec)

mysql> describe book;
+---------+--------------+------+-----+---------+-------+
| Field   | Type         | Null | Key | Default | Extra |
+---------+--------------+------+-----+---------+-------+
| id      | bigint(20)   | YES  |     | NULL    |       |
| title   | varchar(255) | YES  |     | NULL    |       |
| content | varchar(255) | YES  |     | NULL    |       |
+---------+--------------+------+-----+---------+-------+
3 rows in set (0.00 sec)

mysql> insert into book (title)values('title1');
Query OK, 1 row affected (0.00 sec)

mysql> select title from book;
+--------+
| title  |
+--------+
| t hah  |
| NULL   |
| t      |
| title1 |
+--------+
4 rows in set (0.00 sec)

mysql> insert into book (title)values('t');
Query OK, 1 row affected (0.01 sec)

mysql> select title from book;
+--------+
| title  |
+--------+
| t hah  |
| NULL   |
| t      |
| title1 |
| t      |
+--------+
5 rows in set (0.00 sec)

mysql> select * from book;
+------+--------+---------+
| id   | title  | content |
+------+--------+---------+
|    1 | t hah  | content |
| NULL | NULL   | c       |
|    3 | t      | c       |
| NULL | title1 | NULL    |
| NULL | t      | NULL    |
+------+--------+---------+
5 rows in set (0.00 sec)



```


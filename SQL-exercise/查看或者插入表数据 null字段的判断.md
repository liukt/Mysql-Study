- 查看数据

```
select * from table_name;
select col_name1,col_name2, ... from table_name;
```
- 插入数据

```
insert into [table_name] values(值1,值2,...)

insert into [table_name] (列1,列2...)values(值1,值2,...)
```
- 插入数据例子

---

```
insert into book values(1,'t hah','content');
insert into book(title)values('title1');
```


```
CREATE TABLE book(
    id bigint(20),
    title varchar(255),
    content varchar(255)
    );
    
mysql> show tables;
+--------------+
| Tables_in_gc |
+--------------+
| book         |
| newaccount   |
+--------------+
2 rows in set (0.00 sec)

mysql> describe book;
+---------+--------------+------+-----+---------+-------+
| Field   | Type         | Null | Key | Default | Extra |
+---------+--------------+------+-----+---------+-------+
| id      | bigint(20)   | YES  |     | NULL    |       |
| title   | varchar(255) | YES  |     | NULL    |       |
| content | varchar(255) | YES  |     | NULL    |       |
+---------+--------------+------+-----+---------+-------+
3 rows in set (0.00 sec)

mysql> insert into book values(1,'t hah','content');
Query OK, 1 row affected (0.00 sec)

mysql> select * from book;
+------+-------+---------+
| id   | title | content |
+------+-------+---------+
|    1 | t hah | content |
+------+-------+---------+
1 row in set (0.00 sec)

mysql> insert into book(content)values('c');
Query OK, 1 row affected (0.01 sec)

mysql> select * from book;
+------+-------+---------+
| id   | title | content |
+------+-------+---------+
|    1 | t hah | content |
| NULL | NULL  | c       |
+------+-------+---------+
2 rows in set (0.00 sec)

mysql> insert into book values(3,'t','c');
Query OK, 1 row affected (0.00 sec)

mysql> select * from book;
+------+-------+---------+
| id   | title | content |
+------+-------+---------+
|    1 | t hah | content |
| NULL | NULL  | c       |
|    3 | t     | c       |
+------+-------+---------+
3 rows in set (0.00 sec)
```
- where语法

```
select * from table_name where col_name 运算符 值
```
- 例子:

```
select * from book where title = 't';
```
- 组合条件 and、or

---
**where后面可以通过and与or运算组合多个条件筛选**
- 语法:

```
select * from table_name where col1 = xxx and col2 = xx or col3 > xx
```

---

```
mysql> select * from book where id =1;
+------+-------+---------+
| id   | title | content |
+------+-------+---------+
|    1 | t hah | content |
+------+-------+---------+
1 row in set (0.00 sec)

mysql> select * from book where id =1 or content = 'c';
+------+-------+---------+
| id   | title | content |
+------+-------+---------+
|    1 | t hah | content |
| NULL | NULL  | c       |
|    3 | t     | c       |
+------+-------+---------+
3 rows in set (0.00 sec)

mysql> select * from book where content = 'c' and title = 't';
+------+-------+---------+
| id   | title | content |
+------+-------+---------+
|    3 | t     | c       |
+------+-------+---------+
1 row in set (0.00 sec)

mysql> select * from book where content = 'c' and (title = 't' or title = 'b');
+------+-------+---------+
| id   | title | content |
+------+-------+---------+
|    3 | t     | c       |
+------+-------+---------+
1 row in set (0.00 sec)


```




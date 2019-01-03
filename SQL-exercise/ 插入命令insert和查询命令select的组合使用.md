##  插入命令insert和查询命令select的组合使用
- 一般用法：

```
insert into [表名] values(值1,值2,...)
insert into [表名] (列1,列2...)values(值1,值2,...)
```
- insert into 与select的组合用法

```
insert into [表名1] select 列1,列2 from [表名2]
insert into [表名1] (列1,列2) select 列3,列4 from [表名2]
```

---
- 例子

```
CREATE TABLE book2(                                                             
    id bigint(20),
    title varchar(255),
    content varchar(255),
    pages int(11)
   );
```
- delete
```
mysql> delete from book2;
Query OK, 1 row affected (0.00 sec)

mysql> select * from book2;
Empty set (0.00 sec)

mysql> insert into book2 values(1,'sun','content',10);
Query OK, 1 row affected (0.01 sec)

mysql> select * from book2;
+------+-------+---------+-------+
| id   | title | content | pages |
+------+-------+---------+-------+
|    1 | sun   | content |    10 |
+------+-------+---------+-------+
1 row in set (0.00 sec)

mysql> insert into book2 select * from book where id != 1;
Query OK, 4 rows affected (0.01 sec)
Records: 4  Duplicates: 0  Warnings: 0

mysql> select * from book2;
+------+--------+---------+-------+
| id   | title  | content | pages |
+------+--------+---------+-------+
|    1 | sun    | content |    10 |
|    2 | title1 | c       |     9 |
|    3 | t      | c       |    20 |
|    4 | title1 | NULL    |    15 |
|    5 | t      | NULL    |     3 |
+------+--------+---------+-------+
5 rows in set (0.00 sec)

mysql> insert into book2(title) select content from book where id != 1;
Query OK, 4 rows affected (0.00 sec)
Records: 4  Duplicates: 0  Warnings: 0

mysql> select * from book2;
+------+--------+---------+-------+
| id   | title  | content | pages |
+------+--------+---------+-------+
|    1 | sun    | content |    10 |
|    2 | title1 | c       |     9 |
|    3 | t      | c       |    20 |
|    4 | title1 | NULL    |    15 |
|    5 | t      | NULL    |     3 |
| NULL | c      | NULL    |  NULL |
| NULL | c      | NULL    |  NULL |
| NULL | NULL   | NULL    |  NULL |
| NULL | NULL   | NULL    |  NULL |
+------+--------+---------+-------+
9 rows in set (0.00 sec)

```

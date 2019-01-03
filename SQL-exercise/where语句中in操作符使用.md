## where语句中in操作符使用
- in 语法

```
select * from 表名 where 列名 in(value1,value2...)
select * from 表名 where 列名 in(select 列名 from 表名)
```
> **注解**： **列名 in(value1,value2...)等同 列名 = value1 or 列名 = value2...**

---
- 例子

```
mysql> select * from book;
+------+-----------+---------+-------+
| id   | title     | content | pages |
+------+-----------+---------+-------+
|    1 | sun       | content |    10 |
|    2 | title1    | c       |     9 |
|    3 | nice tree | bad day |    20 |
|    4 | title1    | NULL    |    15 |
|    5 | color     | NULL    |     3 |
+------+-----------+---------+-------+
5 rows in set (0.00 sec)

mysql> select * from book where title in ('sun','color');
+------+-------+---------+-------+
| id   | title | content | pages |
+------+-------+---------+-------+
|    1 | sun   | content |    10 |
|    5 | color | NULL    |     3 |
+------+-------+---------+-------+
2 rows in set (0.00 sec)

```

---
- 例2

```
mysql> select * from book;
+------+-----------+---------+-------+
| id   | title     | content | pages |
+------+-----------+---------+-------+
|    1 | sun       | content |    10 |
|    2 | title1    | c       |     9 |
|    3 | nice tree | bad day |    20 |
|    4 | title1    | NULL    |    15 |
|    5 | color     | NULL    |     3 |
+------+-----------+---------+-------+
5 rows in set (0.00 sec)

mysql> select * from book2;
+------+--------+---------+-------+
| id   | title  | content | pages |
+------+--------+---------+-------+
|    1 | sun    | content |    10 |
|    2 | title1 | c       |     9 |
|    3 | t      | c       |    20 |
|    4 | title1 | NULL    |    15 |
|    5 | color  | NULL    |     3 |
| NULL | c      | NULL    |  NULL |
| NULL | c      | NULL    |  NULL |
| NULL | NULL   | NULL    |  NULL |
| NULL | NULL   | NULL    |  NULL |
+------+--------+---------+-------+
9 rows in set (0.00 sec)

mysql> select * from book where title in (select title from book2 where id < 4);
+------+--------+---------+-------+
| id   | title  | content | pages |
+------+--------+---------+-------+
|    1 | sun    | content |    10 |
|    2 | title1 | c       |     9 |
|    4 | title1 | NULL    |    15 |
+------+--------+---------+-------+
3 rows in set (0.00 sec)

```

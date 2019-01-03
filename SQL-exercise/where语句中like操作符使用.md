## where语句中like操作符使用
- 语法：

```
select * from 表名 where 列名 [not] like pattern
```
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

mysql> select * from book where id like 1;
+------+-------+---------+-------+
| id   | title | content | pages |
+------+-------+---------+-------+
|    1 | sun   | content |    10 |
+------+-------+---------+-------+
1 row in set (0.00 sec)

mysql> select * from book where id like '1';
+------+-------+---------+-------+
| id   | title | content | pages |
+------+-------+---------+-------+
|    1 | sun   | content |    10 |
+------+-------+---------+-------+
1 row in set (0.01 sec)

mysql> select * from book where title like 't%';
+------+--------+---------+-------+
| id   | title  | content | pages |
+------+--------+---------+-------+
|    2 | title1 | c       |     9 |
|    4 | title1 | NULL    |    15 |
+------+--------+---------+-------+
2 rows in set (0.00 sec)

mysql> select * from book where title like '%or';
+------+-------+---------+-------+
| id   | title | content | pages |
+------+-------+---------+-------+
|    5 | color | NULL    |     3 |
+------+-------+---------+-------+
1 row in set (0.00 sec)

mysql> select * from book where title like '%or%';
+------+-------+---------+-------+
| id   | title | content | pages |
+------+-------+---------+-------+
|    5 | color | NULL    |     3 |
+------+-------+---------+-------+
1 row in set (0.00 sec)

mysql> select * from book where title not like '%or%';
+------+-----------+---------+-------+
| id   | title     | content | pages |
+------+-----------+---------+-------+
|    1 | sun       | content |    10 |
|    2 | title1    | c       |     9 |
|    3 | nice tree | bad day |    20 |
|    4 | title1    | NULL    |    15 |
+------+-----------+---------+-------+
4 rows in set (0.00 sec)


```

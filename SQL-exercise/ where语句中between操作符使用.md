##  where语句中between操作符使用
- 语法

```
select * from 表名 where  列名 between 值1 and 值2
select * from 表名 where  列名 not between 值1 and 值2
```

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

mysql> select * from book where id between 1 and 3;
+------+-----------+---------+-------+
| id   | title     | content | pages |
+------+-----------+---------+-------+
|    1 | sun       | content |    10 |
|    2 | title1    | c       |     9 |
|    3 | nice tree | bad day |    20 |
+------+-----------+---------+-------+
3 rows in set (0.00 sec)

mysql> select * from book where id not between 1 and 3;
+------+--------+---------+-------+
| id   | title  | content | pages |
+------+--------+---------+-------+
|    4 | title1 | NULL    |    15 |
|    5 | color  | NULL    |     3 |
+------+--------+---------+-------+
2 rows in set (0.00 sec)

```

## - 使用limit截取查询结果
- offset: 查询结果的起始位置，第一条记录的其实是0 
- rowCount: 从offset位置开始，获取的记录条数
```
select * from table_name[where子句][order by子句] limit [offset,] rowCount
```
> **注意** limit rowCount = limit 0,rowCount
- 例子

```
mysql> select * from book order by id limit 2,2;
+------+--------+---------+-------+
| id   | title  | content | pages |
+------+--------+---------+-------+
|    3 | t      | c       |    20 |
|    4 | title1 | NULL    |    15 |
+------+--------+---------+-------+
2 rows in set (0.01 sec)

#limit rowCount = limit 0,rowCount
mysql> select * from book order by id limit 2;
+------+--------+---------+-------+
| id   | title  | content | pages |
+------+--------+---------+-------+
|    1 | t hah  | content |    10 |
|    2 | title1 | c       |     9 |
+------+--------+---------+-------+
2 rows in set (0.00 sec)

```

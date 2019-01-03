
## 使用order by对查询结果排序
---

- 使用order by例子
```

mysql> select * from book where pages > 0 order by id asc;
+------+--------+---------+-------+
| id   | title  | content | pages |
+------+--------+---------+-------+
|    1 | t hah  | content |    10 |
|    2 | title1 | c       |     9 |
|    3 | t      | c       |    20 |
|    4 | title1 | NULL    |    15 |
|    5 | t      | NULL    |     3 |
+------+--------+---------+-------+
5 rows in set (0.00 sec)


mysql> select * from book where pages > 0 order by id desc;
+------+--------+---------+-------+
| id   | title  | content | pages |
+------+--------+---------+-------+
|    5 | t      | NULL    |     3 |
|    4 | title1 | NULL    |    15 |
|    3 | t      | c       |    20 |
|    2 | title1 | c       |     9 |
|    1 | t hah  | content |    10 |
+------+--------+---------+-------+
5 rows in set (0.00 sec)

mysql> select * from book where pages > 0 order by content desc , pages asc ;
+------+--------+---------+-------+
| id   | title  | content | pages |
+------+--------+---------+-------+
|    1 | t hah  | content |    10 |
|    2 | title1 | c       |     9 |
|    3 | t      | c       |    20 |
|    5 | t      | NULL    |     3 |
|    4 | title1 | NULL    |    15 |
+------+--------+---------+-------+
5 rows in set (0.00 sec)


```

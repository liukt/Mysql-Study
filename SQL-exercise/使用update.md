## - update

---
### - 语法格式
```
UPDATE 表名称 SET 列名称 = 新值（WHERE 列名称 = 某值）

```
- MySQL update替换字段部分内容

```
UPDATE 表名 SET 字段名 = REPLACE(替换前的字段值, '替换前关键字', '替换后关键字');
```



### - **注意** null的判断-is -is not
```
mysql> update book set id = 2 where id = null &&title=null;
Query OK, 0 rows affected (0.01 sec)
Rows matched: 0  Changed: 0  Warnings: 0

mysql> select * from book;
+------+--------+---------+-------+
| id   | title  | content | pages |
+------+--------+---------+-------+
|    1 | t hah  | content |    10 |
| NULL | NULL   | c       |     1 |
|    3 | t      | c       |     1 |
| NULL | title1 | NULL    |     1 |
| NULL | t      | NULL    |     1 |
+------+--------+---------+-------+
5 rows in set (0.00 sec)

mysql> update book set id = 2 where id is null &&title is null;
Query OK, 1 row affected (0.00 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> select * from book;
+------+--------+---------+-------+
| id   | title  | content | pages |
+------+--------+---------+-------+
|    1 | t hah  | content |    10 |
|    2 | NULL   | c       |     1 |
|    3 | t      | c       |     1 |
| NULL | title1 | NULL    |     1 |
| NULL | t      | NULL    |     1 |
+------+--------+---------+-------+
5 rows in set (0.00 sec)

```

- MySQL有三种主要数据类型:
1. 文本类
2. 数字类
3. 日期类
- 创建数据表table

---

```
CREATE TABLE account(
    id bigint(20),
    createTmie datetime,
    ip varchar(255),
    mobile varchar(255),
    nickname varchar(255),
    passwd varchar(255),
    username varchar(255),
    avatar varchar(255),
    brief text,
    job varchar(255),
    location varchar(255),
    qq varchar(255),
    gender int(11),
    city varchar(255),
    province varchar(255)
    );
    

    

```

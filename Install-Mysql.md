##以CentOS7为例 安装 Mysql

---
[安装教程](http://www.runoob.com/mysql/mysql-install.html)

- Mysql安装成功后，默认的root用户密码为空，你可以使用以下命令来创建root用户的密码：
```
[root@host]# mysqladmin -u root password "new_password";
```
- 现在你可以通过以下命令来修改root用户的密码：
```
[root@centos7 ~]# mysqladmin -u root -p password "root"

```
- 现在你可以通过以下命令来连接到Mysql服务器：
```
[root@host]# mysql -u root -p
Enter password:*******
```


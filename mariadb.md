注：同样适用于 MySQL。

```
DROP USER 'root'@'localhost';
CREATE USER 'root'@'%' IDENTIFIED BY 'Passw0rd';
SET PASSWORD FOR 'root'@'%' = PASSWORD('Passw0rd');
GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' WITH GRANT OPTION;
FLUSH PRIVILEGES;
```

其中，`%`可以按照需求换成`localhost`等。

如果你希望从外部访问你的数据库，请务必做好安全措施后，修改 `/etc/mysql/mysql.conf.d/mysqld.cnf` 文件中的 `bind-address` 一项。

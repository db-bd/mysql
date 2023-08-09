## MySQL 8.x User Create with ` mysql_native_password `
```sql
CREATE USER 'admin'@'localhost' IDENTIFIED WITH mysql_native_password BY 'Admin#12???';
GRANT ALL PRIVILEGES ON *.* TO 'admin'@'localhost';
FLUSH PRIVILEGES;
```

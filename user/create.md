## MySQL 8.0 User Create with ` mysql_native_password `
```sql
CREATE USER 'admin'@'localhost' IDENTIFIED WITH mysql_native_password BY 'nopass';
GRANT ALL PRIVILEGES ON *.* TO 'admin'@'localhost';
FLUSH PRIVILEGES;
```

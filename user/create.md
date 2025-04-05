## MySQL 8.x User Create with ` mysql_native_password `
```sql
CREATE USER 'admin'@'localhost' 
IDENTIFIED WITH caching_sha2_password 
BY 'nopass';

GRANT ALL PRIVILEGES ON *.* TO 'admin'@'localhost';

FLUSH PRIVILEGES;
```

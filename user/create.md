## MySQL User Create with ` caching_sha2_password `
```sql
CREATE USER 'admin'@'localhost' 
IDENTIFIED WITH caching_sha2_password 
BY 'nopass';

GRANT ALL PRIVILEGES ON *.* TO 'admin'@'localhost';

FLUSH PRIVILEGES;
```

## Access outside machine
```sql
create user 'admin'@'%' identified by 'nopass';
grant all privileges on *.* to 'admin'@'%' with grant option;
flush privileges;
```

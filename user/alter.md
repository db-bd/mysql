## Alter Update MySQL Database User
```sh
SHOW VARIABLES LIKE 'validate_password%';
SET GLOBAL validate_password.length = 6;
ALTER USER 'sample'@'localhost' IDENTIFIED BY 'testpassword';
```

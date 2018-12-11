## Dump Error 
```sh
mysqldump: Got error: 1449: The user specified as a definer ('root'@'%') does not exist when using LOCK TABLES
```
> Solution
```sh
 mysqldump --single-transaction -uroot -pnopass mydb > mydb.sql
 ```

## Duplicate MySQL DB
```sh
mysqldump -u amran --password=nopass mydb | mysql -u amran -p mydbnew
```

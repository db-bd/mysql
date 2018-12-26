#### MySQL Portable Install in Windows

* Download [dev.mysql.com](https://dev.mysql.com/downloads/mysql/) => Windows (x86, 64-bit) ZIP Archive
* Unzip Zip File. Suppose in ` C:/database/mysql ` Folder
* Make a Copy of ` my-default.ini ` to ` my.ini ` in current Directory
* Make a ` data ` directory in current Folder
* Add these lines in ` my.ini `
* If ` my.ini ` Not Found Then Create ` my.ini ` with Following Configs
```sh
 [mysqld]
 basedir = "C:/database/mysql"
 datadir = "C:/database/mysql/data"
 max_allowed_packet=100M
```
* OR
```sh
 [mysqld]
 basedir = "C:/Database/MySQL"
 datadir = "C:/Database/MySQL/data"
 max_allowed_packet=100M
 ```

* Navigate to ` C:/database/mysql/bin ` directory through two command prompt
* Run following commands step by step
```sh
 mysqld --initialize
 mysqld --initialize-secure
 mysqld --console
```

* Another command prompt run: ` mysql -h localhost -u root -p newpass `
* An error file will be generated in `data` directory say for example ` username.err `
* Find [Note] A temporary password is generated for ` root@localhost: q1;dusbRjkzJ `
* Connect By this Generated Password
* Executed Following Command to `mysql>` Command Prompt
```sql
 ALTER USER root@localhost IDENTIFIED BY 'newpass';
 ALTER USER root@localhost IDENTIFIED BY 'nopass';
```
* Now quit and reconnect: ` mysql -h localhost -u root -p newpass `
* Everything is working fine
* Mind it. First Start mysqld by 
```sh
 mysqld --console
```
* Or open cmd and type
```sh
mysqld
```

#### MySQL Portable Install in Linux

* Download [dev.mysql.com](https://dev.mysql.com/downloads/mysql/) => Linux - Generic (glibc 2.12) (x86, 64-bit), Compressed TAR Archive

* Search Following ` mysql ` server runtime dependencies
```sh
yum search libaio       [centos]
apt-cache search libaio [ubuntu]
```

* Following packages may be found
```sh
libaio-dev - Linux kernel AIO access library - development files
libaio1 - Linux kernel AIO access library - shared library
```

* Install dependent package
```sh
yum install libaio # install library      [centos]
apt-get install libaio1 # install library [ubuntu] 
``` 

* Extract TAR File. Suppose in ` /opt/mysql ` Folder by following command
```sh
tar xvf mysql-xxx-linux-glibc2.xxx-x86_64.tar.xz 
```

* Create ` my.ini ` file in current directory
* Make a ` data ` directory in current directory
* Add these lines in ` my.ini `
```sh
 [mysqld]
 basedir = "/opt/mysql"
 datadir = "/opt/mysql/data"
 max_allowed_packet=100M
```
* Add ` /bin ` directory to ` .bash_aliases ` or ` .bashrc `
```sh
# MySQL
export PATH="$PATH:/opt/mysql/bin"
```
* Navigate to ` /opt/mysql/bin ` directory through two terminal prompt
* Run following commands step by step
```sh
 mysqld --initialize
 mysqld --initialize-secure [Optional: May Not Work In Linux]
 mysqld --console
```

* ` mysqld --initialize ` will generate following message with a ` Temporary Password ` for ` root ` user
```sh
2018-11-06T06:52:52.985133Z 0 [System] [MY-013169] [Server] /opt/mysql/bin/mysqld (mysqld 8.0.13) initializing of server in progress as process 25696
2018-11-06T06:52:54.938988Z 5 [Note] [MY-010454] [Server] A temporary password is generated for root@localhost: ig=gVyd-I4ZH
2018-11-06T06:52:56.133156Z 0 [System] [MY-013170] [Server] /opt/mysql/bin/mysqld (mysqld 8.0.13) initializing of server has completed
```
* MySQL Demon will be running through ` mysqld --console ` command
* From another terminal connect to mysql: ` mysql -u root -p generated_password `

* Executed Following Command to `mysql>` Command Prompt
```sql
 ALTER USER root@localhost IDENTIFIED BY 'nopass'
```
* Now quit and reconnect: ` mysql -u root -p nopass `
* Everything is working fine

* Mind it. First Start mysqld by for starting server
```sh
 mysqld --console
```
* Or open cmd and type
```sh
mysqld
```

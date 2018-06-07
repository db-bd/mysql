## [Change MySQL Root Password](https://support.rackspace.com/how-to/mysql-resetting-a-lost-mysql-root-password/)

```sh
sudo service mysql stop
sudo mysqld_safe --skip-grant-tables &
mysql -uroot

use mysql;
update user set password=PASSWORD("nopass") where User='root';
flush privileges;
quit

sudo service mysql stop
sudo service mysql start
```

## MySQL Remote Login
```sh
sudo apt-get update
sudo apt-get install mysql-server
sudo mysql_secure_installation

Uncomment: # bind-address		= 127.0.0.1

sudo service mysql restart

GRANT ALL PRIVILEGES ON *.* TO 'root'@'192.168.244.101' IDENTIFIED BY 'nopass' WITH GRANT OPTION;
GRANT ALL PRIVILEGES ON *.* TO 'root'@'192.168.0.105' IDENTIFIED BY 'nopass' WITH GRANT OPTION;

FLUSH PRIVILEGES;
```

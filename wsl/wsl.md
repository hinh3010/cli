# sudo apt update && apt upgrade

# redis
- sudo apt install redis-server -y
- redis-server
- sudo service redis-server stop
- sudo service redis-server start

# apache
- sudo apt install apache2 -y
- sudo service apache2 start
- sudo service apache2 status
- sudo service apache2 stop

# mysql server
- sudo apt install mysql-server -y
- sudo service mysql start
- sudo service mysql status
- sudo service mysql stop
- config : sudo nano /etc/apache2/mods-enabled/dir.conf
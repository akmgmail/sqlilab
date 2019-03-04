# sqlilab for Kali 4.19.0-kali3

 Install Instructions:
 ---------------------
 
Download the Lab Setup and unzip it or you can directly git clone it by the following command:

git clone https://github.com/akmgmail/sqlilab

Unzip the lab by the following command

unzip sqlilabs.zip

Now copy the sqlilab directory to apache folder through the following command

cp -R sqlilab /var/www/html/

Now we need to do some changes in MySQL to do this follow the following steps:

start the mysql service by following command:

service mysql start

Login to mysql using the following command:

mysql -u root -p

Enter you root password of mysql.

now at Mysql prompt type the following command:

use mysql;

Now we will create a user it give it all permissions through the following command:

#grant all privileges on *.* to 'hacker'@'localhost' identified by 'hacker';

Type ctrl+c to exit from mysql

Now we need to make modification in db-creds.inc, we need to change the $dbuser='hacker' and $dbpass'hacker'. To do this type the following command:

vi /var/www/html/sqlilab/sql-connections/db-creds.inc

Now the file will look like:
<?php

//give your mysql connection username n password
$dbuser ='hacker';
$dbpass ='hacker';
$dbname ="security";
$host = 'localhost';
$dbname1 = "challenges";

?>

Now you need to restart the MySQL service and apache2 Service by the following command:

service mysql restart

service apache2 restart

Now on the browser type http://localhost/sqlilab

Click on the link setup/resetDB to create database, create tables and populate Data.

Labs ready to be used, click on lesson number to open the lesson page.

Enjoy the labs

For any Queries mail me at ashokkumarmohanty@gmail.com

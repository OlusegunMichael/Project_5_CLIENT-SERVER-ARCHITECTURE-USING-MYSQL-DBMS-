# Project 5 - Implemetation of Client-Server Architecture using MYSQL (DBMS)
___
___

### **Step 1 - Setting up the 2 Ubuntu Servers using the EC2 Instance, Updating and ugrading the apt packages**
___
>#### EC2 instance Up and Running
![EC2 Instance Up and Running](./Project5%20Images/EC2%20Instance.PNG)

___
>#### Updating and ugrading the Ubuntu’s package manager ‘apt’

#####  To update a list of packages in package manager *`sudo apt update`* & *`sudo apt upgrade`* command is used and below images shows the status of the running update.
![sudo apt](./Project5%20Images/sudo%20update.PNG)
![sudo apt](./Project5%20Images/sudo%20update1.PNG)
![sudo apt](./Project5%20Images/sudo%20upgrade.PNG)
![sudo apt](./Project5%20Images/sudo%20upgrade1.PNG)
### **Step 2 INSTALLING & SETTING UP MYSQL (SERVER)**
___

>#### Acquiring & Installing mysql server  using ‘apt’
#####  To install the mysql *`sudo apt install mysql-server`* & to check the status of the server *`sudo systemctl status mysql.service`* command is used and below images shows the status of the running update.

![mysqlserver](./Project5%20Images/msql%20server%20install.PNG)
![mysqlserver](./Project5%20Images/msql%20server%20install1.PNG)

>#### Accessing and setting up the Server Mysql Database
#### The following set command were used to logon and create the test Database and access configured to it, so the client would be able to query data from the Server DB and display it.

* *`sudo mysql`* - (Connects to mysql)
* *`CREATE DATABASE `Project5_Database`;`* - (Creates a New Database)
* *`CREATE USER 'Olusegun'@'%' IDENTIFIED WITH mysql_native_password BY 'Pass123';`* - ( create a new user and grants full privileges on the database)
* *`GRANT ALL ON Project5_Database.* TO 'Olusegun'@'%';`* - (Give the user permission over the specified database)
* *`SHOW DATABASES`* - (Displays the Database Table)
* *`CREATE TABLE Project5_Database.name_list (item_id INT AUTO_INCREMENT,content VARCHAR(255),PRIMARY KEY(item_id));`* - (Create a test table named name_list.)
* *`INSERT INTO Project5_Database.name_list (content) VALUES ("Input desired Values");`* (Inserts Rows in the Test table)
* *`SELECT * FROM Project5_Database.name_list;`* (Displays the Test table)
![mysql](./Project5%20Images/sudo%20mysql.PNG)
![mysql](./Project5%20Images/sudo%20mysql1.PNG)
![mysql](./Project5%20Images/sudo%20mysql2.PNG)

### **Step 2 INSTALLING MYSQL (CLIENT) & SETTING UP THE SERVER TO ALLOW REMOTE CONNECTION**
___

>####  To install the mysql *`sudo apt install mysql-client`* .

![mysqlclient](./Project5%20Images/mysqlclient.PNG)

>####  Configuring MySQL server to allow connections from remote hosts.
#### MySQL server uses TCP port 3306 by default remote connection and it set as part of the Inbound Rules in the Security Group of the EC2 Instance. Also the command *`sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf`;`* is used to edit the bind address to 0.0.0.0
![rules](./Project5%20Images/3306.PNG)
![bind](./Project5%20Images/bind%20add.PNG)

>####  Connect from mysql Client to myqsl Server.

From mysql Client Linux Server mysql utility*`mysql -u db_user -h 172.31.5.218 -p`* is used to connect remotely to mysql server Database Engine.

![client_server](./Project5%20Images/connect.PNG)

### Project Ends

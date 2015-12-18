
yum install mysql mysql-server -y

chkconfig mysqld on

vim /etc/my.cnf

#####my.cnf content

>[mysqld]

>log-bin=mysql-bin

>server-id=1

service mysqld start

mysql_secure_installation

#####mysql internal command start

>CREATE USER 'repl' IDENTIFIED BY 'slavepass'; #Create user for slave

>GRANT REPLICATION SLAVE ON *.* TO 'repl'; 

>FLUSH TABLES WITH READ LOCK;

>SHOW MASTER STATUS;

> `waitiing slave`

>UNLOCK TABLES; `unlock if slave done`


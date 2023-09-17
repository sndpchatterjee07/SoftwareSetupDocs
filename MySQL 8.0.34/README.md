#  MySQL Server 8.0.34 Installation Notes on Ubuntu 22.04.1

1. To ensure the apt libraries are up-to-date:

   `sudo apt update && sudo apt upgrade -y`


2. Install MySQL Server

   `sudo apt-get install mysql-server -y`


3. To check the version of MySQL server running

   `mysql -V`


   **Output:**
   
   `mysql  Ver 8.0.34-0ubuntu0.22.04.1 for Linux on x86_64 ((Ubuntu))`
   

4. To verify if the MySQL service is activated or not:

	`systemctl is-active mysql`
    
    
   **Output:**
   
   `active`
   
   

5. To Improve MySQL Installation Security by setting a password for root accounts & remove anonymous-user accounts

   `sudo mysql_secure_installation`	
	
	
   **Output:**
   
  ```
  [sudo] password for sandeep: 

  Securing the MySQL server deployment.

  Connecting to MySQL using a blank password.

  VALIDATE PASSWORD COMPONENT can be used to test passwords
  and improve security. It checks the strength of password
  and allows the users to set only those passwords which are
  secure enough. Would you like to setup VALIDATE PASSWORD component?

  Press y|Y for Yes, any other key for No: y

  There are three levels of password validation policy:

  LOW    Length >= 8
  MEDIUM Length >= 8, numeric, mixed case, and special characters
  STRONG Length >= 8, numeric, mixed case, special characters and dictionary                  file

  Please enter 0 = LOW, 1 = MEDIUM and 2 = STRONG: 2

  Skipping password set for root as authentication with auth_socket is used by default.
  If you would like to use password authentication instead, this can be done with the "ALTER_USER" command.
  See https://dev.mysql.com/doc/refman/8.0/en/alter-user.html#alter-user-password-management for more information.

  By default, a MySQL installation has an anonymous user,
  allowing anyone to log into MySQL without having to have
  a user account created for them. This is intended only for
  testing, and to make the installation go a bit smoother.
  You should remove them before moving into a production
  environment.

  Remove anonymous users? (Press y|Y for Yes, any other key for No) : n

   ... skipping.


  Normally, root should only be allowed to connect from
  'localhost'. This ensures that someone cannot guess at
  the root password from the network.

  Disallow root login remotely? (Press y|Y for Yes, any other key for No) : n

   ... skipping.
  By default, MySQL comes with a database named 'test' that
  anyone can access. This is also intended only for testing,
  and should be removed before moving into a production
  environment.


  Remove test database and access to it? (Press y|Y for Yes, any other key for No) : n

   ... skipping.
  Reloading the privilege tables will ensure that all changes
  made so far will take effect immediately.

  Reload privilege tables now? (Press y|Y for Yes, any other key for No) : y
  Success.

  All done! 

  ```
 
 
   
   
   

6. To Install MySQL Workbench   

  	`sudo snap install mysql-workbench-community`
    
    
   **Output:**
   
   
   `mysql-workbench-community 8.0.32 from Tonin Bolzan (tonybolzan) installed`
   
   
   
   
7. To set the root user to use the `mysql_native_password plugin`
   
   
     sudo mysql -u root
     mysql> USE mysql;
     mysql> UPDATE user SET plugin='mysql_native_password' WHERE User='root';
     mysql> FLUSH PRIVILEGES;
     mysql> exit;
     sudo service mysql restart



8. Login to MySQL as `root`

	`mysql -u root`
	
   
   
   
9. Create a new `db_user` with you `system_user`

   ``` 
   sudo mysql -u root
   mysql> USE mysql;
   mysql> CREATE USER 'YOUR_SYSTEM_USER'@'localhost' IDENTIFIED BY 'YOUR_PASSWD';
   mysql> GRANT ALL PRIVILEGES ON *.* TO 'YOUR_SYSTEM_USER'@'localhost';
   mysql> UPDATE user SET plugin='auth_socket' WHERE User='YOUR_SYSTEM_USER';
   mysql> FLUSH PRIVILEGES;
   mysql> exit;
   sudo service mysql restart
   ```



   
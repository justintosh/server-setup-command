# server-setup-command
Comment server setup commands for Ubuntu and CentOS

# Install MySQL

For Ubuntu

1. Install mysql-server.

  ```
    $ sudo apt install mysql-server
  ```

2. Start mysql server.

  ```
    $ sudo systemctl start mysql
  ```
  
3. Check mysql status.

  ```
    $ systemctl status mysql
  ```
  
4. Set mysql auto start on server startup.

  ```
    $ sudo systemctl enable mysql
  ```
  
5. Set root password.

  ```
    $ sudo secure_mysql_installation
  ```

6. If the previous step does not work and you still can't login with the new root password, do this:
  
  ```
    $ sudo mysqlGRANT ALL PRIVILEGES ON *.* TO 'xxx'@'localhost' WITH GRANT OPTION;
    mysql> ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
    mysql> FLUSH PRIVILEGES;
  ```
  
7. Create new user.

  ```
    mysql> CREATE USER 'xxx'@'localhost' IDENTIFIED BY 'password';
    mysql> GRANT ALL PRIVILEGES ON *.* TO 'xxx'@'localhost' WITH GRANT OPTION;
  ```



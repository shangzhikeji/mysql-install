# mysql-install
how-to-install-mysql-on-linux

###Quick setup: Copy and Paste

```
root@linuxserver:~# sudo apt update && sudo apt install mysql-server
root@linuxserver:~# sudo service mysql status
root@linuxserver:~# sudo mysql_secure_installation
//You will be asked if you want to set up the Validate Password Plugin. Press ENTER.
Please set the password for root here.
New password:
Re-enter new password:
//You will be asked if you want to remvoe anonymous users? Press Yes.
Remove anonymous users? (Press y|Y for Yes, any other key for No) :
//You will be asked if you want to disallow root login remotely? Press No.
Disallow root login remotely? (Press y|Y for Yes, any other key for No) :
//You will be asked if you want to remove the test database? Press Yes.
Remove test database and access to it? (Press y|Y for Yes, any other key for No) :
//You will be asked if you want to reload privilege tables? Press Yes.
Reload privilege tables now? (Press y|Y for Yes, any other key for No) :

```

###Complete setup

Install the mysql-server package:

```
//On Debian/Ubuntu operating systems
root@linuxserver:~# sudo apt update && sudo apt install mysql-server

```
Press y and ENTER when prompted to install the MySQL package.
Once the package installer has finished, we can check to see if the MySQL service is running.

```
root@linuxserver:~# sudo service mysql status
```
If running, you will see a green Active status like below.
```
● mysql.service - MySQL Community Server
Loaded: loaded (/lib/systemd/system/mysql.service; enabled; vendor preset: enabled)
Active: active (running) since Mon 2018-04-02 02:40:59 CEST; 2min 47s ago
Main PID: 18476 (mysqld)
Tasks: 27 (limit: 4915)
CGroup: /system.slice/mysql.service
└─18476 /usr/sbin/mysqld --daemonize --pid-file=/run/mysqld/mysqld.pid

Apr 02 02:40:59 ubuntu1804 systemd[1]: Starting MySQL Community Server...
Apr 02 02:40:59 ubuntu1804 systemd[1]: Started MySQL Community Server.
```
You may need to press q to exit the service status.

Configure MySQL Security
You should now run mysql_secure_installation to configure security for your MySQL server.
```
root@linuxserver:~# sudo mysql_secure_installation
```
If you created a root password in Step 1, you may be prompted to enter it here. Otherwise you will be asked to create one.

You will be asked if you want to set up the Validate Password Plugin. It’s not really necessary unless you want to enforce strict password policies for some reason.
```
Securing the MySQL server deployment.

Connecting to MySQL using a blank password.

VALIDATE PASSWORD PLUGIN can be used to test passwords
and improve security. It checks the strength of password
and allows the users to set only those passwords which are
secure enough. Would you like to setup VALIDATE PASSWORD plugin?

Press y|Y for Yes, any other key for No:
```

Press ENTER here if you don’t want to set up the validate password plugin.
```
Please set the password for root here.

New password:

Re-enter new password:
```
If you didn’t create a root password in Step 1, you must now create one here.

Generate a strong password and enter it. Note that when you enter passwords in Linux, nothing will show as you are typing (no stars or dots).
```
By default, a MySQL installation has an anonymous user,
allowing anyone to log into MySQL without having to have
a user account created for them. This is intended only for
testing, and to make the installation go a bit smoother.
You should remove them before moving into a production
environment.

Remove anonymous users? (Press y|Y for Yes, any other key for No) :
```
Press y and ENTER to remove anonymous users.

```
Normally, root should only be allowed to connect from
'localhost'. This ensures that someone cannot guess at
the root password from the network.

Disallow root login remotely? (Press y|Y for Yes, any other key for No) :
```
Press y and ENTER to disallow root login remotely. This will prevent bots and hackers from trying to guess the root password.


```
By default, MySQL comes with a database named 'test' that
anyone can access. This is also intended only for testing,
and should be removed before moving into a production
environment.

Remove test database and access to it? (Press y|Y for Yes, any other key for No) :
```
Press y and ENTER to remove the test database.

```
Reloading the privilege tables will ensure that all changes
made so far will take effect immediately.

Reload privilege tables now? (Press y|Y for Yes, any other key for No) :
```
Press y and ENTER to reload the privilege tables.

All done!

As a test, you can log into the MySQL server and run the version command.
```
sudo mysqladmin -p -u root version
```
Enter the MySQL root password you created earlier and you should see the following:
```
mysqladmin Ver 8.42 Distrib 5.7.21, for Linux on x86_64
Copyright (c) 2000, 2018, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Server version 5.7.21-1ubuntu1
Protocol version 10
Connection Localhost via UNIX socket
UNIX socket /var/run/mysqld/mysqld.sock
Uptime: 2 hours 34 min 19 sec

Threads: 1 Questions: 15 Slow queries: 0 Opens: 113 Flush tables: 1 Open tables: 106 Queries per second avg: 0.001
```
You have now successfully installed and configured MySQL!

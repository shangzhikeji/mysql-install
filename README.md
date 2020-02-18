# mysql-install
how-to-install-mysql-on-linux

Quick setup: Copy and Paste

```
root@linuxserver:~# sudo apt update && sudo apt install mysql-server
root@linuxserver:~# sudo apt install mysql-server
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

Before You Begin:

```
# sudo apt update && sudo apt upgrade
```

```
# sudo apt install mysql-server
```

Press y and ENTER when prompted to install the MySQL package.

Once the package installer has finished, we can check to see if the MySQL service is running.

```
sudo service mysql status
```

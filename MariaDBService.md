The most common open source RDBMS servers right now are probably MySQL and PostgreSQL.  I was going to go with MySQL, but I saw
this article about MariaDB: https://howtoraspberrypi.com/mariadb-raspbian-raspberry-pi/ and it sounds like a superior alternative
to MySQL.  It is actually a branch of MySQL, so there should be no compatibility worries and the availability of client software
and configuration tools seems assured.

The link above outlines installation, which went as follows:

```shell
sudo apt-get update
sudo apt-get install mariadb-server
```

MariaDB is now installed, running (as service mysql) and ready for configuration and operation.

To check:

```shell
service mysql status
```

```shell
mysql -u pi -p
(permission denied error)
```

```shell
sudo mysql
(apparently connected as DBA, can create/enable users, create databases, grant roles and privileges)
MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
+--------------------+
3 rows in set (0.001 sec)

MariaDB [(none)]>
```

### A command and output that shows the hostname of your database server

```
hostname -A
```

output (This shows the internal ip address of the master host):

```
ip-172-31-1-145.eu-west-1.compute.internal
```

### A command and output that reports the database server version

```
mysql -e "SELECT VERSION();"
```

output:

```
+----------------+
| VERSION()      |
+----------------+
| 5.5.57-MariaDB |
+----------------+
```

### A command and output that lists all the databases in the server

```
mysql -u root -e "SHOW DATABASES;" -p
```

output:

```
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hive               |
| hue                |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
+--------------------+
```
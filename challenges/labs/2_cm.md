### List the command and output for ls /etc/yum.repos.d

```
ls /etc/yum.repos.d
```

output:

```
CentOS-Base.repo  CentOS-CR.repo  CentOS-Debuginfo.repo  CentOS-fasttrack.repo  CentOS-Sources.repo  CentOS-Vault.repo  cloudera-manager.repo  MariaDB.repo  mysql-community.repo  mysql-community-source.repo
```

### Connect Cloudera Manager Server to its database

```
sudo /usr/share/cmf/schema/scm_prepare_database.sh mysql -h ip-172-31-1-145.eu-west-1.compute.internal --scm-host $(hostname -f) scm scm scm123
```

output:

```
JAVA_HOME=/usr/lib/jvm/jre-openjdk
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/lib/jvm/jre-openjdk/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Successfully connected to database.
All done, your SCM database is configured correctly!
```

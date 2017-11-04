* Connect Cloudera Manager Server to its database
* Use the `scm_prepare_database.sh` script to create the `db.properties` file 
```bash
[root@stf-btc-challenge-2 ~]# /usr/share/cmf/schema/scm_prepare_database.sh mysql --host stf-btc-challenge-1.gce.cloudera.com --scm-host stf-btc-challenge-2.gce.cloudera.com scm scm scm_password
JAVA_HOME=/usr/java/jdk1.8.0_131
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.8.0_131/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
2017-11-03 13:38:18,998 [main] INFO  com.cloudera.enterprise.dbutil.DbCommandExecutor  - Successfully connected to database.
All done, your SCM database is configured correctly!
```

* Copy your `db.properties` content to the same file
```bash
[root@stf-btc-challenge-2 ~]# cat /etc/cloudera-scm-server/db.properties
# Auto-generated by scm_prepare_database.sh on Fri Nov  3 13:38:18 PDT 2017
#
# For information describing how to configure the Cloudera Manager Server
# to connect to databases, see the "Cloudera Manager Installation Guide."
#
com.cloudera.cmf.db.type=mysql
com.cloudera.cmf.db.host=stf-btc-challenge-1.gce.cloudera.com
com.cloudera.cmf.db.name=scm
com.cloudera.cmf.db.user=scm
com.cloudera.cmf.db.setupType=EXTERNAL
com.cloudera.cmf.db.password=scm_password
```

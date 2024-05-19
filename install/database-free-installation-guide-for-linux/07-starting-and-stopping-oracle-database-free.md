# 7 Starting and Stopping Oracle Database Free

## Shut Down and Start-Up Using SQL*Plus

- To shut down the database:

```shell
$ sqlplus / as sysdba
SQL> SHUTDOWN IMMEDIATE
```

- To start the database:

```shell
SQL> STARTUP
SQL> ALTER PLUGGABLE DATABASE ALL OPEN;
```

## Shutting Down and Starting Up Using the Configuration Services Script

- After you configure the listener, you can run the Configuration Services Script to check the status of the database and listener.

```shell
# /etc/init.d/oracle-free-23ai status
```

- To start the listener and the database:

```shell
# systemctl start oracle-free-23ai
```

- To stop the database and the listener:

```shell
# systemctl stop oracle-free-23ai
```

- To stop and start the listener and the database:

```shell
# systemctl restart oracle-free-23ai
```

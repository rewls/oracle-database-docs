# 6 Connecting to Oracle Database Free

## Connecting Locally using OS Authentication

- When you install Oracle Database Free, the oracle user is granted SYSDBA privileges.

- You can use the following commands to connect to the database.

```shell
$ sqlplus / as sysdba
```

- These commands connect you to the root container CDB$ROOT of the multitenant database (CDB) as database user SYS.

- This method of connecting to the database works even if the Net Services listener is not running.

## Net Services Listener and Default Services

- The Net Services database listener for Oracle Database Free allows you to connect to the database over TCP/IP from the same machine or other machines on the network.

- The configuration of the Listener can be viewed using the following commands run from the command prompt:

    ```shell
    $ lsnrctl status
    ```

- The output from the lsnrctl command shows values of a number of important parameters:

    - the port the listener listens on

    - the list of services registered with the listener

    - the name of the configuration file used by the listener

    - the name of the log file

- You must specify a service when connecting to the database through the listener. 
- The default services created by Oracle Database Free are FREE and FREEPDB1. 

- The Oracle Database Free service connects you to the root container of the database (CDB$ROOT) and the FREEPDB1 service connects you to the default pluggable database FREEPDB1, created during installation. 

- For each new pluggable database (PDB), there is a new default service created with the same name as the PDB.

> ##### Note
>
> - If you shut down the Oracle Database Free instance, then the lsnrctl status command does not show any services that you can connect to.

## Connecting to Oracle Database Using Easy Connect Naming Method

- You can connect to the database using the following Easy Connect strings:

    - Multitenant container database: host[:port]

    - Pluggable database: host[:port]/service_name

- You must specify the port number if you use another port.

- The Net Services database listener must be running on the database host of the specified port for the connections to succeed.

- For example, you can connect to the root container of the database from a client computer with SQL*Plus using the following commands:

```sh
$ cd $ORACLE_HOME/bin
$ ./sqlplus system@dbhost.example.com:1521
```

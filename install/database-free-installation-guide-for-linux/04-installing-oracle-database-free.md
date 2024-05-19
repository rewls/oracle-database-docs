# 4 Installing Oracle Database Free

- You can install Oracle Database Free using RPM packages.

## Installing Oracle Database Free Using RPM Packages

### Installing Oracle Database Free RPM

3. Access the Oracle Database Free software download page:

    - https://www.oracle.com/database/technologies/free-downloads.html

4. Pull container images straight from Oracle’s Container Registry via:

    ```shell
    docker pull container-registry.oracle.com/database/free:latest
    ```

### Creating and Configuring an Oracle Database

- The configuration script creates a container database (FREE) with one pluggable database (FREEPDB1) and configures the listener at the default port (1521).

- You can modify the configuration parameters by editing the /etc/sysconfig/oracle-free–23ai.conf file.

- To create the database with the default settings:

    1. Log in as root using sudo.

        ```shell
        sudo -s
        ```

    2. Run the service configuration script:

        ```shell
        /etc/init.d/oracle-free-23ai configure
        ```

- At the command prompt, specify a password for the SYS, SYSTEM, and PDBADMIN administrative user accounts.

- Oracle recommends that your password should be at least 8 characters in length, contain at least 1 upper case character, 1 lower case character and, 1 digit [0-9].

- The same password will be used for these accounts.

- After the configuration completes, the database and listener are started.

## Setting Oracle Database Free Environment Variables

- After you install and configure Oracle Database Free, set the environment before you use Oracle Database Free.

- Use the oraenv and coraenv scripts to set your environment variables.

```shell
. /opt/oracle/product/23ai/dbhomeFree/bin/oraenv
```

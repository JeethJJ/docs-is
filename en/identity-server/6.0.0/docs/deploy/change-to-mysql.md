# Change to MySQL

By default, WSO2 Identity Server uses the embedded H2 database as the database
for storing user management and registry data. Given below are the steps
you need to follow in order to use MySQL for this purpose. 

!!! note
    If you are using MySQL version 8.0 or later, make sure that you 
    create the database with charset latin1 as shown in the example below:

    ```
    create database <db_name> character set latin1;
    ```
---

## Datasource configurations

{!./includes/datasource-config.md !}
                       
After setting up the MySQL database. You can point the `WSO2_IDENTITY_DB` or 
`WSO2_SHARED_DB` or both to that MySQL database by following the instructions given below.

---

## Change the default datasource

### Minimum configurations for changing default datasource to MySQL
 
You can configure the datasource by editing the default configurations in `<IS-HOME>/repository/conf/deployment.toml`. 

Following are the basic configurations and their descriptions. 

{!./includes/db-basic-config.md !}  
 
A sample configuration is given below.

1. `WSO2_IDENTITY_DB` 

    1. Configure the`deployment.toml` file.

        ``` toml
        [database.identity_db]
        type = "mysql"
        hostname = "localhost"
        name = "regdb"
        username = "regadmin"
        password = "regadmin"
        port = "3306"
        ```
    
    1. Execute database scripts.
    
        Navigate to `<IS-HOME>/dbscripts`. Execute the scripts in the following files, against the database created.
        
        - `<IS-HOME>/dbscripts/identity/mysql.sql`
        - `<IS-HOME>/dbscripts/identity/uma/mysql.sql`
        - `<IS-HOME>/dbscripts/consent/mysql.sql`
        
2. `WSO2_SHARED_DB`
    
    1.  Configure the `deployment.toml` file. 

        ``` toml
        [database.shared_db]
        type = "mysql"
        hostname = "localhost"
        name = "regdb"
        username = "regadmin"
        password = "regadmin"
        port = "3306"
        ```
        
    1.  Execute database scripts.
    
        Execute the scripts in the `<IS-HOME>/dbscripts/mysql.sql` file against the database created.
                         
!!! note     
    Instead of defining `hostname`, `port`, and `name` separately, you can define the `url`
    of the database in the following format.
                
    ``` toml
    type = "mysql"
    url = "jdbc:mysql://localhost:3306/regdb"
    username = "regadmin"
    password = "regadmin"
    ```  
            
        
3. If you have a requirement in using workflow feature follow, 
    [Change the default database of BPS database]({{base_path}}/deploy/change-datasource-bpsds)
    
4.  Download the MySQL JDBC driver for the version you are using. Extract the downloaded file and copy all required JAR files from the driver package to the `<IS_HOME>/repository/components/lib` folder.

    
           
---

### Advanced database configurations

{!./includes/db-advanced-config.md !}

{!./includes/db-config-table.md !}


---
  
## Configure the connection pool behavior on return 

{!./includes/connection-pool-behavior.md !}

### Configure the connection pool to commit pending transactions on connection return
        
{!./includes/commit-pending.md !}

### Configure the connection pool to rollback pending transactions on connection return

{!./includes/rollback-pending.md !}

## Driver-Level Timeouts (Recommended for Production)

{!./includes/driver-level-timeouts.md !}

### Example: MySQL database

```toml
[database.identity_db]
url = "jdbc:mysql://DB_HOST:3306/WSO2_IDENTITY_DB?connectTimeout=10000&socketTimeout=60000&tcpKeepAlive=true"
username = "..."
password = "..."
driver = "com.mysql.cj.jdbc.Driver"
```

Learn more in [MySQL Connector/J properties](https://docs.oracle.com/cd/E19509-01/820-3497/agqju/index.html){: target="_blank"}.

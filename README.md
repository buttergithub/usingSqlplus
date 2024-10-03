# usingSqlplus
This provides a detailed explanation of the commands executed using SQL*Plus connected to an Oracle Database 21c instance. The process involves creating, managing, and deleting pluggable databases (PDBs), configuring HTTP/HTTPS ports, and starting/stopping the Oracle instance.
##Command Breakdown
#Connect to Oracle Database 
```sql
C:\Users\Sandra>sqlplus sys as SYSDBA    --Connecting to oracle database as sysdba
```
## Display
```sql
SQL> show pdbs;               --Display Existing Pluggable Databases
```
## Creating a New Pluggable Database plsql_class2024db
```sql
CREATE PLUGGABLE DATABASE plsql_class2024db
ADMIN USER sa_plsqlauca IDENTIFIED BY password
FILE_NAME_CONVERT =
('D:\app\Sandra\oradata\ORCL\pdbseed','D:\app\Sandra\oradata\ORCL\orclpdb\sa_plsqlauca');
```
## Creating Another Pluggable Database sa_to_delete_pdb
```sql
CREATE PLUGGABLE DATABASE sa_to_delete_pdb
ADMIN USER sa_delplsqlauca IDENTIFIED BY password
FILE_NAME_CONVERT =
('D:\app\Sandra\oradata\ORCL\pdbseed','D:\app\Sandra\oradata\ORCL\orclpdb\sa_delplsqlauca');
```
## Open mode of all containers
```sql
SQL> select name, open_mode from v$containers;
```
## Drop the sa_to_delete_pdb Pluggable Database
```sql
DROP PLUGGABLE DATABASE sa_TO_DELETE_PDB INCLUDING DATAFILES;
```
## Set HTTP and HTTPS Ports for Oracle Database
```sql
BEGIN
DBMS_XDB_CONFIG.SETHTTPPORT(8083);
DBMS_XDB_CONFIG.SETHTTPSPORT(8443);
END;
```
## Checking the Configured Ports
```sql
SELECT DBMS_XDB_CONFIG.GETHTTPPORT() AS HTTP_PORT,
       DBMS_XDB_CONFIG.GETHTTPSPORT() AS HTTPS_PORT
FROM dual;
```
## Shutdown the Database
```sql
SQL> SHUTDOWN IMMEDIATE;
```
## Restarting the DB
```sql
SQL> STARTUP;
```
### License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT). You can freely use, copy, modify, and distribute this software, but please include a copy of this license in any distributions.





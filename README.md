# usingSqlplus
This provides a detailed explanation of the commands executed using SQL*Plus connected to an Oracle Database 21c instance. The process involves creating, managing, and deleting pluggable databases (PDBs), configuring HTTP/HTTPS ports, and starting/stopping the Oracle instance.
##Command Breakdown
#Connect to Oracle Database 
```sql
C:\Users\Sandra>sqlplus sys as SYSDBA    --Connecting to oracle database as sysdba
```
##Display
```sql
SQL> show pdbs;               --Display Existing Pluggable Databases
```
#Create a New Pluggable Database plsql_class2024db
```sql
CREATE PLUGGABLE DATABASE plsql_class2024db
ADMIN USER sa_plsqlauca IDENTIFIED BY password
FILE_NAME_CONVERT =
('D:\app\Sandra\oradata\ORCL\pdbseed','D:\app\Sandra\oradata\ORCL\orclpdb\sa_plsqlauca');
```

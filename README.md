## Pluggable Database Work
###Task 1: 
#### I created a Pluggable Database (PDB) named plsql_class2024db. My username follows the required format, starting with the first two letters of my name, so it is no_plsqlauca.
I used "noble" as my password. This user will be utilized for class activities where I will store all my work during the course.

##### Creating a Pluggable Database (PDB) named plsql_class2024db

```sql

SQL> CREATE PLUGGABLE DATABASE plsql_class2024db
  2  ADMIN USER no_plsqlauca IDENTIFIED BY noble
  3  FILE_NAME_CONVERT = ('C:\APP\FALLY\PRODUCT\21C\ORADATA\XE\PDBSEED\', 'C:\APP\FALLY\PRODUCT\21C\ORADATA\XE\plsql_class2024db\');

Pluggable database created.
SQL> show pdbs;

    CON_ID CON_NAME                       OPEN MODE  RESTRICTED
---------- ------------------------------ ---------- ----------
         2 PDB$SEED                       READ ONLY  NO
         3 XEPDB1                         READ WRITE NO
         4 NO_TO_DELETE_PDB               MOUNTED
         5 PLSQL_CLASS2024DB              MOUNTED
         6 PLSQL_CLASS2024DBAO            READ WRITE NO
```
##### Opening plsql_class2024db
```sql

SQL> ALTER PLUGGABLE DATABASE plsql_class2024db OPEN;

Pluggable database altered.
```
##### Creating User,Changing sessions and  granting all priveleges  
```sql
SQL> ALTER SESSION SET CONTAINER = plsql_class2024dbao;

Session altered.

SQL> CREATE USER NO_plsqlauca IDENtified BY noble;

User created.
SQL> GRANT CONNECT, RESOURCE, DBA TO NO_plsqlauca;

Grant succeeded.

```

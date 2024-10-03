## Pluggable Database Work
### Task 1: 
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

```
SQL> ALTER PLUGGABLE DATABASE plsql_class2024db OPEN;

Pluggable database altered.
```
##### Creating User,Changing sessions and  granting all priveleges  
```sql
SQL> ALTER SESSION SET CONTAINER = plsql_class2024dbao;

Session altered.

SQL> CREATE USER NO_plsqlauca IDENtified BY noble;
User created.
```
### Task 2: 
####I created another PDB named no_to_delete_pdb, following the format based on my name. After successfully creating the PDB, I proceeded to delete it. Screenshots were taken for both the creation and deletion process, along with all SQL commands used.
```sql

SQL> CREATE PLUGGABLE DATABASE  no_to_delete_pdb
  2  ADMIN USER no_to_delete_pdb IDENTIFIED BY noble
  3  FILE_NAME_CONVERT = ('C:\APP\FALLY\PRODUCT\21C\ORADATA\XE\PDBSEED\', 'C:\APP\FALLY\PRODUCT\21C\ORADATA\XE\no_to_delete_pdb\');

Pluggable database created.
```
#### Connecting to no_to_delete_pdb wit all resourse
```sql

SQL> GRANT CONNECT, RESOURCE, DBA TO NO_plsqlauca;

Grant succeeded.
SQL> show pdbs;

    CON_ID CON_NAME                       OPEN MODE  RESTRICTED
---------- ------------------------------ ---------- ----------
         2 PDB$SEED                       READ ONLY  NO
         3 XEPDB1                         READ WRITE NO
         4 NO_TO_DELETE_PDB               MOUNTED
         5 PLSQL_CLASS2024DB              MOUNTED
         6 PLSQL_CLASS2024DBAO            READ WRITE NO
```
#### Droping no_to_delete_pdb
```sql
SQL> DROP PLUGGABLE DATABASE no_to_delete_pdb INCLUDING DATAFILES;

Pluggable database dropped.

SQL> show pdbs;

    CON_ID CON_NAME                       OPEN MODE  RESTRICTED
---------- ------------------------------ ---------- ----------
         2 PDB$SEED                       READ ONLY  NO
         3 XEPDB1                         READ WRITE NO
         5 PLSQL_CLASS2024DB              READ WRITE NO
         6 PLSQL_CLASS2024DBAO            READ WRITE NO
```

### Task 3: 

#### I configured Oracle Enterprise Manager, completed the setup, and captured a screenshot of the dashboard reflecting the successful completion of the previous tasks.

##### Screenshot 1

###### Inserting values that to  estabish connection of pllugable Database plsql_class2024dbon name of connection I inserted random name calle pluggable_Database_plsql , on use name i inserted user name i created and password identifiying his privilleges and on service name i inserted name of that database PLSQL_CLASS2024DB

![pluggable](https://github.com/user-attachments/assets/7e478cfc-a7b3-451e-98be-dcfc0238efe5)

 ##### Screenshot 2

 ###### on this screenshot i just justfying that connection was succesfull established
 
![pluggable suceess connection](https://github.com/user-attachments/assets/9705d388-9776-4ca4-b8cf-ca1be97eb05a)
 ##### Screenshot3
 ###### connection is connected succesfull!!
 ![connected pluggable](https://github.com/user-attachments/assets/0d7e1515-d0b2-4289-8791-4ecff99732a4)
 

 ####### Oracle enteprise Manager

 
 ![sspl8778](https://github.com/user-attachments/assets/5d9caba1-4727-42b8-a9cb-593125c55e2e)
![datbase basic](https://github.com/user-attachments/assets/04e8ec84-c7bf-456a-9a7b-2885d14ff9ca)

 












```

<h1 align="center">SQL Commands</h1>


###  DDL ( Data Definition Language ):
 --> CREATE, ALTER, DROP, TRUNCATE, RENAME

### DML ( Data Manupilation Language ):
 --> INSERT, UPDATE, DELETE
 
### DRL/DQL ( Data Retrieval / Data Query Language ):
 --> SELECT

### TCL ( Transaction Control Language ):
 --> COMMIT, ROLLBACK, SAVE POINT

### DCL ( Data Control Language ):
 --> GRANT, REVOKE

<h2 align="center">Create Database / Schema</h2>

``` sql
CREATE DATABASE mydb; 
DROP DATABASE mydb; 
```

OR:

``` sql
CREATE SCHEMA mydb; 
DROP SCHEMA mydb; 
```

if not exists:

``` sql
CREATE DATABASE IF NOT EXISTS mydb;
``` 

<h2 align="center">Create Table</h2>

CREATE TABLE ``` <<TABLE NAME>> ``` ( ``` <<COLUMN NAME>> ``` ```  <<DATA TYPE>> ```  ( ``` <<SIZE OF THE DATA>> ```  ) );

Example:
   
 ``` sql 
 USE mydb;
 
 CREATE TABLE STUDENT(NO INT (5), NAME VARCHAR(15), MARKS INT (3)); 
 ```
 
 <h2 align="center">Insert data into table</h2>
 
  INSERT INTO ``` <<TABLE NAME>> ``` VALUES  (  ``` VAL1 ```, ``` VAL2 ```, ``` VAL3 ```  ) 
  
  Example:
  
  ```sql
  USE mydb;
  
  INSERT INTO STUDENT VALUES(101, 'BEZZI', 80);
  INSERT INTO STUDENT(NAME, NO, MARKS) VALUES('BEGLI', 102, 60);
  INSERT INTO STUDENT VALUES(103, 'BATYR', NULL);
  ```
 
<h2 align="center">Selecting Rows from a table</h2>
  
  ```sql
  USE hr;
  
  SELECT * FROM EMPLOYEES;
  SELECT EMPLOYEE_ID, FIRST_NAME, LAST_NAME, SALARY FROM EMPLOYEES;
  
  ```
  
<h2 align="center">SQL Data types</h2>
    
### Numeric

 - ```TINYINT```(size) -->	A very small integer. Signed range is from -128 to 127. Unsigned range is from 0 to 255. The size parameter specifies the maximum display width (which is 255)
 - ```SMALLINT```(size) -->	A small integer. Signed range is from -32768 to 32767. Unsigned range is from 0 to 65535. The size parameter specifies the maximum display width (which is 255)
 - ```MEDIUMINT```(size) -->	A medium integer. Signed range is from -8388608 to 8388607. Unsigned range is from 0 to 16777215. The size parameter specifies the maximum display width (which is 255)
 - ```INT```(size) -->	A medium integer. Signed range is from -2147483648 to 2147483647. Unsigned range is from 0 to 4294967295. The size parameter specifies the maximum display width (which is 255)
 - ```BIGINT```(size) -->	A large integer. Signed range is from -9223372036854775808 to 9223372036854775807. Unsigned range is from 0 to 18446744073709551615. The size parameter specifies the maximum display width (which is 255)
 - ```FLOAT``` -->	A small approximate number with a floating decimal point
 - ```DOUBLE``` -->	A large number with a floating decimal point.
 - ```DECIMAL``` -->	A DOUBLE stored as a string, allowing for a fixed decimal point. Choice for storing currency values.

### Text
- ```CHAR```(size) -->	A FIXED length string (can contain letters, numbers, and special characters). The size parameter specifies the column length in characters - can be from 0 to 255. Default is 1
- ```VARCHAR```(size) --->	A VARIABLE length string (can contain letters, numbers, and special characters). The size parameter specifies the maximum column length in characters - can be from 0 to 65535
- ```BLOB```(size) --> (Binary Large Objects). Holds up to 65,535 bytes of data
- ```MEDIUMTEXT``` -->	Holds a string with a maximum length of 16,777,215 characters
- ```MEDIUMBLOB``` -->	(Binary Large Objects). Holds up to 16,777,215 bytes of data
- ```LONGTEXT``` -->	Holds a string with a maximum length of 4,294,967,295 characters
- ```LONGBLOB``` --> (Binary Large Objects). Holds up to 4,294,967,295 bytes of data

### Date/time
- ```DATE``` -->	A date. Format: YYYY-MM-DD. The supported range is from '1000-01-01' to '9999-12-31'
- ```DATETIME``` -->	A date and time combination. Format: YYYY-MM-DD hh:mm:ss. The supported range is from '1000-01-01 00:00:00' to '9999-12-31 23:59:59'
- ```TIMESTAMP``` -->	A timestamp. Format: YYYY-MM-DD hh:mm:ss. The supported range is from '1970-01-01 00:00:01' UTC to '2038-01-09 03:14:07' UTC
- ```TIME``` -->	A time. Format: hh:mm:ss. The supported range is from '-838:59:59' to '838:59:59'

<h2 align="center">Where clause</h2>

Used for selecting the rows based on condition. (Filtering the rows using where condition)

```sql
USE hr;

SELECT * FROM EMPLOYEES;
SELECT * FROM EMPLOYEES WHERE SALARY > 8000;
SELECT * FROM EMPLOYEES WHERE SALARY <= 5000;
SELECT * FROM EMPLOYEES WHERE DEPARTMENT_ID = 30;
SELECT * FROM EMPLOYEES WHERE COMMISSION_PCT is null;
SELECT * FROM EMPLOYEES WHERE FIRST_NAME = 'Jennifer';
SELECT DISTINCT DEPARTMENT_ID FROM EMPLOYEES;
SELECT DISTINCT * FROM EMPLOYEES;
```

<h2 align="center">Logical Operators (AND, OR, NOT)</h2>

```sql
USE hr;

SELECT * FROM EMPLOYEES WHERE SALARY > 15000 AND JOB_ID = 'AD_VP';
SELECT * FROM EMPLOYEES WHERE SALARY > 15000 OR JOB_ID = 'AD_VP';
SELECT * FROM EMPLOYEES WHERE NOT FIRST_NAME = 'David';
```

<h2 align="center">Between & IN Operators</h2>

- Between --> Used to display the rows which is following in the range of values.

- Not Between

```sql
USE hr;

SELECT * FROM EMPLOYEES WHERE SALARY BETWEEN 10000 AND 12000;
SELECT * FROM EMPLOYEES WHERE SALARY NOT BETWEEN 10000 AND 12000;
```

- In --> In operator return the rows when the values are matching in the list

- Not In

```sql
SELECT * FROM EMPLOYEES WHERE SALARY = 3400 OR SALARY = 2500 OR SALARY = 3000;

SELECT * FROM EMPLOYEES WHERE SALARY IN(3400, 2500, 3000);
SELECT * FROM EMPLOYEES WHERE SALARY NOT IN(3400, 2500, 3000);
```

<h2 align="center">Pattern Matching operators (whiled card characters)</h2>

- % --> many characters
- _ --> single character

```sql
SELECT * FROM EMPLOYEES WHERE FIRST_NAME LIKE 'S%';
SELECT * FROM EMPLOYEES WHERE FIRST_NAME LIKE '%r';
SELECT * FROM EMPLOYEES WHERE FIRST_NAME LIKE 'S%r';
SELECT * FROM EMPLOYEES WHERE FIRST_NAME LIKE '%m%';
SELECT * FROM EMPLOYEES WHERE FIRST_NAME NOT LIKE 'S%';
SELECT * FROM EMPLOYEES WHERE FIRST_NAME LIKE '%e_';
SELECT * FROM EMPLOYEES WHERE FIRST_NAME LIKE '___';
```










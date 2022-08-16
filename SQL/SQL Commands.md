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

<h2 align="center">MySQL Functions</h2>

### 1) Strings functions - operate on string data types

```Upper()```: converts into upper case letters.
```sql
SELECT UPPER(First_name) FROM employees;
```

```Lower()```: converts into lower case letters.
```sql
SELECT LOWER(First_name) FROM employees;
```

```Length()```: return the length of string.
```sql
SELECT LENGTH('bezzi');
SELECT * FROM EMPLOYEES WHERE LENGTH(First_name) = 4;
```
```TRIM()```: removes the specified characters from both sides.
```sql
SELECT TRIM('   bezzii   ');
SELECT TRIM('g' from 'ggbezziigg');
```
```NSTR()```: returns the position of the character within a string.
```sql
SELECT INSTR('bezzii','e');
```

```SUBSTR()```/```SUBSTRING()```: Returns the substring of the string.
```sql
SELECT SUBSTR('bezzii',2,3);   --ezz
SELECT SUBSTR('bezzii',3,3);   --zzi
SELECT SUBSTR('bezzii',4,3);   --zii

SELECT SUBSTRING('bezzii',2,3);   --ezz
SELECT SUBSTRING('bezzii',3,3);   --zzi
SELECT SUBSTRING('bezzii',4,3);   --zii

USE hr;
SELECT SUBSTR(FIRST_NAME, 1, 3) FROM EMPLOYEES;
```

```CONCAT()```: To join two strings.
```sql
SELECT CONCAT('bez', 'zii');

USE hr;
SELECT CONCAT(First_name, Last_name) fullName FROM EMPLOYEES;
```

### 2) Numeric functions - operate on numeric data types

```sql
SELECT ABS(-40);    --40
SELECT ABS(+40);    --40
SELECT SQRT(25);    --5
SELECT MOD(10, 3);   --1
SELECT power(2, 5);  --32
```

```TRUNCATE()```: function truncates a number to the specified number of decimal places.
```sql
SELECT TRUNCATE(40.1234, 3);     -- 40.123
SELECT TRUNCATE(40.1234, 2);     -- 40.12
SELECT TRUNCATE(6876, -1);       -- 6870
SELECT TRUNCATE(6876, -2);       -- 6800
SELECT TRUNCATE(68763456, -5);   -- 68700000
```

```GREATEST()``` & ```LEAST()```: returns greatest,least values in the provided values.
```sql
SELECT GREATEST(100, 200, 300, 400, 500);  --500
SELECT LEAST(100, 200, 300, 400, 500);     --100
```

### 3) Date functions - operate on date data types

```CURDATE()``` / ```CURRENT_DATE()```: function returns the current date.
```sql
SELECT CURDATE();
SELECT CURRENT DATE();
```

```CURTIME()``` / ```CURRENT_TIME()```: function returns the current time.
```sql
SELECT CURTIME();
SELECT CURRENT_TIME();
```

```NOW()```: function returns the current date and time.
```sql
SELECT NOW();
```

```SYSDATE()```: function returns the current date and time.
```sql
SELECT SYSDATE();
```

```MONTH()```: function returns the month part for a given date (a number from 1 to 12).
```sql
SELECT MONTH("2019-05-19");  --5
```

```YEAR()```: function returns the year part for a given date (a number from 1000 to 9999).
```sql
SELECT YEAR("2019-05-19");   -- 2019
```
```DAY()```: function returns the day of the month for a given date (a number from 1 to 31).
```sql
SELECT DAY("2019-05-19");
```

#### Queries on Date Functions

Display employees who are joined in 1987.
```sql
SELECT * FROM EMPLOYEES WHERE YEAR(HIRE_DATE)="1987";
```

Display employees who are joined in June.
```sql
SELECT * FROM EMPLOYEES WHERE MONTH(HIRE_DATE) = '6';
SELECT * FROM EMPLOYEES WHERE MONTHNAME(HIRE_DATE) = 'JUNE';
```

### 4) Aggregate functions - operate on all of the data types and produce summarized result sets

Aggregate Functions are all about performing calculations on multiple rows of a single column of a table and returning a single value.
```sql
USE hr;

SELECT AVG(SALARY) FROM EMPLOYEES;  --returns average value
SELECT SUM(SALARY) FROM EMPLOYEES;  --returns summary   
SELECT MIN(SALARY) FROM EMPLOYEES;  --returns minumum value
SELECT MAX(SALARY) FROM EMPLOYEES;  --returns maximum value
SELECT COUNT(*) FROM EMPLOYEES;    
```


<h2 align="center">Group By clause</h2>

Group By clause:

The GROUP BY clause groups records into summary rows.

GROUP BY returns one records for each group.

GROUP BY typically also involves aggregates: COUNT, MAX, SUM, AVG, etc.

GROUP BY can group by one or more columns.
```sql
SELECT DEPARTMENT_ID, SUM(SALARY) FROM EMPLOYEES GROUP BY DEPARTMENT_ID;
SELECT DEPARTMENT_ID, AVG(SALARY) FROM EMPLOYEES GROUP BY DEPARTMENT_ID;
SELECT DEPARTMENT_ID, MAX(SALARY), MIN(SALARY) FROM EMPLOYEES GROUP BY DEPARTMENT_ID;
SELECT JOB_ID, COUNT(*) FROM EMPLOYEES GROUP BY JOB_ID;
```

All the columns in the select list should include in group by clause.
```sql
SELECT DEPARTMENT_ID, JOB_ID, SUM(SALARY) FROM EMPLOYEES GROUP BY DEPARTMENT_ID, JOB_ID;
SELECT DEPARTMENT_ID, SUM(SALARY), FIRST_NAME FROM EMPLOYEES GROUP BY DEPARTMENT_ID;  -- Invalid query
```

<h2 align="center">Having & Order by clause</h2>

Having clause:Having clause is used to filter the output from the group by clause.
```sql
SELECT DEPARTMENT_ID, SUM(SALARY) FROM EMPLOYEES GROUP BY DEPARTMENT_ID HAVING SUM(SALARY) > 20000;
SELECT DEPARTMENT_ID, SUM(SALARY) FROM EMPLOYEES WHERE DEPARTMENT_ID <> 50 GROUP BY DEPARTMENT_ID;
```
Order By clause:Order by clause is used to arrange the rows inatable(ascending or descending
order).
```sql
SELECT * FROM EMPLOYEES ORDER BY DEPARTMENT_ID DESC;
SELECT * FROM EMPLOYEES ORDER BY SALARY;
```

<h2 align="center">Order Of Execution</h2>

Where --> Group by --> Having --> Order By
```
SELECT column-names
 FROM table-name
  WHERE condition
    GROUP BY column-names
       Having condition
        ORDER BY column-names
```
```sql
SELECT DEPARTMENT_ID, SUM(SALARY) FROM EMPLOYEES 
 GROUP BY DEPARTMENT_ID 
 HAVING SUM(SALARY) > 20000 
 ORDER BY SUM(SALARY);

SELECT DEPARTMENT_ID, SUM(SALARY) FROM EMPLOYEES 
 WHERE DEPARTMENT_ID <> 100 
 GROUP BY DEPARTMENT_ID 
 HAVING SUM(SALARY) > 20000 
 ORDER BY SUM(SALARY) DESC;
```

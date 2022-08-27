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

<h2 align="center">UNION & UNION ALL</h2>

The UNION operator is used to combine the result-set of two or more SELECT statements.

Each SELECT statement within UNION must have the same number of columns

The columns must also have similar data types

The columns in each SELECT statement must also be in the same order
```sql
SELECT * FROM A;
SELECT * FROM B;

SELECT NUM FROM A UNION SELECT NUM FROM B;       -- without duplicates 
SELECT NUM FROM A UNION ALL SELECT NUM FROM B;   -- with duplicates
```

<h2 align="center">SQL Joins</h2>

Joins help retrieving data from two or more database tables.

The tables are mutually related using primary and foreign keys.

Types of Joins

1. Equi Join / Inner Join / Simple Join
2. Right Join
3. Left Join
4. Full Join
5. Self Join

Inner / Equi join ( Returns Only matched records from Tab1 & Tab2 )
```sql
SELECT * FROM TAB1 INNER JOIN TAB2 ON TAB1.NUMID = TAB2.NUMID;
```

Right outer join ( Returns matched records + unmatched from right table Tab1 )
```sql
SELECT * FROM TAB1 RIGHT JOIN TAB2 ON TAB1.NUMID = TAB2.NUMID;
```  
Left outer join ( Returns matched records + unmatched from right table Tab2 )
```sql
SELECT * FROM TAB1 LEFT JOIN TAB2 ON TAB1.NUMID = TAB2.NUMID;
```  
Full outer join ( Returns matched records + unmatched from both tables )  -- not supported in mysql
```sql
SELECT * FROM TAB1 FULL JOIN TAB2 ON TAB1.NUMID = TAB2.NUMID;
```  

#### Inner Join/Self-Join

Returns Only matched records from both the tables
```sql
SELECT
 EMPLOYEE_ID, FIRST_NAME, JOB_ID, DEPT.DEPARTMENT_ID, DEPARTMENT_NAME, LOCATION_ID
FROM EMPLOYEES EMP INNER JOIN DEPARTMENTS DEPT ON
 (EMP.DEPARTMENT_ID = DEPT.DEPARTMENT_ID);
```

#### Left Join

Returns matched records+unmatched from left table departments
```sql
SELECT EMPLOYEE_ID, FIRST_NAME, JOB_ID, DEPT.DEPARTMENT_ID, DEPARTMENT_NAME, LOCATION_ID
FROM EMPLOYEES EMP LEFT JOIN DEPARTMENTS DEPT 
 ON (EMP.DEPARTMENT_ID = DEPT.DEPARTMENT_ID);
```

#### Right Join

Returns matched records + unmatched from right table employees
```sql
SELECT EMPLOYEE_ID, FIRST_NAME, JOB_ID, DEPT.DEPARTMENT_ID, DEPARTMENT_NAME, LOCATION_ID
FROM EMPLOYEES EMP RIGHT JOIN DEPARTMENTS DEPT 
 ON (EMP.DEPARTMENT_ID = DEPT.DEPARTMENT_ID);
```

#### Inner Join/Self-Join

Returns Only matched records from both the tables
```sql
SELECT EMPLOYEE_ID, FIRST_NAME, JOB_ID, DEPT.DEPARTMENT_ID, DEPARTMENT_NAME, LOCATION_ID
FROM EMPLOYEES EMP INNER JOIN DEPARTMENTS DEPT 
 ON (EMP.DEPARTMENT_ID = DEPT.DEPARTMENT_ID);
```

#### Self-Join

Join withatable with the same table

Query : Print Employees details who is Manager of other employees.
```sql
SELECT E.EMPLOYEE_ID, M.MANAGER_ID, E.FIRST_NAME, E.JOB_ID, M.FIRST_NAME 
FROM EMPLOYEES E, EMPLOYEES M WHERE EMPLOYEE_ID = M.MANAGER_ID;
```

<h2 align="center">Sub Queries</h2>

Sub Query isaQuery withinaQuery.

Sub Query contains2parts.

1. Outer Query
2. Inner Query
 
The output of inner query is become input of outer query.

2 Types of Sub Queries :

1. Single row sub query, <=, >=, !=
2. Multi row Sub Query. IN, ANY, ALL


#### Single Row Sub Queries

```sql
-- Display employees whose salary is less than the of Ellen's Salary

SELECT SALARY FROM EMPLOYEES WHERE FIRST_NAME = 'Ellen';  -- 11000.00
SELECT SALARY FROM EMPLOYEES WHERE SALARY < 11000.00;

SELECT SALARY FROM EMPLOYEES WHERE SALARY < ( SELECT SALARY FROM EMPLOYEES WHERE FIRST_NAME = 'Ellen' );
```

```sql
-- 2nd max salary from employee

SELECT MAX(SALARY) FROM EMPLOYEES WHERE SALARY <
    ( SELECT MAX(SALARY) FROM EMPLOYEES WHERE SALARY );
    
-- 3nd max salary from employee

SELECT MAX(SALARY) FROM EMPLOYEES WHERE SALARY <
    ( SELECT MAX(SALARY) FROM EMPLOYEES WHERE SALARY <
            ( SELECT MAX(SALARY) FROM EMPLOYEES ) );
            
-- Find the salary of employees whose salary is greater than the salary of employee whose EMPLOYEE_ID 150

SELECT SALARY FROM EMPLOYEES WHERE SALARY > ( SELECT SALARY FROM EMPLOYEES WHERE EMPLOYEE_ID = 150);

-- Display the employees who all are earning the highest salary

SELECT * FROM EMPLOYEES WHERE SALARY = ( SELECT MAX(SALARY) FROM EMPLOYEES );
```

#### Multi row Sub Queries

```sql
-- Display employees whose salary is equal to the salary of the at least one employee in department id 30

SELECT * FROM EMPLOYEES WHERE SALARY IN ( SELECT SALARY FROM EMPLOYEES WHERE DEPARTMENT_ID = 30 );

-- Display the employees whose salary is greater than the at least on employee in department id 30

SELECT * FROM EMPLOYEES WHERE SALARY > ANY ( SELECT SALARY FROM EMPLOYEES WHERE DEPARTMENT_ID = 30 );

-- Display the employees whose salary is less than the at least on employee in department id 30

SELECT * FROM EMPLOYEES WHERE SALARY < ANY ( SELECT SALARY FROM EMPLOYEES WHERE DEPARTMENT_ID = 30 );

-- Query to get department name of the employee

SELECT FIRST_NAME, EMPLOYEE_ID, DEPARTMENT_ID, 
 ( SELECT DEPARTMENT_NAME FROM DEPARTMENTS WHEREEMPLOYEES.DEPARTMENT_ID = DEPARTMENTS.DEPARTMENT_ID ) DNAME
FROM EMPLOYEES;

-- List out the employees who are having salary less than the maximum salary and also having hire
-- date greater than the hire date of an employee who is having maximum salary

SELECT EMPLOYEE_ID, FIRST_NAME SALARY, HIRE_DATE FROM EMPLOYEES WHERE SALARY <
  ( SELECT MAX(SALARY) FROM EMPLOYEES ) AND HIRE_DATE >
     ( SELECT HIRE_DATE FROM EMPLOYEES WHERE SALARY =
        ( SELECT MAX(SALARY) FROM EMPLOYEES ) );
```

<h2 align="center">Integrity Constraints</h2>

SQL constraints are used to specify rules for data inatable.

Constraints can be specified when the table is created with the CREATE TABLE statement,or after the table is created with the ALTER TABLE statement.
SQL Constraints

- NOT NULL-Ensures thatacolumn cannot haveaNULL value

- UNIQUE-Ensures that all values inacolumn are different

- PRIMARY KEY-Acombination ofaNOT NULL and UNIQUE.Uniquely identifies each row inatable

- FOREIGN KEY-Uniquely identifiesarow/record in another table

- CHECK- Ensures that all values inacolumn satisfiesaspecific condition

- DEFAULT-Setsadefault value foracolumn when no value is specified

#### Not null

NOT NULL: This is a constraint will not accept NULL values into the column.

You can apply NOT NULL on any number of columns

```sql
CREATE TABLE student
( no INT(3) NOT NULL, 
  name VARCHAR(10), 
  marks INT(3) );

INSERT INTO student VALUES( 101, 'Bezzi', 50 );    -- CORRECT
INSERT INTO student VALUES( NULL, 'Begli', 70 );  -- ERROR
```

#### UNIQUE

UNIQUE: this constraint will not accept duplicate values.

This constraint can apply on both column and table level.

Unique constraint column can accept multiple NULLS.
```SQL
-- Column Level
CREATE TABLE student
( no INT(3) UNIQUE,
  name VARCHAR(10),
  marks INT(3) );

-- Table Level
CREATE TABLE student
( no INT(3),
  name VARCHAR(10),
  marks INT(3),
  UNIQUE(no) );
  
  
INSERT INTO student VALUES(101, 'Bezzi', 50);     -- CORRECT
INSERT INTO student VALUES(101, 'Begli', 60);     -- ERROR
INSERT INTO student VALUES(null, 'Batyr', 80);    -- CORRECT
INSERT INTO student VALUES(null, 'Dovran', 60);   -- CORRECT
```

#### Primary Key

PRIMARY KEY: Combination of Unique + Not Null

primary key column will not allow duplicate values and also null values.

primary key constraint can create both column level & table level.

We can create primary key on combination of two columns called as composite primary key.

Composite key can be applied only at table level.
```sql
CREATE TABLE student
( no INT(3) PRIMARY KEY,
  name VARCHAR(10),
  marks INT(3) );
 
INSERT INTO student VALUES(101, 'Bezzi', 50);     -- CORRECT
INSERT INTO student VALUES(101, 'Begli', 60);     -- ERROR
INSERT INTO student VALUES(null, 'Batyr', 60);    -- ERROR
```

#### Foreign key constraint

A FOREIGN KEY is a key used to link two tables together.

A FOREIGN KEY is a field ( or collection of fields ) in one table that refers to the PRIMARY KEY in another table.

The table containing the foreign key is called the child table, and the table containing the candidate key is called the referenced or parent table.
```sql
-- parent Table
CREATE TABLE school
( no INT(3),
  name VARCHAR(15),
  marks INT(3),
  PRIMARY KEY(no) );
 
INSERT INTO school VALUES(101, 'Bezzi', 90);
INSERT INTO school VALUES(102, 'Begli', 70);
INSERT INTO school VALUES(103, 'Batyr', 60);

-- child Table
CREATE TABLE library
( no INT(3),
  FOREIGN KEY(no) REFERENCES school(no),
  book_name VARCHAR(10) );

INSERT INTO library VALUES(102, 'java');       -- CORRECT
INSERT INTO library VALUES(108, 'c');          -- ERROR
INSERT INTO library VALUES(null, 'dot net');   -- CORRECT
```

#### ON DELETE CASCADE

ON DELETE CASCADE:

Normally, we cannot delete rows from Parent table unless we delete corresponding row from child table.

We can delete the rows from the parent table & corresponding child table row as well ( at sametime ) by using ON DELETE CASCADE option. 
```sql
-- parent Table
CREATE TABLE school
( no INT(3),
name VARCHAR(15),
marks INT(3),
PRIMARY KEY(no) );

INSERT INTO school VALUES(101, 'Bezzi', 90);
INSERT INTO school VALUES(102, 'Begli',70);
INSERT INTO school VALUES(103, 'Batyr', 80);

-- child Table
CREATE TABLE library
( no INT(3),
  FOREIGN KEY(no) REFERENCES school(no) ON DELETE CASCADE,
  book_name VARCHAR(10) );

INSERT INTO library VALUES(101, 'dot net');
INSERT INTO library VALUES(102, 'java');

DELETE FROM school WHERE no = 101;   -- CORRECT
-- One row deleted from parent table and one from child table also deleted
```

#### Foreign key constraint at table level

```sql
-- parent Table
CREATE TABLE school
( no NUMBER(3),
  name VARCHAR(15),
  marks NUMBER(3),
  PRIMARY KEY(no) );
  
INSERT INTO school VALUES(101, 'Bezzi', 50);
INSERT INTO school VALUES(102, 'Begli', 60);
INSERT INTO school VALUES(103, 'Batyr', 80);

-- child Table
CREATE TABLE library
( rollno int(3),
  book_name VARCHAR(10),
  FOREIGN KEY(rollno) REFERENCES school(NO) ON DELETE CASCADE );

INSERT INTO library VALUES(101, 'dot net');
INSERT INTO library VALUES(102, 'java');
```

#### Check Constraint

Check constraint is used for allowing to user to enter specific values into column.

```sql
CREATE TABLE school
( no INT(5),
  name VARCHAR(15),
  marks INT(5)
  CHECK(marks BETWEEN 50 AND 100) );
 
INSERT INTO student VALUES(101, 'Bezzi', 60);   -- CORRECT
INSERT INTO student VALUES(101, 'Bezzi', 45);   -- ERROR
INSERT INTO student VALUES(101, 'Bezzi', 105);  -- ERROR

-- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --

CREATE TABLE loc
( city VARCHAR(15) CHECK( city IN( 'Mary', 'Bayram-aly', 'Ashgabat') ),
 country VARCHAR(15),
 pin INT(8));
 
INSERT INTO loc VALUES('Mary', 'Turkmenistan', 123456);       -- CORRECT
INSERT INTO loc VALUES('Istanbul', 'Turkey', 644566);         -- ERROR
INSERT INTO loc VALUES('Ashgabat', 'Turkmenistan', 678445);   -- CORRECT
```

#### Default Constraint

The DEFAULT constraint is used to provide a default value for a column.

The default value will be added to all new records IF no other value is specified.

```sql
CREATE TABLE orders
( ID INT(5),
  orderNumber INT(5),
  orderDate datetime DEFAULT now() );
  
INSERT INTO Orders(ID, orderNumber) VALUES(101, 2456);
INSERT INTO Orders(ID, orderNumber) VALUES(102, 2457);
```

<h2 align="center">AUTO INCREMENT</h2>

Auto Increment is a function that operates on numeric data types. It automatically generates sequential numeric values every time thatarecord is inserted in to a table for a field defined as auto increment.
```sql
CREATE TABLE student
( no INT(5) PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(15),
  marks INT(5) );

ALTER TABLE student AUTO_INCREMENT = 100;

INSERT INTO student(name, marks) VALUES('X', 60);
INSERT INTO student(name, marks) VALUES('Y', 45);
INSERT INTO student(name, marks) VALUES('Z', 105);
```

<h2 align="center">LIMIT</h2>

Limit is used to display limited Rows fromatable.

```sql
SELECT * FROM employees LIMIT 10;
SELECT * FROM employees LIMIT 5, 10; 
```

<h2 align="center">Views</h2>

A view is a virtual table based on the result-set of an SQL statement.

A view contains rows and columns, just like a real table. The fields in a view are fields from one or more real tables in the database.

You can add SQL functions, WHERE, and JOIN statements to a view and present the data as if the data were coming from one single table.

Example:
```sql
use hr;

-- Creating a view
CREATE VIEW employees_V1 AS SELECT Employee_ID, First_Name, Salary FROM employees;
SELECT * FROM employees_V1;

-- Dropping View
DROP VIEW employees_V1;
```

<h2 align="center">Index</h2>

Indexes are used to retrieve data from the database very fast.

The users cannot see the indexes,they are just used to speed up searches/queries.
```sql
-- Creating Index
CREATE INDEX idx_employees ON employees(First_Name);

-- Dropping Index
DROP INDEX idx_employees ON employees;
```

<h2 align="center">TCL-Commit & Rollback</h2>
```sql
SET autocommit = 0;

CREATE TABLE student(id INT(3),name VARCHAR(15) );

INSERT INTO student VALUES(101, 'abc');
INSERT INTO student VALUES(102, 'abc');
INSERT INTO student VALUES(103, 'abc');

DELETE FROM student WHERE id = 103;  -- Deletes record temporarily

Rollback;       -- Rollback record
Commit;         -- Commited delete
Rollback;

SELECT * FROM student;  -- cannot get deleted record after commit
```





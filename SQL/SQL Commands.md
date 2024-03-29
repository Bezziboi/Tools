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

SELECT * FROM employees WHERE SALARY IN ( SELECT SALARY FROM EMPLOYEES WHERE DEPARTMENT_ID = 30 );

-- Display the employees whose salary is greater than the at least on employee in department id 30

SELECT * FROM employees WHERE SALARY > ANY ( SELECT SALARY FROM EMPLOYEES WHERE DEPARTMENT_ID = 30 );

-- Display the employees whose salary is less than the at least on employee in department id 30

SELECT * FROM employees WHERE SALARY < ANY ( SELECT SALARY FROM EMPLOYEES WHERE DEPARTMENT_ID = 30 );

-- Query to get department name of the employee

SELECT FIRST_NAME, EMPLOYEE_ID, DEPARTMENT_ID, 
 ( SELECT DEPARTMENT_NAME FROM DEPARTMENTS WHEREEMPLOYEES.DEPARTMENT_ID = DEPARTMENTS.DEPARTMENT_ID ) DNAME
FROM employees;

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

The users cannot see the indexes,they are just used to speed up searches / queries.

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

<h2 align="center">MySQL Stored Procedure</h2>

MySQL Stored Procedure. A procedure (often called a stored procedure) is a collection of pre-compiled SQL statements stored inside the database. It is a subroutine or a subprogram in the regular computing language. A procedure always contains a name, parameter lists, and SQL statements.

- A stored procedure is block of SQL Statements.
- We can save stored procedure and can be reuse multiple times.
- We can also pass parameters to a stored procedure.


Procedure without Parameter :

- set the delimiter to // to avoid confusion with the ; in the procedure body
```sql
delimiter //

CREATE PROCEDURE SelectAllCustomers()
 BEGIN
    select * from customers;
 END //

delimiter ;
```

- To see the procedures 
```sql
SELECT ROUTINE_NAME
FROM INFORMATION_SCHEMA.ROUTINES;
```

- To call the procedure 
```sql
call SelectAllCustomers();
```

MySQL procedure parameter has one of three modes:

- IN parameter

It is the default mode. It takes a parameter as input, such as an attribute. When we define it, the calling program has to pass an argument to the stored procedure. This parameter's value is always protected.

- OUT parameters

It is used to pass a parameter as output. Its value can be changed inside the stored procedure, and the changed (new) value is passed back to the calling program. It is noted that a procedure cannot access the OUT parameter's initial value when it starts.

- INOUT parameters

It is a combination of IN and OUT parameters. It means the calling program can pass the argument, and the procedure can modify the INOUT parameter, and then passes the new value back to the calling program.

```sql
delimiter //
         
CREATE PROCEDURE SelectAllCustomersByCity(IN mycity varchar(50))
 BEGIN
     SELECT * FROM customers WHERE city = mycity;
 END //

delimiter;

call SelectAllCustomersBycity('NewYork');
```

```sql
delimiter //

CREATE PROCEDURE SelectAllCustomersByCityAndPin(IN mycity varchar(50), IN pcode varchar(15))
 BEGIN
     SELECT * FROM customers WHERE city = mycity AND postalCode = pcode;
 END //
 
delimiter ;

call SelectAllCustomersByCityAndPin('NewYork', '060503' );
```

```sql
delimiter //
           
CREATE PROCEDURE get_order_by_cust(
     IN cust_no INT,
     OUT shipped INT,
     OUT canceled INT,
     OUT resolved INT,
     OUT disputed INT)
 BEGIN
       -- shipped
       SELECT count (*) INTO shipped FROM orders  WHERE customerNumber = cust_no AND status = 'Shipped';
       
       -- canceled
       SELECT count (*) INTO canceled FROM orders WHERE customerNumber = cust_no AND status = 'Canceled';
                                    
       -- resolved                                     
       SELECT count (*) INTO resolved FROM orders WHERE  customerNumber = cust_no  AND status = 'Resolved';
       
       -- disputed
       SELECT count (*) INTO disputed FROM orders WHERE  customerNumber = cust_no  AND status = 'Disputed';
 END //
     
delimiter ;

call get_order_by_cust(141, @shipped, @canceled, @resolved, @disputed);
select @shipped, @canceled, @resolved, @disputed;
```




```sql
delimiter //

CREATE PROCEDURE GetCustomershipping(
     IN pCustomerNUmber INT,
     OUT pShipping VARCHAR (50) )
     
BEGIN
     -- create variable
     DECLARE customerCountry VARCHAR (100);
     
 -- add customer country into variable    
 SELECT country INTO customerCountry FROM customers WHERE customerNumber = pCustomerNUmber;

     -- check customer country
     CASE customerCountry 
        -- if customer country 'USA' set '2-day Shipping'
        WHEN 'USA' THEN
            SET pShipping = '2-day Shipping';
        
        =- if customer country 'Canada' set '3-day Shipping'
        WHEN 'Canada' THEN
            SET pShipping = '3-day Shipping';
            
        =- else set '5-day Shipping'    
        ELSE
            SET pShipping = '5-day Shipping';
        END CASE;
        
 END //
 
delimiter ;

call GetCustomershipping(112, @shipping);
select @shipping;
```
 #### Error handling
```sql
delimiter //

CREATE PROCEDURE InsertSupplierProduct(IN inSupplierId INT, IN inProductId INT)

 BEGIN
 
     -- exit if the duplicate key occurs
     DECLARE EXIT HANDLER FOR 1062 SELECT 'Duplicate keys error encountered' Message;
     DECLARE EXIT HANDLER FOR SQLEXCEPTION SELECT 'SQLException encountered' Message;
     DECLARE EXIT HANDLER FOR SQLSTATE '23000' SELECT 'SQLSTATE 23000' ErrorCode;
     
     -- insert a new row into the SupplierProducts
     INSERT INTO SupplierProducts(supplierid, ,productId) VALUES (inSupplierId, inProductId);
     
    -- return the products supplied by the supplier id
     SELECT COUNT(*) FROM SupplierProducts WHERE supplierId = inSupplierId;
     
 END //
     
delimiter ;

-- valid 
call InsertsupplierProduct(1, 1);
call InsertSupplierProduct(1, 2);
call InsertSupplierProduct(1, 3);
-- invalid 
call InsertsupplierProduct(1, 3); -- error message 'Duplicate keys error encountered'
```

<h2 align="center">MySQL Stored Function</h2>

A stored function is a special kind stored program that returns a single value.

- Stored Procedure Vs Stored Function
  - The stored function must return a value but in Stored Procedure it is optional.
  - Even a procedure can return zero or n values.
  - Functions can have only input parameters for it whereas Procedures can have input or output parameters.
  - Functions can be called from Procedure whereas Procedures cannot be called from a Function.

Stored Function 1: Returns the customer level based on creditLimit

```sql
delimiter //

CREATE FUNCTION CustomerLevel(credit DECIMAL(10, 2)) RETURNS VARCHAR(20)

BEGIN

    DECLARE customerLevel VARCHAR(20);
    
    IF credit > 50000 THEN
       SET customerLevel = 'PLATINUM';
       
    ELSEIF (credit > = 10000 AND
            credit < = 50000) THEN
        SET customerLevel = 'GOLD';
        
    ELSEIF credit < 10000 THEN
       SET customerLevel = 'SILVER';
       
    END IF;
    
    RETURN customerLevel;
    
END //

delimiter ;

-- Shows all functions in 'classicmodels' database
SHOW FUNCTION STATUS WHERE db = 'classicmodels';

-- Select(use) function
SELECT customerName, CustomerLevel(creditLimit) FROM customers;
```

Stored Function in Stored Procedure

```sql
delimiter //

CREATE PROCEDURE GetCustomerLevel( IN customerNo INT, OUT customerLevel VARCHAR (20) )
   
BEGIN

   DECLARE credit DEC(10, 2) DEFAULT 0;
   
    -- get credit limit of a customer
    SELECT creditLimit INTO credit FROM customers WHERE customerNumber = customerNo;

    -- call the function
   SET customerLevel = CustomerLevel(credit);
   
END //

delimiter ;
```


<h2 align="center">MySQL Trigger</h2>

A trigger is a set of SQL statements that reside in a system catalog

It is a special type of stored procedure that is invoked automatically in response to an event

Each trigger is associated with a table , which is activated on any DML statement such as INSERT , UPDATE , or DELETE

A trigger is called a special procedure because it cannot be called directly like a stored procedure

The main difference between the trigger and procedure is that **a trigger is called automatically when a data modification event** is made against a table

A stored procedure **must be called explicitly**


#### Types of Triggers in MySQL


We can define the maximum six types of actions or events in the form of
triggers :
                                  
- **Before Insert** : It is activated before the insertion of data into the table
- **After Insert** : It is activated after the insertion of data into the table
- **Before Update** : It is activated before the update of data in the table
- **After Update** : It is activated after the update of the data in the table
- **Before Delete** : It is activated before the data is removed from the table
- **After Delete** : It is activated after the deletion of data from the table

Trigger 1 - Type: Before Insert

Description: Updates the total capacity in the WorkCenterStats table
before a new work center is inserted into the WorkCenter table

Let's create table first
```sql
CREATE TABLE WorkCenters(
   id INT AUTO INCREMENT PRIMARY KEY,
   name VARCHAR(100) NOT NULL,
   capacity INT NOT NULL);
   
CREATE TABLE WorkCenterStats(
   totalCapacity INT NOT NULL);
```

Creating trigger
```sql
delimiter //

CREATE TRIGGER before_workcenters_insert BEFORE INSERT ON WorkCenters FOR EACH ROW

BEGIN

   DECLARE rowcount INT ;
   
   SELECT COUNT(*) INTO rowcount FROM WorkCenterstats;
   IF rowcount > 0 THEN
      UPDATE WorkCenterStats SET totalCapacity = totalCapacity + new.capacity;
   ELSE
      INSERT INTO WorkCenterstats(totalCapacity) VALUES(new.capacity);
   END IF;
   
END //

delimiter ;
```

Trigger 2 - Type: After Insert

Description: Inserts a reminder into the reminders table if the birth date of the member is NULL

Tables Creation

```sql
CREATE TABLE members(
   id INT AUTO_INCREMENT,
   name VARCHAR(100) NOT NULL,
   email VARCHAR(255),
   birthDate DATE,
   PRIMARY KEY(id)
   );
   
CREATE TABLE reminders(
   id INT AUTO_INCREMENT,
   memberId INT,
   message VARCHAR(255) NOT NULL,
   PRIMARY KEY(id, memberId)
   );
```
   
Creating trigger

```sql
delimiter //

CREATE TRIGGER after_members_insert AFTER INSERT ON members FOR EACH ROW

BEGIN

   IF new.birthDate IS NULL THEN INSERT INTO reminders(memberId, message)
      VALUES(new.id, CONCAT('Hi', new.name, ', please update your date of birth.')); 
   END IF;
   
END //

delimiter ;
```
   
Trigger 3 - Type: Before Update 
   
Description: If you update the value in the quantity column to a new value that is 3 times greater than the current value, the trigger raises an error and stops the update 

Tables Creation

```sql
CREATE TABLE sales(
    id INT AUTO_INCREMENT,
    product VARCHAR (100) NOT NULL,
    quantity INT NOT NULL DEFAULT 0,
    fiscal Year SMALLINT NOT NULL,
    fiscalMonth TINYINT NOT NULL,
    CHECK (fiscalMonth >= 1 AND fiscalMonth <= 12),
    CHECK(fiscalYear BETWEEN 2000 and 2050),
    CHECK(quantity >= 0),
    UNIQUE(product, fiscalYear, fiscalMonth),
    PRIMARY KEY(id) );
    
INSERT INTO sales (product, quantity, fiscalYear, fiscalMonth) VALUES
    ('2003 Harley - Davidson Eagle Drag Bike', 120, 2020, 1),
    ('1969 Corvair Monza', 150, 2020, 1),
    ('1970 Plymouth Hemi Cuda', 200, 2020, 1);                       
```

Creating trigger

```sql
delimiter //

CREATE TRIGGER before_sales_update BEFORE UPDATE ON sales FOR EACH ROW

BEGIN

    DECLARE errorMessage VARCHAR(255);
    
    SET errorMessage = CONCAT('The new quantity', NEW.quantity,
                              ' cannot be 3 times greater than the current quantity',
                               OLD.quantity);
    
    IF new.quantity > old.quantity * 3 THEN
       SIGNAL SQLSTATE '45000' SET MESSAGE_TEXT = errorMessage;
    END IF;
    
END //

delimiter ;
```

Trigger 4 - Type: After Update

Description: If you update the value in the quantity column to a new value the trigger insert a new row to log the changes in the SalesChanges table

Tables Creation

```sql
CREATE TABLE SalesChanges(
    id INT AUTO_INCREMENT PRIMARY KEY,
    salesId INT,
    beforeQuantity INT,
    afterQuantity INT,
    changedAt TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP
    );
```

Creating trigger

```sql
delimiter //

CREATE TRIGGER after_sales_update AFTER UPDATE ON sales FOR EACH ROW

BEGIN

    IF OLD.quantity <> new.quantity THEN
        INSERT INTO SalesChanges (salesId, beforeQuantity, afterQuantity)
        VALUES(old.id, old.quantity, new.quantity);
    END IF;
    
END //

delimiter ;
```

Trigger 5 - Type: Before Delete

Description: Inserts a new row into the SalaryArchives table before a row from the Salaries table is deleted

Tables Creation

```sql
CEREATE TABLE Salaries(
    employeeNumber INT PRIMARY KEY,
    validFrom DATE NOT NULL,
    salary DECIMAL(12, 2) NOT NULL DEFAULT 0);

INSERT INTO salaries (employeeNumber, validFrom, salary)
VALUES
    (1002, '2000-01-01', 50000),
    (1056, '2000-01-01', 60000),
    (1076, '2000-01-01', 70000);
    
CREATE TABLE SalaryArchives(
   id INT PRIMARY KEY AUTO_INCREMENT,
   employeeNumber INT,
   validFrom DATE NOT NULL,
   salary DEC(12, 2) NOT NULL DEFAULT 0,
   deletedAt TIMESTAMP DEFAULT NOW() );
```

Creating trigger

```sql
delimiter //

CREATE TRIGGER before_salaries_delete BEFORE DELETE ON salaries FOR EACH ROW

BEGIN

    INSERT INTO SalaryArchives(employeeNumber, validFrom, salary)
    VALUES (OLD.employeeNumber, OLD.validFrom, OLD.salary);
    
END //

delimiter ;
```

Trigger 6 - Type: After Delete

Description: Updates the total salary in the Salary Budgets table after a row is deleted from the Salaries table.

Tables Creation

```sql
CREATE TABLE Salaries(
    employeeNumber INT PRIMARY KEY,
    validFrom DATE NOT NULL,
    salary DECIMAL(12, 2) NOT NULL DEFAULT 0);
    
INSERT INTO salaries(employeeNumber, validFrom, salary)
VALUES
    (1002, '2000-01-01' , 50000 ),
    (1056, '2000-01-01' , 60000 ),
    (1076, '2000-01-01' , 70000 );

CREATE TABLE SalaryBudgets(total DECIMAL(15, 2) NOT NULL);
INSERT INTO SalaryBudgets(total) SELECT SUM(salary) FROM Salaries;
```

Creating trigger

```sql
CREATE TRIGGER after_salaries_delete AFTER DELETE ON Salaries FOR EACH ROW
UPDATE SalaryBudgets SET total = total - OLD.salary;
```








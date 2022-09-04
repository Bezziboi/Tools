
<h2 align="center"><samp>MySQL Sample Database Schema</samp></h2>
<p  align="right"><a href="https://github.com/Bezziboi/Tools/blob/main/SQL/mysqlsampledatabase.sql" alt="bezziboi">SQL file</a></p>

The MySQL sample database schema consists of the following tables:

- ***Customers*** : stores customer’s data.
- ***Products*** : stores a list of scale model cars.
- ***ProductLines*** : stores a list of product line categories.
- ***Orders*** : stores sales orders placed by customers.
- ***OrderDetails*** : stores sales order line items for each sales order.
- ***Payments*** : stores payments made by customers based on their accounts.
- ***Employees*** : stores all employee information as well as the organization structure such as who reports to whom.
- ***Offices*** : stores sales office data.


<h2 align="center"> <samp> Diagram of a Database </samp></h2>
<p align="center"> <img src="https://user-images.githubusercontent.com/106346771/187048686-1f7d7b4d-e75b-4b8b-a23b-4b1a8e37c523.png"> </p>

<table>
<thead>
  <tr>
    <th>Table Name</th>
    <th>Columns</th>
    <th>Data Type &amp; Size</th>
    <th>Nulls</th>
    <th>Keys</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td rowspan="13">Customers</td>
    <td>customerNumber</td>
    <td>int</td>
    <td>NO</td>
    <td>PRI</td>
  </tr>
  <tr>
    <td>customerName</td>
    <td>varchar(50)</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>contactLastName</td>
    <td>varchar(50)</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>contactFirstName</td>
    <td>varchar(50)</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>phone</td>
    <td>varchar(50)</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>addressLine1</td>
    <td>varchar(50)</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>addressLine2</td>
    <td>varchar(50)</td>
    <td>YES</td>
    <td></td>
  </tr>
  <tr>
    <td>city</td>
    <td>varchar(50)</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>state</td>
    <td>varchar(50)</td>
    <td>YES</td>
    <td></td>
  </tr>
  <tr>
    <td>postalCode</td>
    <td>varchar(50)</td>
    <td>YES</td>
    <td></td>
  </tr>
  <tr>
    <td>country</td>
    <td>varchar(50)</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>salesRepEmployeeNumber</td>
    <td>int</td>
    <td>YES</td>
    <td>MUL</td>
  </tr>
  <tr>
    <td>creditLimit</td>
    <td>decimal(10,2)</td>
    <td>YES</td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td rowspan="8">Employees</td>
    <td>employeeNumber</td>
    <td>int</td>
    <td>NO</td>
    <td>PRI</td>
  </tr>
  <tr>
    <td>lastName</td>
    <td>varchar(50)</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>firstName</td>
    <td>varchar(50)</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>extension</td>
    <td>varchar(10)</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>email</td>
    <td>varchar(100)</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>officeCode</td>
    <td>varchar(10)</td>
    <td>NO</td>
    <td>MUL</td>
  </tr>
  <tr>
    <td>reportsTo</td>
    <td>int</td>
    <td>YES</td>
    <td>MUL</td>
  </tr>
  <tr>
    <td>jobTitle</td>
    <td>varchar(50)</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td rowspan="9">Offices</td>
    <td>officeCode</td>
    <td>varchar(10)</td>
    <td>NO</td>
    <td>PRI</td>
  </tr>
  <tr>
    <td>city</td>
    <td>varchar(50)</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>phone</td>
    <td>varchar(50)</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>addressLine1</td>
    <td>varchar(50)</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>addressLine2</td>
    <td>varchar(50)</td>
    <td>YES</td>
    <td></td>
  </tr>
  <tr>
    <td>state</td>
    <td>varchar(50)</td>
    <td>YES</td>
    <td></td>
  </tr>
  <tr>
    <td>country</td>
    <td>varchar(50)</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>postalCode</td>
    <td>varchar(15)</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>territory</td>
    <td>varchar(10)</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td rowspan="5">Orderdetails</td>
    <td>orderNumber</td>
    <td>int</td>
    <td>NO</td>
    <td>PRI</td>
  </tr>
  <tr>
    <td>productCode</td>
    <td>varchar(15)</td>
    <td>NO</td>
    <td>PRI</td>
  </tr>
  <tr>
    <td>quantityOrdered</td>
    <td>int</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>priceEach</td>
    <td>decimal(10,2)</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>orderLineNumber</td>
    <td>smallint</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td rowspan="7">Orders</td>
    <td>orderNumber</td>
    <td>int</td>
    <td>NO</td>
    <td>PRI</td>
  </tr>
  <tr>
    <td>orderDate</td>
    <td>date</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>requiredDate</td>
    <td>date</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>shippedDate</td>
    <td>date</td>
    <td>YES</td>
    <td></td>
  </tr>
  <tr>
    <td>status</td>
    <td>varchar(15)</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>comments</td>
    <td>text</td>
    <td>YES</td>
    <td></td>
  </tr>
  <tr>
    <td>customerNumber</td>
    <td>int</td>
    <td>NO</td>
    <td>MUL</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td rowspan="4">Payments</td>
    <td>customerNumber</td>
    <td>int</td>
    <td>NO</td>
    <td>PRI</td>
  </tr>
  <tr>
    <td>checkNumber</td>
    <td>varchar(50)</td>
    <td>NO</td>
    <td>PRI</td>
  </tr>
  <tr>
    <td>paymentDate</td>
    <td>date</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>amount</td>
    <td>decimal(10,2)</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td rowspan="5">ProductLines</td>
    <td>productLine</td>
    <td>varchar(50)</td>
    <td>NO</td>
    <td>PRI</td>
  </tr>
  <tr>
    <td>textDescription</td>
    <td>varchar(4000)</td>
    <td>YES</td>
    <td></td>
  </tr>
  <tr>
    <td>htmlDescription</td>
    <td>mediumtext</td>
    <td>YES</td>
    <td></td>
  </tr>
  <tr>
    <td>image</td>
    <td>mediumblob</td>
    <td>YES</td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td rowspan="9">Products</td>
    <td>productCode</td>
    <td>varchar(15)</td>
    <td>NO</td>
    <td>PRI</td>
  </tr>
  <tr>
    <td>productName</td>
    <td>varchar(70)</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>productLine</td>
    <td>varchar(50)</td>
    <td>NO</td>
    <td>MUL</td>
  </tr>
  <tr>
    <td>productScale</td>
    <td>varchar(10)</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>productVendor</td>
    <td>varchar(50)</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>productDescription</td>
    <td>text</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>quantityInStock</td>
    <td>smallint</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>buyPrice</td>
    <td>decimal(10,2)</td>
    <td>NO</td>
    <td></td>
  </tr>
  <tr>
    <td>MSRP</td>
    <td>decimal(10,2)</td>
    <td>NO</td>
    <td></td>
  </tr>
</tbody>
</table>

<h3 align="left"> <samp>First test case</samp></h3>

<p align="left"><a href="https://docs.google.com/spreadsheets/d/1y8sfJ_DfzmsGN_hqNbh_CuOMRpCBHd9OMoQ3X4cHtUY/edit?usp=sharing">Click to open Google sheets for better view</a></p>

<p align="center"> <img src="https://user-images.githubusercontent.com/106346771/187746724-8abc0110-10a4-456b-b8fe-44bbc11ca5ca.png"> </p>



<h2 align="center"> <samp>Stored Procedure</samp></h2>

<h3 align="left"> <samp>Common Test Scenarios for Stored Procedure</samp></h3>

1) **Check Stored Procedure exist in database**
2) **Check stored procedure with valid input data**
3) **Check stored procedure handle exceptions when you pass invalid input data**
4) **Check stored procedure display results as expected**
5) **Check stored procedure inserting data in proper table/s**
6) **Check stored procedure updating data in proper table/s**
7) **Check stored procedure deleting data from proper table/s**
8) **Check calling stored procedure from another stored procedure**

<h3 align="left"> <samp>So let's create some simple Stored Procedures</samp></h3>

<h3 align="left"> <samp>Stored Procedure 1:</samp></h3>
<table>
<tbody>
  <tr>
    <td width="200px">Stored procedure Name</td>
    <td width="600px">SelectAllCustomers</td>
  </tr>
  <tr>
    <td>Description</td>
    <td>selects all records from the "Customers" table </td>
  </tr>
  <tr>
    <td>Input Parameters</td>
    <td>NA</td>
  </tr>
  <tr>
    <td>Output Parameters</td>
    <td>NA</td>
  </tr>
</tbody>
</table>

```sql
delimiter //

CREATE PROCEDURE SelectAllCustomers()
 BEGIN
    select * from customers;
 END //

delimiter ;
```

<h3 align="left"> <samp>Stored Procedure 2:</samp></h3>
<table>
<tbody>
  <tr>
    <td width="200px">Stored procedure Name</td>
    <td width="600px">SelectAllCustomersByCity</td>
  </tr>
  <tr>
    <td>Description</td>
    <td>selects Customers from a particular City from the " Customers " table</td>
  </tr>
  <tr>
    <td>Input Parameters</td>
    <td>cityName</td>
  </tr>
  <tr>
    <td>Output Parameters</td>
    <td>NA</td>
  </tr>
</tbody>
</table>

```sql
delimiter //
         
CREATE PROCEDURE SelectAllCustomersByCity(IN mycity varchar(50))
 BEGIN
     SELECT * FROM customers WHERE city = mycity;
 END //

delimiter;
```

<h3 align="left"> <samp>Stored Procedure 3:</samp></h3>
<table>
<tbody>
  <tr>
    <td width="200px">Stored procedure Name</td>
    <td width="600px">SelectAllCustomersByCityAndPin</td>
  </tr>
  <tr>
    <td>Description</td>
    <td>selects Customers from a particular City with a particular PostalCode  <br>from the " Customers " table</td>
  </tr>
  <tr>
    <td>Input Parameters</td>
    <td>cityName, PostalCode</td>
  </tr>
  <tr>
    <td>Output Parameters</td>
    <td>NA</td>
  </tr>
</tbody>
</table>

```sql
delimiter //

CREATE PROCEDURE SelectAllCustomersByCityAndPin(IN mycity varchar(50), IN pcode varchar(15))
 BEGIN
     SELECT * FROM customers WHERE city = mycity AND postalCode = pcode;
 END //
 
delimiter ;
```

<h3 align="left"> <samp>Stored Procedure 4:</samp></h3>
<table>
<tbody>
  <tr>
    <td width="200px">Stored procedure Name</td>
    <td width="600px">get_order_by_cust</td>
  </tr>
  <tr>
    <td>Description</td>
    <td>accepts customer number and returns the total number of orders that<br>were shipped , canceled , resolved , and disputed.<br></td>
  </tr>
  <tr>
    <td>Input Parameters</td>
    <td>custNo</td>
  </tr>
  <tr>
    <td>Output Parameters</td>
    <td>shipped, canceled, resolved, disputed</td>
  </tr>
</tbody>
</table>

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
```



<h3 align="left"> <samp>Stored Procedure 5:</samp></h3>
<table>
<tbody>
  <tr>
    <td width="200px">Stored procedure Name</td>
    <td width="600px">GetCustomerShipping</td>
  </tr>
  <tr>
    <td>Description</td>
    <td>Return the shipping time based on the country of the customer . If the<br>customer locates in USA , the shipping time is 2 - day shipping . If the<br>customer locates in Canada , the shipping time is 3 - day shipping . The<br>customers from other countries have 5 - day shipping .</td>
  </tr>
  <tr>
    <td>Input Parameters</td>
    <td>custNo</td>
  </tr>
  <tr>
    <td>Output Parameters</td>
    <td>shipping Time</td>
  </tr>
</tbody>
</table>

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
        
        -- if customer country 'Canada' set '3-day Shipping'
        WHEN 'Canada' THEN
            SET pShipping = '3-day Shipping';
            
        -- else set '5-day Shipping'    
        ELSE
            SET pShipping = '5-day Shipping';
        END CASE;
        
 END //
 
delimiter ;
```

<h3 align="left"> <samp> Second test case : Stored procedure </samp></h3>
<p align="left"><a href="https://docs.google.com/spreadsheets/d/17rL3kR7YtHFyX3kLhEtNsh_Wy7WIIGT0gDcQUefwuRA/edit?usp=sharing">Click to open Google sheets for better view</a></p>

<p align="center"> <img src="https://user-images.githubusercontent.com/106346771/187744028-fa2684a8-9d0d-44fc-86bf-3035d8d86509.png"> </p>


<h2 align="center"> <samp>Stored Function</samp></h2>

<h3 align="left"> <samp>Common Test Scenarios for Stored Function</samp></h3>

1) **Check Stored Function exist in database**
2) **Check Stored Function with valid input data**
3) **Check Stored Function handle exceptions when you pass invalid input data**
4) **Check Stored Function returns results as expected**
5) **Check Stored Function not used insert/update/delete operations**
6) **Check Stored Function used only select statements**
7) **Check calling Stored Function from stored procedure**

<h3 align="left"> <samp>Let's create some simple Stored Function</samp></h3>

<table>
<tbody>
  <tr>
    <td width="200px">Stored Function Name</td>
    <td width="600px">CustomerLevel</td>
  </tr>
  <tr>
    <td>Description</td>
    <td>Returns the customer level based on creditLimit</td>
  </tr>
  <tr>
    <td>Input Parameters</td>
    <td>creditLimit</td>
  </tr>
  <tr>
    <td>Output Parameters</td>
    <td>CustomerLevel</td>
  </tr>
</tbody>
</table>


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

<h3 align="left"> <samp> Third test case : Stored function </samp></h3>

<p align="left"><a href="https://docs.google.com/spreadsheets/d/1sudO3v3yAsqIqXw2fMDVC-OOZ9jte_AmscULG975ZVY/edit?usp=sharing">Click to open Google sheets for better view</a></p>

<p align="center"> <img src="https://user-images.githubusercontent.com/106346771/188014871-ee272ef6-24df-424c-a34a-870633626f21.png"> </p>


<h2 align="center"> <samp>Trigger Testing</samp> </h2>

### Trigger #1
<table>
<tbody>
  <tr>
    <td width="200px">Trigger Name</td>
    <td width="600px">before_workcenters_insert</td>
  </tr>
  <tr>
    <td>Trigger Type</td>
    <td>Before Insert</td>
  </tr>
  <tr>
    <td>Description</td>
    <td>Updates the total capacity in the WorkCenterStats table before a new work center is inserted into the WorkCenter table:</td>
  </tr>
  <tr>
    <td>Tables</td>
    <td>WorkCenters</br> WorkCenterStats</td>
  </tr>
</tbody>
</table>

Lets's create table and trigger

Tables Creation

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

#### Test case #1

<table>
<thead>
  <tr>
    <th colspan="2">Testing trigger</th>
    <th>Trigger 1-Type: Before Insert</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Steps</td>
    <td>Description &amp; Query</td>
    <td>Expected Result</td>
  </tr>
  <tr>
    <td>Step1</td>
    <td  width="500px">Insert a new row into WorkCenters table:<br><br>INSERT INTO WorkCenters(name, capacity)<br>VALUES('Mold Machine', 100);</td>
    <td  width="500px">NA</td>
  </tr>
  <tr>
    <td>Step2</td>
    <td>Query data from the WorkCenterStats table:<br><br>SELECT * FROM WorkCenterstats;</td>
    <td>totalCapacity<br>100</td>
  </tr>
  <tr>
    <td>Step3</td>
    <td>Insert a new work center:<br><br>INSERT INTO WorkCenters(name, capacity)<br>VALUES('Packing', 200);</td>
    <td>NA</td>
  </tr>
  <tr>
    <td>Step4</td>
    <td>Finally query data from the WorkCenterStats table<br><br>SELECT * FROM WorkCenterStats;</td>
    <td>totalCapacity<br>300</td>
  </tr>
</tbody>
</table>

### Trigger #2

<table>
<tbody>
  <tr>
    <td width="200px">Trigger Name</td>
    <td width="600px">after_members_insert</td>
  </tr>
  <tr>
    <td>Trigger Type</td>
    <td>After Insert</td>
  </tr>
  <tr>
    <td>Description</td>
    <td>Inserts a reminder into the reminders table if the birth date of the member is NULL</td>
  </tr>
  <tr>
    <td>Tables</td>
    <td>members</br> reminders</td>
  </tr>
</tbody>
</table>

Lets's create table and trigger

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

#### Test case #2

<table>
<thead>
  <tr>
    <th colspan="2">Testing trigger<br></th>
    <th>Trigger 2-Type: After Insert</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Steps</td>
    <td>Description &amp; Query</td>
    <td>Expected Result</td>
  </tr>
  <tr>
    <td>Step1</td>
    <td width="500px">Insert 2 rows into members table:<br><br>INSERT INTO members(name, email, birthDate)<br>VALUES('Bezzi', 'bezzi@example.com', NULL);<br>INSERT INTO members(name, email, birthDate)<br>VALUES('Begli', 'begli@example.com', '1999-03-06');</td>
    <td width="500px">NA</td>
  </tr>
  <tr>
    <td>Step2</td>
    <td>Query data from the members table:<br><br>SELECT * FROM members;</td>
    <td>Table should contain 2 records, one of the record birthdate value should be NULL.</td>
  </tr>
  <tr>
    <td>Step3</td>
    <td>Finally query data from the reminders table:<br><br>SELECT * FROM reminders;</td>
    <td>Message<br><br>Hi Bezzi, please update your date of birth.</td>
  </tr>
</tbody>
</table>


### Trigger #3

<table>
<tbody>
  <tr>
    <td width="200px">Trigger Name</td>
    <td width="600px">before_sales_update</td>
  </tr>
  <tr>
    <td>Trigger Type</td>
    <td>Before Update</td>
  </tr>
  <tr>
    <td>Description</td>
    <td>If you update the value in the quantity column to a new value that is 3 times greater than the current value, the trigger raises an error and stops the update</td>
  </tr>
  <tr>
    <td>Tables</td>
    <td>sales</td>
  </tr>
</tbody>
</table>

Lets's create table and trigger

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

#### Test case #3

<table>
<thead>
  <tr>
    <th colspan="2">Testing trigger<br></th>
    <th>Trigger 3 - Type: Before Update</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Steps</td>
    <td>Description &amp; Query</td>
    <td>Expected Result</td>
  </tr>
  <tr>
    <td>Step1</td>
    <td>Update the quantity of the row with id 1 to 150<br> UPDATE sales SET quantity = 150 WHERE id = 1;<br><br>Query data from the sales table to verify update<br> SELECT * FROM sales;</td>
    <td>It should update sales table because the new quantity does not violate the rule.</td>
  </tr>
  <tr>
    <td>Step2</td>
    <td>Update the quantity of the row with id 1 to 500<br><br>UPDATE sales SET quantity = 500 WHERE id = 1;</td>
    <td>Error Code : 1644. The new quantity 500 cannot be 3 times greater than the current quantity 150.<br><br>In this case, the trigger should found the new quantity caused a violation and raised an error.</td>
  </tr>
</tbody>
</table>


### Trigger #4

<table>
<tbody>
  <tr>
    <td width="200px">Trigger Name</td>
    <td width="600px">after_sales_update</td>
  </tr>
  <tr>
    <td>Trigger Type</td>
    <td>After Update</td>
  </tr>
  <tr>
    <td>Description</td>
    <td>If you update the value in the quantity column to a new value the trigger insert a new row to log the changes in the SalesChanges table</td>
  </tr>
  <tr>
    <td>Tables</td>
    <td>Sales</br>SalesChanges</td>
  </tr>
</tbody>
</table>

Lets's create table and trigger

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

#### Test case #4

<table>
<thead>
  <tr>
    <th colspan="2">Testing trigger<br></th>
    <th>Trigger 4-Type: After Update</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Steps</td>
    <td>Description &amp; Query</td>
    <td>Expected Result</td>
  </tr>
  <tr>
    <td>Step1</td>
    <td>Update the quantity of the row with id 1 to 350<br> UPDATE sales SET quantity = 350 WHERE id = 1;<br><br>Query data from the SalesChanges table to verify update<br> SELECT * FROM SalesChanges;</td>
    <td>The trigger should triggered automatically.</td>
  </tr>
  <tr>
    <td>Step2</td>
    <td>Update the quantity of all 3 rows by increasing 10%<br><br>UPDATE Sales SET quantity = CAST(quantity * 1.1 AS UNSIGNED);</td>
    <td>NA</td>
  </tr>
  <tr>
    <td>Step3</td>
    <td>Query data from the SalesChanges table<br><br>SELECT * FROM SalesChanges;</td>
    <td>The trigger should fire three times because of the updates of the three rows</td>
  </tr>
</tbody>
</table>


### Trigger #5

<table>
<tbody>
  <tr>
    <td width="200px">Trigger Name</td>
    <td width="600px">before_salaries_delete</td>
  </tr>
  <tr>
    <td>Trigger Type</td>
    <td>Before Delete</td>
  </tr>
  <tr>
    <td>Description</td>
    <td>Inserts a new row into the SalaryArchives table before a row from the Salaries table is deleted</td>
  </tr>
  <tr>
    <td>Tables</td>
    <td>salaries</br>SalaryArchives</td>
  </tr>
</tbody>
</table>

Lets's create table and trigger

Tables Creation

```sql
CEREATE TABLE Salaries(
    employeeNumber INT PRIMARY KEY,
    validFrom DATE NOT NULL,
    salary DECIMAL(12, 2) NOT NULL DEFAULT 0);

INSERT INTO salaries(employeeNumber, validFrom, salary)
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

#### Test case #5

<table>
<thead>
  <tr>
    <th colspan="2">Testing trigger<br></th>
    <th>Trigger 5-Type: Before Delete</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Steps</td>
    <td>Description &amp; Query</td>
    <td>Expected Result</td>
  </tr>
  <tr>
    <td>Step1</td>
    <td>Delete the row from salaries table<br>DELETE FROM salaries WHERE employeeNumber = 1002;<br><br>Query the data from SalaryArchives table<br>SELECT * FROM SalaryArchives;<br></td>
    <td>The trigger should invoke and insert a new row into the SalaryArchives table</td>
  </tr>
  <tr>
    <td>Step2</td>
    <td>Delete all the rows from salaries table<br>DELETE FROM salaries;<br><br>Finally, query the data from SalaryArchives table<br>SELECT * FROM SalaryArchives;</td>
    <td>The trigger should trigger 2 times because the DELETE statement deleted two rows from the Salaries table</td>
  </tr>
</tbody>
</table>

### Trigger #6

<table>
<tbody>
  <tr>
    <td width="200px">Trigger Name</td>
    <td width="600px">after_salaries_delete</td>
  </tr>
  <tr>
    <td>Trigger Type</td>
    <td>After Delete</td>
  </tr>
  <tr>
    <td>Description</td>
    <td>Updates the total salary in the Salary Budgets table after a row is deleted from the Salaries table</td>
  </tr>
  <tr>
    <td>Tables</td>
    <td>Salaries</br>SalaryBudgets</td>
  </tr>
</tbody>
</table>

Lets's create table and trigger

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

#### Test case #6

<table>
<thead>
  <tr>
    <th colspan="2">Testing trigger<br></th>
    <th>Trigger 6-Type: After Delete</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Steps</td>
    <td>Description &amp; Query</td>
    <td>Expected Result</td>
  </tr>
  <tr>
    <td>Step1</td>
    <td>Delete the row from salaries table<br>DELETE FROM salaries WHERE employeeNumber = 1002;<br><br>Query salary from SalaryBudgets table<br>SELECT * FROM SalaryBudgets;</td>
    <td>In the output, the total should be reduced by the deleted salary</td>
  </tr>
  <tr>
    <td>Step2</td>
    <td>Delete all the rows from salaries table<br>DELETE FROM salaries;<br><br>Finally, query the total from SalaryBudgets table<br>SELECT * FROM SalaryBudgets;</td>
    <td>The trigger updated the total to zero</td>
  </tr>
</tbody>
</table>

<p align="left"><a href="https://docs.google.com/spreadsheets/d/1wGYzBTkbPWNhe6Ugw65Peu3IvHq-w8YsNqPSmONbado/edit?usp=sharing">⬆ Click to open all Trigger test cases in Google sheets for better view</a></p>

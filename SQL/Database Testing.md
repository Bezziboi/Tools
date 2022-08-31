
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

<table class="tg">
<thead>
  <tr>
    <th class="tg-0pky">Table Name</th>
    <th class="tg-0pky">Columns</th>
    <th class="tg-0pky">Data Type &amp; Size</th>
    <th class="tg-0pky">Nulls</th>
    <th class="tg-0pky">Keys</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-buh4"></td>
    <td class="tg-btxf"></td>
    <td class="tg-btxf"></td>
    <td class="tg-btxf"></td>
    <td class="tg-btxf"></td>
  </tr>
  <tr>
    <td class="tg-7btt" rowspan="13">Customers</td>
    <td class="tg-0pky">customerNumber</td>
    <td class="tg-0pky">int</td>
    <td class="tg-0pky">NO</td>
    <td class="tg-0pky">PRI</td>
  </tr>
  <tr>
    <td class="tg-btxf">customerName</td>
    <td class="tg-btxf">varchar(50)</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf"></td>
  </tr>
  <tr>
    <td class="tg-0pky">contactLastName</td>
    <td class="tg-0pky">varchar(50)</td>
    <td class="tg-0pky">NO</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-btxf">contactFirstName</td>
    <td class="tg-btxf">varchar(50)</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf"></td>
  </tr>
  <tr>
    <td class="tg-0pky">phone</td>
    <td class="tg-0pky">varchar(50)</td>
    <td class="tg-0pky">NO</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-btxf">addressLine1</td>
    <td class="tg-btxf">varchar(50)</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf"></td>
  </tr>
  <tr>
    <td class="tg-0pky">addressLine2</td>
    <td class="tg-0pky">varchar(50)</td>
    <td class="tg-0pky">YES</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-btxf">city</td>
    <td class="tg-btxf">varchar(50)</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf"></td>
  </tr>
  <tr>
    <td class="tg-0pky">state</td>
    <td class="tg-0pky">varchar(50)</td>
    <td class="tg-0pky">YES</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-btxf">postalCode</td>
    <td class="tg-btxf">varchar(50)</td>
    <td class="tg-btxf">YES</td>
    <td class="tg-btxf"></td>
  </tr>
  <tr>
    <td class="tg-0pky">country</td>
    <td class="tg-0pky">varchar(50)</td>
    <td class="tg-0pky">NO</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-btxf">salesRepEmployeeNumber</td>
    <td class="tg-btxf">int</td>
    <td class="tg-btxf">YES</td>
    <td class="tg-btxf">MUL</td>
  </tr>
  <tr>
    <td class="tg-0pky">creditLimit</td>
    <td class="tg-0pky">decimal(10,2)</td>
    <td class="tg-0pky">YES</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-btxf"></td>
    <td class="tg-btxf"></td>
    <td class="tg-btxf"></td>
    <td class="tg-btxf"></td>
    <td class="tg-btxf"></td>
  </tr>
  <tr>
    <td class="tg-7btt" rowspan="8">Employees</td>
    <td class="tg-0pky">employeeNumber</td>
    <td class="tg-0pky">int</td>
    <td class="tg-0pky">NO</td>
    <td class="tg-0pky">PRI</td>
  </tr>
  <tr>
    <td class="tg-btxf">lastName</td>
    <td class="tg-btxf">varchar(50)</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf"></td>
  </tr>
  <tr>
    <td class="tg-0pky">firstName</td>
    <td class="tg-0pky">varchar(50)</td>
    <td class="tg-0pky">NO</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-btxf">extension</td>
    <td class="tg-btxf">varchar(10)</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf"></td>
  </tr>
  <tr>
    <td class="tg-0pky">email</td>
    <td class="tg-0pky">varchar(100)</td>
    <td class="tg-0pky">NO</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-btxf">officeCode</td>
    <td class="tg-btxf">varchar(10)</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf">MUL</td>
  </tr>
  <tr>
    <td class="tg-0pky">reportsTo</td>
    <td class="tg-0pky">int</td>
    <td class="tg-0pky">YES</td>
    <td class="tg-0pky">MUL</td>
  </tr>
  <tr>
    <td class="tg-btxf">jobTitle</td>
    <td class="tg-btxf">varchar(50)</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf"></td>
  </tr>
  <tr>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-zwlc" rowspan="9">Offices</td>
    <td class="tg-btxf">officeCode</td>
    <td class="tg-btxf">varchar(10)</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf">PRI</td>
  </tr>
  <tr>
    <td class="tg-0pky">city</td>
    <td class="tg-0pky">varchar(50)</td>
    <td class="tg-0pky">NO</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-btxf">phone</td>
    <td class="tg-btxf">varchar(50)</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf"></td>
  </tr>
  <tr>
    <td class="tg-0pky">addressLine1</td>
    <td class="tg-0pky">varchar(50)</td>
    <td class="tg-0pky">NO</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-btxf">addressLine2</td>
    <td class="tg-btxf">varchar(50)</td>
    <td class="tg-btxf">YES</td>
    <td class="tg-btxf"></td>
  </tr>
  <tr>
    <td class="tg-0pky">state</td>
    <td class="tg-0pky">varchar(50)</td>
    <td class="tg-0pky">YES</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-btxf">country</td>
    <td class="tg-btxf">varchar(50)</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf"></td>
  </tr>
  <tr>
    <td class="tg-0pky">postalCode</td>
    <td class="tg-0pky">varchar(15)</td>
    <td class="tg-0pky">NO</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-btxf">territory</td>
    <td class="tg-btxf">varchar(10)</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf"></td>
  </tr>
  <tr>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-if4e" rowspan="5">Orderdetails</td>
    <td class="tg-btxf">orderNumber</td>
    <td class="tg-btxf">int</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf">PRI</td>
  </tr>
  <tr>
    <td class="tg-0pky">productCode</td>
    <td class="tg-0pky">varchar(15)</td>
    <td class="tg-0pky">NO</td>
    <td class="tg-0pky">PRI</td>
  </tr>
  <tr>
    <td class="tg-btxf">quantityOrdered</td>
    <td class="tg-btxf">int</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf"></td>
  </tr>
  <tr>
    <td class="tg-0pky">priceEach</td>
    <td class="tg-0pky">decimal(10,2)</td>
    <td class="tg-0pky">NO</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-btxf">orderLineNumber</td>
    <td class="tg-btxf">smallint</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf"></td>
  </tr>
  <tr>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-zwlc" rowspan="7">Orders</td>
    <td class="tg-btxf">orderNumber</td>
    <td class="tg-btxf">int</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf">PRI</td>
  </tr>
  <tr>
    <td class="tg-0pky">orderDate</td>
    <td class="tg-0pky">date</td>
    <td class="tg-0pky">NO</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-btxf">requiredDate</td>
    <td class="tg-btxf">date</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf"></td>
  </tr>
  <tr>
    <td class="tg-0pky">shippedDate</td>
    <td class="tg-0pky">date</td>
    <td class="tg-0pky">YES</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-btxf">status</td>
    <td class="tg-btxf">varchar(15)</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf"></td>
  </tr>
  <tr>
    <td class="tg-0pky">comments</td>
    <td class="tg-0pky">text</td>
    <td class="tg-0pky">YES</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-btxf">customerNumber</td>
    <td class="tg-btxf">int</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf">MUL</td>
  </tr>
  <tr>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-zwlc" rowspan="4">Payments</td>
    <td class="tg-btxf">customerNumber</td>
    <td class="tg-btxf">int</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf">PRI</td>
  </tr>
  <tr>
    <td class="tg-0pky">checkNumber</td>
    <td class="tg-0pky">varchar(50)</td>
    <td class="tg-0pky">NO</td>
    <td class="tg-0pky">PRI</td>
  </tr>
  <tr>
    <td class="tg-btxf">paymentDate</td>
    <td class="tg-btxf">date</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf"></td>
  </tr>
  <tr>
    <td class="tg-0pky">amount</td>
    <td class="tg-0pky">decimal(10,2)</td>
    <td class="tg-0pky">NO</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-btxf"></td>
    <td class="tg-btxf"></td>
    <td class="tg-btxf"></td>
    <td class="tg-btxf"></td>
    <td class="tg-btxf"></td>
  </tr>
  <tr>
    <td class="tg-7btt" rowspan="5">ProductLines</td>
    <td class="tg-0pky">productLine</td>
    <td class="tg-0pky">varchar(50)</td>
    <td class="tg-0pky">NO</td>
    <td class="tg-0pky">PRI</td>
  </tr>
  <tr>
    <td class="tg-btxf">textDescription</td>
    <td class="tg-btxf">varchar(4000)</td>
    <td class="tg-btxf">YES</td>
    <td class="tg-btxf"></td>
  </tr>
  <tr>
    <td class="tg-0pky">htmlDescription</td>
    <td class="tg-0pky">mediumtext</td>
    <td class="tg-0pky">YES</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-btxf">image</td>
    <td class="tg-btxf">mediumblob</td>
    <td class="tg-btxf">YES</td>
    <td class="tg-btxf"></td>
  </tr>
  <tr>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-zwlc" rowspan="9">Products</td>
    <td class="tg-btxf">productCode</td>
    <td class="tg-btxf">varchar(15)</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf">PRI</td>
  </tr>
  <tr>
    <td class="tg-0pky">productName</td>
    <td class="tg-0pky">varchar(70)</td>
    <td class="tg-0pky">NO</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-btxf">productLine</td>
    <td class="tg-btxf">varchar(50)</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf">MUL</td>
  </tr>
  <tr>
    <td class="tg-0pky">productScale</td>
    <td class="tg-0pky">varchar(10)</td>
    <td class="tg-0pky">NO</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-btxf">productVendor</td>
    <td class="tg-btxf">varchar(50)</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf"></td>
  </tr>
  <tr>
    <td class="tg-0pky">productDescription</td>
    <td class="tg-0pky">text</td>
    <td class="tg-0pky">NO</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-btxf">quantityInStock</td>
    <td class="tg-btxf">smallint</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf"></td>
  </tr>
  <tr>
    <td class="tg-0pky">buyPrice</td>
    <td class="tg-0pky">decimal(10,2)</td>
    <td class="tg-0pky">NO</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-btxf">MSRP</td>
    <td class="tg-btxf">decimal(10,2)</td>
    <td class="tg-btxf">NO</td>
    <td class="tg-btxf"></td>
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
5) **Check stored procedure inserting data in proper table / s**
6) **Check stored procedure updating data in proper table / s**
7) **Check stored procedure deleting data from proper table / s**
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



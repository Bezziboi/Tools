
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

<h2 align="center"> <samp>Test Cases</samp></h2>



<p align="center"> <a href="https://github.com/Bezziboi/Tools/blob/main/checkLists%20%26%20testCases/SQL%20testCase_1.png" > <img src="https://user-images.githubusercontent.com/106346771/187048080-a4c6f44e-ef45-403c-96f7-4240afbd7920.png"> </a> </p>

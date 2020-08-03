# 1. Ink Cartridge Regeneration [ICR] 2.0 </br> 
Project of ink cartridge regeneration service database, which is built on Microsoft SQL Server 2014.  </br> 
## 1.1 Database description </br> 
The project is a relational database written for Microsoft SQL Server 2014, which contains <i>8 tables</i> related to the activity of <b>ink cartridge regeneration service.</b></br> The service is the regeneration of selected original HP ink cartridges. The database contains information about the customer who places the order, the order and its details, order give away and payment.</br>

The database provides access to data on: </br>
- customer data </br>
- data on the subject of the order placed </br>
- data on the stock release status of the regenerated carcasses </br>
- payment details </br>

Assumptions: </br>
- the complete order is issued no later than 3 days from the date of placing the order </br>
- payment methods are cash or bank transfer </br>
- only the types of carcasses from the offer are subject to regeneration (table "product") </br>

## 2. Description of the tables </br>
- <i>tb_customers:</i> the table contains the personal data of the customers placing the order. </br>

- <i>tb_orders:</i> the table contains data on the date of placing the order, id of the employee accepting the order and the id of the customer placing the order. </br>

- <i>tb_order_details:</i> the table contains data such as order id, quantity and type of product to be regenerated. </br>

- <i>tb_employees:</i> the table contains the first name, surname and id of a given employee. </br> 

- <i>tb_product:</i> the table contains the product type, ink color, unit price for the regeneration of a given type of ink cartridge. </br>

- <i>tb_give_away:</i> the table contains data on the date of give away of the regenerated ink cartridges, the number of cartridges gaven away and the id of the order to which the give away service relates. </br>

- <i>tb_printers:</i> the table contains data on the types of printers that support a given type of cartridge. </br>

- <i>tb_payments:</i> the table contains data on the customer to whom the payment relates, order id, date of payment and its value, as well as the type of payment selected by the customer. </br>

## 3. Columns in a tables and their data types </br>

### 3.1 tb_customers </br>

<table>
  <tr>
    <th> Column Name </th>
    <th>Data Type </th>
    </tr>
  <tr>
    <td>id_customers</td>
    <td>int, PK</td>
  </tr>
  <tr>
    <td>first_name</td>
    <td>varchar(255)</td>
  </tr>
    <td>last_name</td>
    <td>varchar(255)</td>
  </tr>
  <tr>
   <td>city</td>
   <td>varchar(100)</td>
  </tr>
  <tr>
   <td>street</td>
   <td>varchar(100)</td>
  </tr>
  <tr>
    <td>street_number</td>
    <td>int</td>
  </tr>
  <tr>
  <td>apartament</td>
  <td>int</td>
  </tr>
  </table> 

### 3.2 tb_orders </br>

<table>
  <tr>
    <th> Column Name </th>
    <th>Data Type </th>
    </tr>
  <tr>
    <td>id_orders</td>
    <td>int, PK</td>
  </tr>
  <tr>
    <td>id_customer</td>
    <td>int, FK</td>
  </tr>
  <tr>
    <td>order_date</td>
    <td>datetime</td>
  </tr>
  <tr>
    <td>id_recipient_of_order</td>
    <td>int, FK</td>
  </tr>
 </table>
  
 ### 3.3 tb_order_details </br>
 
 <table>
  <tr>
    <th> Column Name </th>
    <th>Data Type </th>
    </tr>
  <tr>
    <td>id_order</td>
    <td>int, FK</td>
  </tr>
  <tr>
    <td>id_order_details</td>
    <td>int, PK</td>
  </tr>
  <tr>
    <td>cartridge_quantity</td>
    <td>int</td>
  </tr>
  <tr>
    <td>id_product_d</td>
    <td>int, FK</td>
  </tr>
 </table>
  
### 3.4 tb_employees </br>
 
 <table>
  <tr>
    <th> Column Name </th>
    <th>Data Type </th>
    </tr>
  <tr>
    <td>id_employees</td>
    <td>int, PK</td>
  </tr>
  <tr>
    <td>e_first_name</td>
    <td>varchar(50)</td>
  </tr>
  <tr>
    <td>e_last_name</td>
    <td>varchar(50)</td>
  </tr>
 </table>
  
  ### 3.5 tb_product </br>
 
 <table>
  <tr>
    <th> Column Name </th>
    <th>Data Type </th>
    </tr>
  <tr>
    <td>id_products</td>
    <td>int, PK</td>
  </tr>
  <tr>
    <td>product_code</td>
    <td>varchar(30)</td>
  </tr>
  <tr>
    <td>ink_color</td>
    <td>varchar(30)</td>
  </tr>
  <tr>
    <td>price_pcs</td>
    <td>money</td>
  </tr>
 </table>
  
  ### 3.6 tb_give_away </br>
 
 <table>
  <tr>
    <th> Column Name </th>
    <th>Data Type </th>
    </tr>
  <tr>
    <td>id_ga</td>
    <td>int, PK</td>
  </tr>
  <tr>
    <td>id_order</td>
    <td>int, FK</td>
  </tr>
  <tr>
    <td>gave_away_quantity</td>
    <td>int</td>
  </tr>
  <tr>
    <td>id_product</td>
    <td>int, FK</td>
  </tr>
 </table>
      
   ### 3.7 tb_printers </br>
 
 <table>
  <tr>
    <th> Column Name </th>
    <th>Data Type </th>
    </tr>
  <tr>
    <td>id_printers</td>
    <td>int, PK</td>
  </tr>
  <tr>
    <td>printer_name</td>
    <td>varchar(255)</td>
  </tr>
  <tr>
    <td>id_product_p</td>
    <td>int, FK</td>
  </tr>
 </table>
  
   ### 3.8 tb_payments </br>
 
 <table>
  <tr>
    <th> Column Name </th>
    <th>Data Type </th>
    </tr>
  <tr>
    <td>id_payments</td>
    <td>int, PK</td>
  </tr>
  <tr>
    <td>id_customer_p</td>
    <td>int, FK</td>
  </tr>
  <tr>
    <td>id_orders_p</td>
    <td>int, FK</td>
  </tr>
  <tr>
    <td>total_cost</td>
    <td>money</td>
  </tr>
  <tr>
    <td>pay_date</td>
    <td>datetime</td>
  </tr>
  <tr>
    <td>pay_way</td>
    <td>varchar(10)</td>
  </tr>
 </table>
  
  ## 4. SQL code for database structure
  
### 4.1 tb_customers </br>

CREATE TABLE customers </br>
( </br>
id_customers int IDENTITY(1,1) PRIMARY KEY, </br>
first_name varchar(255), </br>
last_name varchar(255), </br>
city varchar(100), </br>
street varchar(100), </br>
street_number int, </br>
apartment_number int</br>
)</br>

### 4.2 tb_orders </br>

CREATE TABLE orders </br>
(</br>
id_orders int IDENTITY(1,1) PRIMARY KEY,</br>
id_customer int FOREIGN KEY REFERENCES customers(id_customers), </br>
order_date DATETIME, </br>
id_recipient_of_order int FOREIGN KEY REFERENCES employees(id_employees)</br>
)</br>

### 4.3 tb_order_details </br>

CREATE TABLE order_details </br>
(</br>
id_order int FOREIGN KEY REFERENCES orders(id_orders), </br>
id_order_details int IDENTITY(1,1) PRIMARY KEY, </br>
cartridge_quantity int CHECK(cartridge_quantity>0), </br>
id_product_d int FOREIGN KEY REFERENCES product(id_products)</br>
)</br>

### 4.4 tb_employees </br>

CREATE TABLE employees </br>
(</br>
id_employees int IDENTITY(1,1) PRIMARY KEY, </br>
e_first_name varchar(50),</br>
e_last_name VARCHAR(50)</br>
)</br>

### 4.5 tb_product </br>

CREATE TABLE product </br>
(</br>
id_products int IDENTITY(1,1) PRIMARY KEY, </br>
product_code varchar(30), </br>
ink_color varchar(30), </br>
price_pcs MONEY</br>
)</br>

### 4.6 tb_give_away </br>

CREATE TABLE give_away </br>
(</br>
id_ga int IDENTITY(1,1) PRIMARY KEY, </br>
id_order int FOREIGN KEY REFERENCES orders(id_orders), </br>
gave_away_quantity int, </br>
id_product int FOREIGN KEY REFERENCES product(id_products), </br>
gave_away_date DATETIME</br>
)</br>

### 4.7 tb_printers </br>

CREATE TABLE printers </br>
(</br>
id_printers int IDENTITY(1,1) PRIMARY KEY, </br>
printer_name varchar(255), </br>
id_product_p int FOREIGN KEY REFERENCES product(id_products)</br>
)</br>

### 4.8 tb_payments </br>

CREATE TABLE payments </br>
(</br>
id_payments int IDENTITY(1,1) PRIMARY KEY, </br>
id_customer_p int FOREIGN KEY REFERENCES customers(id_customers),</br>
id_orders_p int FOREIGN KEY REFERENCES orders(id_orders), </br>
total_cost MONEY, </br>
pay_date DATETIME, </br>
pay_way VARCHAR(10)</br>
)</br>
  
## 5. Main database relations diagram 
<img src="https://user-images.githubusercontent.com/59047042/87777158-48ded980-c829-11ea-8d0e-dda1280ad530.jpg">

## 6. Views code and description

### 6.1 Payments status

<b>Desribe:</b> the view shows the current payment status for a given order.

<b>Code:</b></br>
CREATE VIEW payments_status </br>
AS </br>
SELECT o.id_orders AS 'ORDER_ID',  </br>
o.order_date AS 'DATE OF ORDER' , </br>
p.pay_way AS 'PAY WAY CHOOSEN BY CUSTOMER',  </br>
	CASE  </br>
		WHEN pay_way = 'cash' THEN (SELECT order_date FROM orders INNER JOIN payments ON p.id_orders_p = o.id_orders WHERE pay_way = 'cash')  </br>
		ELSE (SELECT DATEADD(DD, 7, give_away_date) FROM give_away INNER JOIN orders ON o.id_orders = ga.id_order INNER JOIN payments ON o.id_orders = p.id_orders_p WHERE pay_way = 'transfer') </br>
		END 'PAYMENT DEADLINE DATE', </br>
ga.give_away_date AS 'PRODUCT GIVE AWAY DATE', </br>
c.first_name AS 'CUSTOMER FIRST NAME' , </br>
c.last_name AS 'CUSTOMER LAST NAME' </br>

FROM orders o </br>
	INNER JOIN customers c </br>
		ON o.id_customer = c.id_customers </br>
	INNER JOIN give_away ga </br>
		ON o.id_orders = ga.id_order </br>
	INNER JOIN payments p </br>
		ON o.id_orders = p.id_orders_p </br>
		
		
## 7. Parameterized scripts

### 7.1 Add some values to tb_orders

BEGIN TRAN 

DECLARE @employee_last_name varchar(50) = 'Niemala'   /* enter your last name  */
DECLARE @employee_first_name varchar(50) = 'Kinga'    /* enter your first name  */
DECLARE @date DATETIME = GETDATE()
DECLARE @employee_id int = (SELECT id_employees FROM employees WHERE e_last_name = @employee_last_name AND e_first_name = @employee_first_name)

INSERT INTO orders(id_customer, order_date, id_recipient_of_order)
VALUES (3, @date, @employee_id)

INSERT INTO orders(id_customer, order_date, id_recipient_of_order)
VALUES (5, @date, @employee_id)


COMMIT TRAN 

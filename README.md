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

## 3. Columns in a table and their data types </br>

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

### 3.2 tb_customers </br>

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
    <td>int</td>
  </tr>
 </table>
  

## Main database relations diagram 
<img src="https://user-images.githubusercontent.com/59047042/87777158-48ded980-c829-11ea-8d0e-dda1280ad530.jpg">

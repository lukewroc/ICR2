# 1.0 Ink Cartridge Regeneration [ICR] 2.0 </br> 
Project of ink cartridge regeneration service database, which is built on Microsoft SQL Server 2014.  </br> 
### 1.1 Database description </br> 
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



## Main database relations diagram 
<img src="https://user-images.githubusercontent.com/59047042/85919730-5af2db00-b86e-11ea-95a3-04940538c57d.jpg">

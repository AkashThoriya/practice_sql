## Concepts of SQL
**Create these 5 tables**
 1. Create customer table with these columns and insert 5 rows => customer_id | first_name | last_name  |  birth_date | phone  |  address  | city  | state 
 2. Create product table with these columns => product_id, product_name, unit_price
 3. Create shipping table with shipper_id, shipper_name
 4. Create order tables with these columns and insert 5 rows in relation with customer table => order_id | customer_id | order_date | status [must be enum with pending, inProgress, shipped] | comments | shipped_date | shipper_id
 5. Create order_items table with these columns and insert 5 rows in relation with customer and order, product, shipping tables => order_item_id | order_id | product_id | quantity | unit_price

## Introduction to SQL

 1. Get the customers whose last names start with MY or contains SE [without using OR]
2. From the order_items table, get the items for order where the total price is greater then average
3. Select all the items from order_items table of "id" 2, and short them by there total price by descending order
4. Return order_items table with order_item_id, order_id, customer_name, product_name, shipper_name, status
5. What is view and when to use it?
6. What is stored procedure and when to use it?

## SQL Task

**Note** <br/>
<code>Each table must have status column with 2 possible value => [active, inactive] <br/><br/>
Where active is default </code>

**Create these 5 tables**
1. create module_master with these columns => module_id, module_name 
       insert 5 rows given in below table :
       
| module_id | module_name | status |
|--|--|--|
| 1 | customer | active |
| 2 | vendor | active |
| 3 | courier | active |
| 4 | module_4 | inactive |
| 5 | module_5 | inactive |


       
2. create customer table with these columns  and insert 5 rows => customer_id, first_name, last_name

3. create vendor table with these columns and insert 5 rows  => vendor_id, first_name, last_name

4. create courier table with these columns  and insert 5 rows => courier_id, first_name, last_name
       
5. create table sales_order with these columns  => sales_order_id, module_id, party_id
	insert 5 rows given in below table :
	
| sales_order_id | module_id | party_id |
|--|--|--|
| 1 | 1 | 3 |
| 2 | 1 | 4 |
| 3 | 2 | 3 |
| 4 | 3 | 1 |
| 5 | 3 | 5 |


**Write SELECT query for sales_order table** <br/>
Which returns full_name of related master <br/>
<code>full_name = first_name + ' ' + last_name</code>

**Example** <br/>
[1, 1, 3] <br/>
module_id = 1 => customer <br/>
We are treating party_id as customer_id because module_id = 1 <br/>
so return full_name of customer where customer_id = 3 <br/><br/>

[4, 3, 1] <br/>
module_id = 3 => courier <br/>
We are treating party_id as courier_id because module_id = 3 <br/>
so return full_name of courier where courier_id = 1

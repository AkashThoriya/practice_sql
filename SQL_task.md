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

<br/>
**Assume : For now only need to consider active modules [customer, vendor, courier]** <br/>
**Write SELECT query for sales_order table** <br/>
Which returns full_name of related master <br/>
<code>full_name = first_name + ' ' + last_name</code> <br/><br/>

**Also create dynamic stored procedure for same** <br/><br/>

**Example** <br/>
[1, 1, 3] <br/>
module_id = 1 => customer <br/>
We are treating party_id as customer_id because module_id = 1 <br/>
so return full_name of customer where customer_id = 3 <br/><br/>

[4, 3, 1] <br/>
module_id = 3 => courier <br/>
We are treating party_id as courier_id because module_id = 3 <br/>
so return full_name of courier where courier_id = 1

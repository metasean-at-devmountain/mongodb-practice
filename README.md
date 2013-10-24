mongodb-practice
================

Set of tasks for practicing mongodb commands/queries

References: 
* http://docs.mongodb.org/manual/core/read-operations/
* http://docs.mongodb.org/manual/core/write-operations/

You're creating a database for a small-time CRM (Customer Relationship Management) system.

1. Create a collection of customers.
2. Add a new customer with a `business_name` of Acme, `num_employees` of 1200, `account_value` of 50000
3. Add a new customer with a `business_name` of Apple, `num_employees` of 35100, `account_value` of 23000000
4. Add a new customer with a `business_name` of Ma&Pa, `num_employees` of 15, `account_value` of 1200
 
Now, practice querying for results
1. Select all customers with an account value of greater than 10000
2. Select only names of businesses that have less than 2000 employees
3. Select all customers sorted by number of employees (ascending, or lowest to highest)
4. Select the id of customers whose business name's begin with 'A' (hint: http://docs.mongodb.org/manual/reference/operator/query/where/#op._S_where)

Modify some of our records
1. Add a `rep` for each record in the collection:
  * For Acme, rep name: 'Wile E. Coyote', employee #: 4311
  * For Apple, rep name: 'Fan Boi', employee #: 1216
  * For Ma&Pa, rep name: 'Jedediah', employee #: 5918
2. Update every customer to have an `active` status of `true`
3. Update Ma&Pa to have 20 employees and an `account_value` of 2500
4. Select the rep names of every customer






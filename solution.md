1. Add a new customer with a business_name of Acme, num_employees of 1200, account_value of 50000

```
db.customers.insert({
  business_name: 'Acme', 
  num_employees: 1200, 
  account_value: 50000
})
```

2. Add a new customer with a business_name of Apple, num_employees of 35100, account_value of 23000000

```
db.customers.insert({
  business_name: 'Apple', 
  num_employees: 35100, 
  account_value: 23000000
})
```

3. Add a new customer with a business_name of Ma&Pa, num_employees of 15, account_value of 1200

```
db.customers.insert({
  business_name: 'Ma&Pa', 
  num_employees: 15, 
  account_value: 1200
})
```

1. Select all customers with an account value of greater than 10000

```
db.customers.find({account_value: {$gt: 10000}})
```

2. Select only names of businesses that have less than 2000 employees

```
db.customers.find({num_employees: {$lt: 2000}}, {business_name: 1})
```

3. Select all customers sorted by number of employees (ascending, or lowest to highest)

```
db.customers.find().sort({num_employees: 1})
```

4. Select the id of customers whose business name's begin with 'A' (hint: http://docs.mongodb.org/manual/reference/operator/query/where/#op._S_where)

```
db.customers.find( { 
  $where: function() { 
    return (this.business_name.charAt(0) == 'A') 
  } 
})
```

1. Add a `rep` for each record in the collection:
  * For Acme, rep name: 'Wile E. Coyote', employee #: 4311
  * For Apple, rep name: 'Fan Boi', employee #: 1216
  * For Ma&Pa, rep name: 'Jedediah', employee #: 5918

```
db.customers.update({
  business_name: 'Acme'
}, {
  $set: {
    rep: {
      name: 'Wile E. Coyote', 
      employee_number: 4311
    }
  }
})
```

2. Update every customer to have an `active` status of `true`

```
db.customers.update({}, 
  {
    $set: {active:'true'}
  }, 
  {multi:true}
)
```

3. Update Ma&Pa to have 20 employees and an `account_value` of 2500

```
db.customers.update({business_name: 'Ma&Pa'}, { $set: {account_value: 2500} })
```

4. Select the rep names of every customer

```
db.customers.find({}, {"rep.name":1})
```

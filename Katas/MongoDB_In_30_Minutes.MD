### A kata from video https://www.youtube.com/watch?v=pWbMrx5rVBE

### Installation
- Download/Install/Change path
- Create data/db & log folder
- Navigate to mongodb/bin folder
- mongodb --directoryperdb --dbpath c:\mongodb\data\db -- logpath c:\mongodb\log\mongo.log --logappend --rest --install
- --install as service
- net start mongodb
### Basic administration
- mongo to enter the shell
- show dbs
- use mycustomers - switch and create
- db - check current 
- use products

### Questions


- Easy scaling ? Understand HA. But how to make it faster?

### Actions

- Check out https://www.eduonix.com/courses/Web-Development/Projects-in-MongoDB-Learn-MongoDB-Building-Ten-Projects

### What is [JSON](http://json.org/)

```
{
	first_name:"John",
	last_name:"Doe",
	membership: ["mem1","mem2"],
	address:{
		street:"4 main st",
		city: "Boston"
	}
	contacts:[{name:"Brad", relationship:"friend"}]
}
```

- google mongodb create user

```
db.createUser(
   {
     user: "accountUser",
     pwd: "password",
     roles: [ "readWrite", "dbAdmin" ]
   }
)
```

```
db.createCollection('customers')

show collections
don't have to specify schema in advance
db.customers.insert({first_name:"John",last_name:"Doe"})
db.customers.insert([{first_name:"John2",last_name:"Doe"},{first_name:"John3",last_name:"Doe"}])
db.customers.find()
db.customers.find().pretty()
db.customer.update({first_name:"John"},{first_name:"John __"})
db.customer.update({first_name:"John3"},{$set:{first_name:"John __"}})
db.customer.update({first_name:"John3"},{$inc:{age:5}})
db.customer.update({first_name:"John3"},{$unset:{age:1}})
db.customer.update({first_name:"John"},{first_name:"John __"},{upsert:true})


db.customer.remove({first_name:"John3"},{justOne:true})

db.customers.find({first_name:"Sharon"})

db.customers.find($or:[{first_name:"Sharon"},{first_name:"Joe"}])

db.customers.find({age:{$lt:40})

db.customers.find({"address.city":"Boston"})
db.customers.sort({"address.city":1})
db.customers.sort({"address.city":-1})

db.customers.find().limit(4).count()
db.customers.find().forEach(function(doc){ print("Customer name" + doc.first_name)})
```

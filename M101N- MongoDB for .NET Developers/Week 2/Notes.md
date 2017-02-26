TBD - table, commands as code


CRUD - Mongo - SQL
Create - Insert - Insert
Read - Find - Select
Update - Update -  Update
Delete  - Remove - Delete

No own language - just API

Mongo shell - is an interactive js interpreter

mongo

UP key - previous command
CTRL+A, CTRL+E begin/end of the line

help
help keys

http://bsonspec.org/

NumberLong(2) + NumberInt(1)


doc = {name:"Smith",age:30, profession:"hacker"}

db.people.insert(doc)
db.people.find().pretty()

collection is created if does not exist
ObjectId is genereted automatically


db.people.findOne({name:"Smith"})
db.people.findOne({name:"Smith"},{name:true, _id:false})

for(i=0;i<1000;i++){ names=["exam","essay","quiz"];for(j=0;j<3;j++){db.scores.insert({"student":i,"type":names[j],score:Math.random()*100});}}

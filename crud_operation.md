### CRUD Operation

#### Create operation
```
# inserts a single document in collection human
db.human.insertOne({"name":"Tom","gender":"male","age":23,"isSingle":true}) 

# inserts multiple documents in collection human
db.human.insertMany([{"name":"Clara","gender":"female","age":26,"isSingle":false},{"name":"Nolan","gender":"male","age":22,"isSingle":true}])

# after inserting any document in collection you will get the acknowledgement from shell with object id of newly inserted documents
```

#### Read operation
```
# fetch all documents in collection human
db.human.find({})

# use query criteria to fetch particular document from collection
db.human.find({"isSingle":true}) 
# fetches documents from human where isSingle is true.

# query filters can use various query operators to specify condition
db.human.find({"age":{$lt:25}})

# query all documents where age is less than 25 and gender is female
db.human.find({"age":{$gt:25},"gender":"female"})
```

#### Update operation
```
# $set operator is provided to update documents in collection
db.human.updateOne({"name":"Tom"},{$set:{"age":24}});
```
#### Delete operation
```
# same as read and write you have to specify the query criteria for which document you want to delete in collection
db.human.deleteMany({"age":{$gt:25}})
```

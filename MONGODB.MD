ref : https://docs.mongodb.com/manual/reference/method/db.collection.insert/

## check type data 
```
db.user.find({"roles.parent.child_id":{$type:2}})
```
ref : https://docs.mongodb.com/manual/reference/operator/query/type/

## select distinct
```
db.areas.distinct('nama_field')  --> select distinct nama_field from areas 
```

## check if  property exists
```
db.users.find({"roles.parent":{$exists:true}})
```

## where and
```
db.users.find({
  $and:	[
  			{"roles.parent":{$exists:true}},
  			{"roles.student":{$exists:true}}
  		]
})
```

## where or
```
db.users.find({
  $and:	[
  			{"roles.parent":{$exists:true}},
  			{"roles.student":{$exists:true}}
  		]
})
```

## insert
```
db.cobi.insert( { item: "card", qty: 15 } )
```

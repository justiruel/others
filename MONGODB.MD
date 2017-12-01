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

## Update
```
db.cobi.update(
   { 
    _id: ObjectId("5a209c3c0c9a07903c0ad78b") 
   },
   {
     $set: {
       "item": "asoy"
     }
   },
  { upsert: true, multi: true }
)
```
### Definisi
<table>
  <tr><td>upsert</td><td>boolean</td><td>Optional. If set to true, creates a new document when no document matches the query criteria. The default value is false, which does not insert a new document when no match is found.</td></tr>
  <tr><td>multi 	boolean</td><td>boolean</td><td>Optional. If set to true, updates multiple documents that meet the query criteria. If set to false, updates one document. The default value is false. For additional information, see Multi Parameter.</td></tr>
</table>

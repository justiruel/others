## check type data 
```
db.user.find({"roles.parent.child_id":{$type:2}})
```
ref : https://docs.mongodb.com/manual/reference/operator/query/type/

## select distinct
```
db.areas.distinct('nama_field')  --> select distinct nama_field from areas 
```


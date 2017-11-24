## check type data 
```
db.user.find({"roles.parent.child_id":{$type:2}})
```
ref : https://docs.mongodb.com/manual/reference/operator/query/type/

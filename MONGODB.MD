## check type data 
db.user.find({"roles.parent.child_id":{$type:2}})

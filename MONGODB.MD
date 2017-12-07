ref : https://docs.mongodb.com/manual/reference/method/db.collection.insert/
- saat install mongodb di windows jika terjadi error : mkdir c:\data\db

## MongoDB (NoSql Database)
- adalah schemaless database, tidak mengenal istilah relation (one to many dll.)
- di konsep NoSQL ini Anda bisa menyimpan data tanpa perlu mendefinisikan tipe data dan ukurannya.
- sangat cocok untuk db blog,portal,dll.
- tidak cocok untuk aplikasi yang butuh transaction rollback
- ref : http://www.diskusiweb.com/discussion/41339/mengenal-mongodb-open-source-database-nosql-document-oriented

## Istilah
- Collection --> di sql seperti table
- Document --> di sql seperti record tapi bedanya document bisa memiliki sub document
- Document bisa memiliki banyak element dan sub document, data yang bisa ditampung tiap document adalah  max 2MB

## check type data 
```
db.user.find({"roles.parent.child_id":{$type:2}})
db.user.find({"roles.parent.child_id":"123A"})
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
## insert many (batch insert)
```
   db.cobi.insertMany( [
      { item: "card", qty: 15 },
      { item: "envelope", qty: 20 },
      { item: "stamps" , qty: 30 }
   ] );

```

## Delete
```
db.cobi.remove( { item: "asoy" } )
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
  <tr><th>Parameter</th><th>Type</th><th>Description</th></tr>
  <tr><td>upsert</td><td>boolean</td><td>Optional. If set to true, creates a new document when no document matches the query criteria. The default value is false, which does not insert a new document when no match is found.</td></tr>
  <tr><td>multi 	boolean</td><td>boolean</td><td>Optional. If set to true, updates multiple documents that meet the query criteria. If set to false, updates one document. The default value is false. For additional information, see Multi Parameter.</td></tr>
</table>


# Join 
Lookup, Performs a left outer join to an unsharded collection in the same database to filter in documents from the “joined” collection for processing.

```
db.users.aggregate([
	{
      $unwind: "$schools"
   },
    {
      $lookup:
        {
          from: "schools", //collection schools
          localField: "schools.school_id",  //schools.school_id adalah field di collection users
          foreignField: "_id",
          as: "datague"
        }
   }
])
```
penjelasan :
```
$unwind duplicates each document in the pipeline, once per array element.
So if your input pipeline contains one article doc with two elements in tags, {$unwind: '$tags'} would transform the pipeline to be two article docs that are the same except for the tags field. In the first doc, tags would contain the first element from the original doc's array, and in the second doc, tags would contain the second element.
```
Menurutku sih intinya $unwind digunakan jika localField atau foreignField adalah berupa element array/object, contoh pada <i>schools.school_id</i>, <i>schools</i> adalah element array jadi agar <i>school_id</i> dapat diakses sebagai localField atau foreignField maka <i>schools</i> harus dimasukkan unwind

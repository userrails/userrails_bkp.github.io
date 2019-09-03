## Crud operations

##### Insert a Single Document

db.collection.insertOne() inserts a single document into a collection.

MongoDB adds the _id field with an ObjectId value to the new document.

```
db.customers.insertOne(
    {
        profile_name: 'customer name',
        email: 'email@example.com',
        age: 32,
        tags: ["regular"],
        full_name: { first_name: 'firstname', mid_name: 'midname', last_name: 'last_name' }
    }
)
```
#### when you run the above command, you will get following output
```
{
	"acknowledged" : true,
	"insertedId" : ObjectId("5d6ccbfda82b6d69714cebeb")
}
```

##### Insert multiple documents

```
db.collection.insertMany()
```

```
db.customers.insertMany(
    [
        {
          profile_name: 'customer name 2',
          email: 'email10@example.com',
          age: 22,
          tags: ["regular"],
          full_name: { first_name: 'firstname2', mid_name: 'midname2', last_name: 'last_name2' }
        },
        {
          profile_name: 'customer name 3',
          email: 'email11@example.com',
          age: 22,
          tags: ["regular"],
          full_name: { first_name: 'firstname3', mid_name: 'midname3', last_name: 'last_name3' }
        },
        {
          profile_name: 'customer name 4',
          email: 'email12@example.com',
          age: 22,
          tags: ["regular"],
          full_name: { first_name: 'firstname4', mid_name: 'midname4', last_name: 'last_name4' }
        }
    ]
)
```

=> output when executing above query
```
{
	"acknowledged" : true,
	"insertedIds" : [
		ObjectId("5d6ccdf9a82b6d69714cebec"),
		ObjectId("5d6ccdf9a82b6d69714cebed"),
		ObjectId("5d6ccdf9a82b6d69714cebee")
	]
}

```

##### View Record

```
> db.customers.find({profile_name: 'customer name'})
{ "_id" : ObjectId("5d6ccbfda82b6d69714cebeb"), "profile_name" : "customer name", "email" : "email@example.com", "age" : 32, "tags" : [ "regular" ], "full_name" : { "first_name" : "firstname", "mid_name" : "midname", "last_name" : "last_name" } }
```

# multiple matched records
```
> db.customers.find({age: 22})
{ "_id" : ObjectId("5d6ccdf9a82b6d69714cebee"), "profile_name" : "customer name 4", "email" : "email4@example.com", "age" : 22, "tags" : [ "regular" ], "full_name" : { "first_name" : "firstname4", "mid_name" : "midname4", "last_name" : "last_name4" } }
{ "_id" : ObjectId("5d6cd0eb68f1285dc9559364"), "profile_name" : "customer name 2", "email" : "email10@example.com", "age" : 22, "tags" : [ "regular" ], "full_name" : { "first_name" : "firstname2", "mid_name" : "midname2", "last_name" : "last_name2" } }
{ "_id" : ObjectId("5d6cd0eb68f1285dc9559365"), "profile_name" : "customer name 3", "email" : "email11@example.com", "age" : 22, "tags" : [ "regular" ], "full_name" : { "first_name" : "firstname3", "mid_name" : "midname3", "last_name" : "last_name3" } }
{ "_id" : ObjectId("5d6cd0eb68f1285dc9559366"), "profile_name" : "customer name 4", "email" : "email12@example.com", "age" : 22, "tags" : [ "regular" ], "full_name" : { "first_name" : "firstname4", "mid_name" : "midname4", "last_name" : "last_name4" } }
```

> db.customers.find({profile_name: "customer name 4"})
```
{ "_id" : ObjectId("5d6ccdf9a82b6d69714cebee"), "profile_name" : "customer name 4", "email" : "email4@example.com", "age" : 22, "tags" : [ "regular" ], "full_name" : { "first_name" : "firstname4", "mid_name" : "midname4", "last_name" : "last_name4" } }
{ "_id" : ObjectId("5d6cd0eb68f1285dc9559366"), "profile_name" : "customer name 4", "email" : "email12@example.com", "age" : 22, "tags" : [ "regular" ], "full_name" : { "first_name" : "firstname4", "mid_name" : "midname4", "last_name" : "last_name4" } }
```

> db.customers.find({profile_name: "customer name 4", "email": "email4@example.com"})
```
{ "_id" : ObjectId("5d6ccdf9a82b6d69714cebee"), "profile_name" : "customer name 4", "email" : "email4@example.com", "age" : 22, "tags" : [ "regular" ], "full_name" : { "first_name" : "firstname4", "mid_name" : "midname4", "last_name" : "last_name4" } }
```

> db.customers.find({profile_name: "customer name 4"}).limit(1)
```
{ "_id" : ObjectId("5d6ccdf9a82b6d69714cebee"), "profile_name" : "customer name 4", "email" : "email4@example.com", "age" : 22, "tags" : [ "regular" ], "full_name" : { "first_name" : "firstname4", "mid_name" : "midname4", "last_name" : "last_name4" } }
```

#### Show all records
> db.customers.find()
```
{ "_id" : ObjectId("5d6ccbfda82b6d69714cebeb"), "profile_name" : "customer name", "email" : "email@example.com", "age" : 32, "tags" : [ "regular" ], "full_name" : { "first_name" : "firstname", "mid_name" : "midname", "last_name" : "last_name" } }
{ "_id" : ObjectId("5d6ccdf9a82b6d69714cebec"), "profile_name" : "customer name 2", "email" : "email2@example.com", "age" : 30, "tags" : [ "regular" ], "full_name" : { "first_name" : "firstname2", "mid_name" : "midname2", "last_name" : "last_name2" } }
{ "_id" : ObjectId("5d6ccdf9a82b6d69714cebed"), "profile_name" : "customer name 3", "email" : "email3@example.com", "age" : 36, "tags" : [ "regular" ], "full_name" : { "first_name" : "firstname3", "mid_name" : "midname3", "last_name" : "last_name3" } }
{ "_id" : ObjectId("5d6ccdf9a82b6d69714cebee"), "profile_name" : "customer name 4", "email" : "email4@example.com", "age" : 22, "tags" : [ "regular" ], "full_name" : { "first_name" : "firstname4", "mid_name" : "midname4", "last_name" : "last_name4" } }
{ "_id" : ObjectId("5d6cd0eb68f1285dc9559364"), "profile_name" : "customer name 2", "email" : "email10@example.com", "age" : 22, "tags" : [ "regular" ], "full_name" : { "first_name" : "firstname2", "mid_name" : "midname2", "last_name" : "last_name2" } }
{ "_id" : ObjectId("5d6cd0eb68f1285dc9559365"), "profile_name" : "customer name 3", "email" : "email11@example.com", "age" : 22, "tags" : [ "regular" ], "full_name" : { "first_name" : "firstname3", "mid_name" : "midname3", "last_name" : "last_name3" } }
{ "_id" : ObjectId("5d6cd0eb68f1285dc9559366"), "profile_name" : "customer name 4", "email" : "email12@example.com", "age" : 22, "tags" : [ "regular" ], "full_name" : { "first_name" : "firstname4", "mid_name" : "midname4", "last_name" : "last_name4" } }
```

## Upsert Option (updateOne(), updateMany(), replaceOne())

#### Replace a record except an ID field

```
db.customers.replaceOne({email: 'email@example.com'}, {"profile_name" : "customer name", "email" : "email@example.com", "age" : 15, "tags" : [ "nonregular" ], "full_name" : { "first_name" : "firstname", "mid_name" : "midname", "last_name" : "last_name" }})
```

`{ "acknowledged" : true, "matchedCount" : 1, "modifiedCount" : 1 }`

When you search the record which is just updated, you will notice update has been made:

```
db.customers.find({email: 'email@example.com'})
{ "_id" : ObjectId("5d6ccbfda82b6d69714cebeb"), "profile_name" : "customer name", "email" : "email@example.com", "age" : 15, "tags" : [ "nonregular" ], "full_name" : { "first_name" : "firstname", "mid_name" : "midname", "last_name" : "last_name" } }
```

#### Update a record execpt an ID field

First track the record you want to update

```
> db.customers.find({email: 'email2@example.com'})

{ "_id" : ObjectId("5d6ccdf9a82b6d69714cebec"), "profile_name" : "customer name 2", "email" : "email2@example.com", "age" : 30, "tags" : [ "regular" ], "full_name" : { "first_name" : "firstname2", "mid_name" : "midname2", "last_name" : "last_name2" } }
>
```

Apply Update command

```
> db.customers.updateOne({email: 'email2@example.com'}, {$set: {"profile_name": 'customer name 2 updated', "full_name.last_name": "last_name2 updated", tags: ["regular updated"]}})

{ "acknowledged" : true, "matchedCount" : 1, "modifiedCount" : 1 }
```

Now check the record and you will notice the record is updated

```
> db.customers.find({email: 'email2@example.com'})

{ "_id" : ObjectId("5d6ccdf9a82b6d69714cebec"), "profile_name" : "customer name 2 updated", "email" : "email2@example.com", "age" : 30, "tags" : [ "regular updated" ], "full_name" : { "first_name" : "firstname2", "mid_name" : "midname2", "last_name" : "last_name2 updated" } }
```

Add lastModified field when you update the record which will add new column

```
> db.customers.updateOne({email: 'email2@example.com'}, {$set: {"profile_name": 'customer name 2 updated', "full_name.last_name": "last_name2 updated", tags: ["regular updated"]}, $currentDate: { lastModified: true }})

{ "_id" : ObjectId("5d6ccdf9a82b6d69714cebec"), "profile_name" : "customer name 2 updated", "email" : "email2@example.com", "age" : 30, "tags" : [ "regular updated" ], "full_name" : { "first_name" : "firstname2", "mid_name" : "midname2", "last_name" : "last_name2 updated" }, "lastModified" : ISODate("2019-09-02T08:55:35.114Z") }
``1

The update action involves following operations:

uses the $set operator to update the value of the size.uom field to "cm" and the value of the status field to "P",
uses the $currentDate operator to update the value of the lastModified field to the current date. If lastModified field does not exist, $currentDate will create the field. See $currentDate for details.


#### UpdateMany

Update all the documents where age is greater than 22

```
db.customers.updateMany(
    {
        "age": { $gt: 22 }
    },
    {
        $set: { "tags": "Multiple Update", active: "true" },
        $currentDate: { lastModified: true }
    }
)
```
>> { "acknowledged" : true, "matchedCount" : 2, "modifiedCount" : 2 }

Now it's time to check updated record:

```
> db.customers.find({"age": {$gt: 22}})
{ "_id" : ObjectId("5d6ccdf9a82b6d69714cebec"), "profile_name" : "customer name 2 updated", "email" : "email2@example.com", "age" : 30, "tags" : "Multiple Update", "full_name" : { "first_name" : "firstname2", "mid_name" : "midname2", "last_name" : "last_name2 updated" }, "lastModified" : ISODate("2019-09-02T12:56:37.700Z"), "active" : "true" }
{ "_id" : ObjectId("5d6ccdf9a82b6d69714cebed"), "profile_name" : "customer name 3", "email" : "email3@example.com", "age" : 36, "tags" : "Multiple Update", "full_name" : { "first_name" : "firstname3", "mid_name" : "midname3", "last_name" : "last_name3" }, "active" : "true", "lastModified" : ISODate("2019-09-02T12:56:37.700Z") }
```

#### Some other options:
```
db.collection.findOneAndReplace().
db.collection.findOneAndUpdate().
db.collection.findAndModify().
db.collection.save().
db.collection.bulkWrite()
```

#### Delete document (deleteOne(), deleteMany())

Delete only one record no matter multiple records for this profile name exists
```
> db.customers.deleteOne({profile_name: 'profile name'})

o/p => { "acknowledged" : true, "deletedCount" : 1 }
```

Delete many records at once
```
> db.customers.deleteMany({profile_name: 'profile name 1'})
o/p => { "acknowledged" : true, "deletedCount" : 4 }
```
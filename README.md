# Mongodb Cheatsheet
MongoDB is a source-available cross-platform document-oriented database program. Classified as a NoSQL database program, MongoDB uses JSON-like documents with optional schemas. MongoDB is developed by MongoDB Inc
- [MongoDB](https://www.mongodb.com/cloud/atlas/lp/try2?utm_source=google&utm_campaign=gs_footprint_row_search_core_brand_atlas_desktop&utm_term=mongodb%20database&utm_medium=cpc_paid_search&utm_ad=e&utm_ad_campaign_id=12212624584&adgroup=115749713703)

## 1. Database Commands
- View all databases
```
show dbs
```
- Create a new or switch databases 
```
use dbName
```

- View current Database
```
db
```

- Delete Database 
```
db.dropDatabase()
```
## 2.Collection Commands
- Show Collections
```
show collections
```
- Create a collection named 'testCollection'
```
db.createCollection('testCollection')
```

- Drop a collection named 'testCollection'
```
db.testCollection.drop()
```

## 3.Row(Document) Commands
- Show all Rows in a Collection 
```
db.testCollection.find()
```
- Show all Rows in a Collection (Prettified)
```
db.testCollection.find().pretty()
```

- Find the first row matching the object
```
db.testCollection.findOne({name: 'Lushiv'})
```

- Insert One Row
```
db.testCollection.insert({
    'name': 'lushiv',
    'lang': 'python',
    'id': 1
 })
```

 Insert many Rows
  
  ```
  db.testCollection.insertMany([{
    'name': 'lusi',
    'lang': 'JavaScript',
    'id': 5
    }, 
    {'name': 'jk',
    'lang': 'Python',
    'id': 3
    },
    {'name': 'Lovish',
    'lang': 'Java',
    'id': 4
}])

  ```

## 4.Search in a MongoDb Database
```
db.testCollection.find({lang:'Python'})
```
## 5.Limit the number of rows in output
```
db.testCollection.find().limit(2)
```

## 6.Count the number of rows in the output
```
db.testCollection.find().count()
```

## 7.Update a row

```
db.testCollection.update({name: 'Shubham'},
{'name': 'lushiv',
    'lang': 'Node js',
    'id': 51s
}, {upsert: true})
```

## 8.Mongodb Increment Operator
```
db.testCollection.update({name: 'Rohan'},
{$inc:{
    id: 1
}})
```


## 9.Mongodb Rename Operator
```
db.testCollection.update({name: 'Rohan'},
{$rename:{
    member_since: 'member'
}})
```

## 10.Delete Row 
```
db.testCollection.remove({name: 'lushiv'})
```

## 11.Less than/Greater than/ Less than or Eq/Greater than or Eq
```
db.testCollection.find({member_since: {$lt: 90}})
```
```
db.testCollection.find({member_since: {$lte: 90}})

```
```
db.testCollection.find({member_since: {$gt: 90}})

```
```
db.testCollection.find({member_since: {$gte: 90}})

```
# MongoDB Lab Assignments -Day 1


## MongoDB Exercise in mongo shell

Connect to a running mongo instance, use a database named mongo_practice. Document all your queries in a javascript file to use as a reference

```
mongosh "mongodb+srv://tonystark.kzwui.mongodb.net/myFirstDatabase" --username subhamsatpathy11
Enter password: *********
Current Mongosh Log ID: 61da758ae044a8339e783c4e
Connecting to:          mongodb+srv://tonystark.kzwui.mongodb.net/myFirstDatabase
Using MongoDB:          4.4.10
Using Mongosh:          1.1.7

For mongosh info see: https://docs.mongodb.com/mongodb-shell/
```

```
Atlas atlas-2v2ryx-shard-0 [primary] myFirstDatabase> use mongodb_practice
switched to db mongodb_practice
```

## Insert Documents

Insert the following documents into a movies collection.
```
Atlas atlas-2v2ryx-shard-0 [primary] mongodb_practice> db.createCollection('movies')
{ ok: 1 }
Atlas atlas-2v2ryx-shard-0 [primary] mongodb_practice> show collections
movies
```

The documents that are to be inserted;

```
title : Fight Club
writer : Chuck Palahniuko
year : 1999
actors : [
 Brad Pitt
 Edward Norton
]

title : Pulp Fiction
writer : Quentin Tarantino
year : 1994
actors : [
 John Travolta
 Uma Thurman
]

title : Inglorious Basterds
writer : Quentin Tarantino
year : 2009
actors : [
 Brad Pitt
 Diane Kruger
 Eli Roth
]

title : The Hobbit: An Unexpected Journey
writer : J.R.R. Tolkein
year : 2012
franchise : The Hobbit

title : The Hobbit: The Desolation of Smaug
writer : J.R.R. Tolkein
year : 2013
franchise : The Hobbit

title : The Hobbit: The Battle of the Five Armies
writer : J.R.R. Tolkein
year : 2012
franchise : The Hobbit
synopsis : Bilbo and Company are forced to engage in a war against an array of
combatants and keep the Lonely Mountain from falling into the hands of a rising
darkness.

title : Pee Wee Herman's Big Adventure

title : Avatar

```

```
//Code 

Atlas atlas-2v2ryx-shard-0 [primary] mongodb_practice> db.movies.insertMany([{title:'Fight Club', writer: 'Chuck Palahniuko', year:1999, actors:['Brad Pitt','Edwrd Norton']}, {title:'Pulp Fiction',writer:'Quentin Tarantino',year:1994,actors:['John Travolta','Uma Thurman']},{title: 'Inglorious Basterds', writer: 'Quentin Tarantino', year: 2009, actors: ['Brad Pitt','Diane Kruger','Eli Roth']}, {title: 'The Hobbit: An Unexpected Journey', writer: 'J.R.R Tolkein', year: 2012, franchise: 'The Hobbit'}, {title: 'The Hobbit: The Desolation of Smaug', writer: 'J.R.R Tolkein', year: 2013, franchise: 'The Hobbit'}, {title: 'The Hobbit: The Battle of the Five Armies', writer: 'J.R.R Tolkein', year: 2012, franchise: 'The Hobbit', synopsis: 'Bilbo and Company are forced to engage in a war against array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness'}, {title:"Pee Wee Herman's Big Adventure"},{title: 'Avatar'}])
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId("61da79d7c4f4f44d993c57d6"),
    '1': ObjectId("61da79d7c4f4f44d993c57d7"),
    '2': ObjectId("61da79d7c4f4f44d993c57d8"),
    '3': ObjectId("61da79d7c4f4f44d993c57d9"),
    '4': ObjectId("61da79d7c4f4f44d993c57da"),
    '5': ObjectId("61da79d7c4f4f44d993c57db"),
    '6': ObjectId("61da79d7c4f4f44d993c57dc"),
    '7': ObjectId("61da79d7c4f4f44d993c57dd")
  }
}
```

## Query/ Find Documents

query the movies collection to

1. get all documents
```
Atlas atlas-2v2ryx-shard-0 [primary] mongodb_practice> db.movies.find()
[
  {
    _id: ObjectId("61da79d7c4f4f44d993c57d6"),
    title: 'Fight Club',
    writer: 'Chuck Palahniuko',
    year: 1999,
    actors: [ 'Brad Pitt', 'Edwrd Norton' ]
  },
  {
    _id: ObjectId("61da79d7c4f4f44d993c57d7"),
    title: 'Pulp Fiction',
    writer: 'Quentin Tarantino',
    year: 1994,
    actors: [ 'John Travolta', 'Uma Thurman' ]
  },
  {
    _id: ObjectId("61da79d7c4f4f44d993c57d8"),
    title: 'Inglorious Basterds',
    writer: 'Quentin Tarantino',
    year: 2009,
    actors: [ 'Brad Pitt', 'Diane Kruger', 'Eli Roth' ]
  },
  {
    _id: ObjectId("61da79d7c4f4f44d993c57d9"),
    title: 'The Hobbit: An Unexpected Journey',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit'
  },
  {
    _id: ObjectId("61da79d7c4f4f44d993c57da"),
    title: 'The Hobbit: The Desolation of Smaug',
    writer: 'J.R.R Tolkein',
    year: 2013,
    franchise: 'The Hobbit'
  },
  {
    _id: ObjectId("61da79d7c4f4f44d993c57db"),
    title: 'The Hobbit: The Battle of the Five Armies',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit',
    synopsis: 'Bilbo and Company are forced to engage in a war against array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness'
  },
  {
    _id: ObjectId("61da79d7c4f4f44d993c57dc"),
    title: "Pee Wee Herman's Big Adventure"
  },
  { _id: ObjectId("61da79d7c4f4f44d993c57dd"), title: 'Avatar' }
]
```

2. get all documents with writer set to "Quentin Tarantino"
```
Atlas atlas-2v2ryx-shard-0 [primary] mongodb_practice> db.movies.find({writer:"Quentin Tarantino"})
[
  {
    _id: ObjectId("61da79d7c4f4f44d993c57d7"),
    title: 'Pulp Fiction',
    writer: 'Quentin Tarantino',
    year: 1994,
    actors: [ 'John Travolta', 'Uma Thurman' ]
  },
  {
    _id: ObjectId("61da79d7c4f4f44d993c57d8"),
    title: 'Inglorious Basterds',
    writer: 'Quentin Tarantino',
    year: 2009,
    actors: [ 'Brad Pitt', 'Diane Kruger', 'Eli Roth' ]
  }
]
```

3. get all documents where actors include "Brad Pitt"
```
Atlas atlas-2v2ryx-shard-0 [primary] mongodb_practice> db.movies.find({actors:"Brad Pitt"})
[
  {
    _id: ObjectId("61da79d7c4f4f44d993c57d6"),
    title: 'Fight Club',
    writer: 'Chuck Palahniuko',
    year: 1999,
    actors: [ 'Brad Pitt', 'Edwrd Norton' ]
  },
  {
    _id: ObjectId("61da79d7c4f4f44d993c57d8"),
    title: 'Inglorious Basterds',
    writer: 'Quentin Tarantino',
    year: 2009,
    actors: [ 'Brad Pitt', 'Diane Kruger', 'Eli Roth' ]
  }
]
```

4. get all documents with franchise set to "The Hobbit"
```
Atlas atlas-2v2ryx-shard-0 [primary] mongodb_practice> db.movies.find({franchise:"The Hobbit"})
[
  {
    _id: ObjectId("61da79d7c4f4f44d993c57d9"),
    title: 'The Hobbit: An Unexpected Journey',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit'
  },
  {
    _id: ObjectId("61da79d7c4f4f44d993c57da"),
    title: 'The Hobbit: The Desolation of Smaug',
    writer: 'J.R.R Tolkein',
    year: 2013,
    franchise: 'The Hobbit'
  },
  {
    _id: ObjectId("61da79d7c4f4f44d993c57db"),
    title: 'The Hobbit: The Battle of the Five Armies',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit',
    synopsis: 'Bilbo and Company are forced to engage in a war against array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness'
  }
]
```

5. get all movies released in the 90s
```
Atlas atlas-2v2ryx-shard-0 [primary] mongodb_practice> db.movies.find({year:{$gt:1990, $lt:2000}})
[
  {
    _id: ObjectId("61da79d7c4f4f44d993c57d6"),
    title: 'Fight Club',
    writer: 'Chuck Palahniuko',
    year: 1999,
    actors: [ 'Brad Pitt', 'Edwrd Norton' ]
  },
  {
    _id: ObjectId("61da79d7c4f4f44d993c57d7"),
    title: 'Pulp Fiction',
    writer: 'Quentin Tarantino',
    year: 1994,
    actors: [ 'John Travolta', 'Uma Thurman' ]
  }
]
```

6. get all movies released before the year 2000 or after 2010
```
Atlas atlas-2v2ryx-shard-0 [primary] mongodb_practice> db.movies.find({$or:[{year:{$gt:2010}},{year: {$lt:2000}}]})
[
  {
    _id: ObjectId("61da79d7c4f4f44d993c57d6"),
    title: 'Fight Club',
    writer: 'Chuck Palahniuko',
    year: 1999,
    actors: [ 'Brad Pitt', 'Edwrd Norton' ]
  },
  {
    _id: ObjectId("61da79d7c4f4f44d993c57d7"),
    title: 'Pulp Fiction',
    writer: 'Quentin Tarantino',
    year: 1994,
    actors: [ 'John Travolta', 'Uma Thurman' ]
  },
  {
    _id: ObjectId("61da79d7c4f4f44d993c57d9"),
    title: 'The Hobbit: An Unexpected Journey',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit'
  },
  {
    _id: ObjectId("61da79d7c4f4f44d993c57da"),
    title: 'The Hobbit: The Desolation of Smaug',
    writer: 'J.R.R Tolkein',
    year: 2013,
    franchise: 'The Hobbit'
  },
  {
    _id: ObjectId("61da79d7c4f4f44d993c57db"),
    title: 'The Hobbit: The Battle of the Five Armies',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit',
    synopsis: 'Bilbo and Company are forced to engage in a war against array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness'
  }
]
```

## Update Documents

1. add a synopsis to "The Hobbit: An Unexpected Journey" : "A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."
```
Atlas atlas-2v2ryx-shard-0 [primary] mongodb_practice> db.movies.update({title:'The Hobbit: An Unexpected Journey'}, {$set:{synopsis:"A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."}})
DeprecationWarning: Collection.update() is deprecated. Use updateOne, updateMany, or bulkWrite.
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
```
2. add a synopsis to "The Hobbit: The Desolation of Smaug" : "The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."
```
Atlas atlas-2v2ryx-shard-0 [primary] mongodb_practice> db.movies.update({title:'The Hobbit: The Desolation of Smaug'}, {$set:{synopsis:"The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
```
3. add an actor named "Samuel L. Jackson" to the movie "Pulp Fiction"
```
Atlas atlas-2v2ryx-shard-0 [primary] mongodb_practice> db.movies.update({title:'Pulp Fiction'}, {$push:{actors:"Samuel L. Jackson"}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
```

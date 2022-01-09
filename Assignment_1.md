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
C:\Users\SUBSATPA\Downloads\mongosh-1.1.7-win32-x64\bin>mongosh "mongodb+srv://tonystark.kzwui.mongodb.net/myFirstDatabase" --username subhamsatpathy11
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

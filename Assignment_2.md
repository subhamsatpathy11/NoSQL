# MongoDB -Aggregation Exercises

Import the zips.json file into your MongoDB. Database name is "population" and collection name is "zipcodes".

```
mongoimport --db population --collection zipcodes --file C:/SUBSATPA/zips.json
```

## Atlanta Population

1. use db.zipcodes.find() to filter results to only the results where city is ATLANTA and state is GA.
```
Atlas atlas-2v2ryx-shard-0 [primary] population> db.zipcodes.find({$and:[{city:'ATLANTA'},{state: 'GA'}]})
[
  {
    _id: '30303',
    city: 'ATLANTA',
    loc: [ -84.388846, 33.752504 ],
    pop: 1845,
    state: 'GA'
  },
  {
    _id: '30305',
    city: 'ATLANTA',
    loc: [ -84.385145, 33.831963 ],
    pop: 19122,
    state: 'GA'
  },
  {
    _id: '30306',
    city: 'ATLANTA',
    loc: [ -84.351418, 33.786027 ],
    pop: 20081,
    state: 'GA'
  }
  .
  .
  .
 ]
Type "it" for more.
```
2. use db.zipcodes.aggregate with $match to do the same as above.
```
Atlas atlas-2v2ryx-shard-0 [primary] population> db.zipcodes.aggregate([{$match:{$and:[{city:'ATLANTA'},{state:'GA'}]}}])
[
  {
    _id: '30303',
    city: 'ATLANTA',
    loc: [ -84.388846, 33.752504 ],
    pop: 1845,
    state: 'GA'
  },
  {
    _id: '30305',
    city: 'ATLANTA',
    loc: [ -84.385145, 33.831963 ],
    pop: 19122,
    state: 'GA'
  },
  {
    _id: '30306',
    city: 'ATLANTA',
    loc: [ -84.351418, 33.786027 ],
    pop: 20081,
    state: 'GA'
  }
 .
 .
 .
 ]
Type "it" for more.
```
3. use $group to count the number of zip codes in Atlanta.
```

```
5. use $group to find the total population in Atlanta.

# bda-assignment

### Assignment 1

3.

```

```

4.

```
db.restaurants.find(
{ 'cuisine':{$ne : 'American '},
  'grades.grade':'A',
  'borough':{$ne: 'Brooklyn'}
}
).sort({'cuisine':-1}).pretty()
```

### Assignment 2

1.

```
db.restaurants.aggregate(
  [
    {$match:{'address.building':'2780'}},
    {$set : {'Comment': 'Hope you enjoyed the Food!'}}
  ]
).pretty()
```

2.

```
db.restaurants.find(
  { 'borough':'Bronx',
    $or:[
      {'cuisine':'American '},
      {'cuisine':'Chinese'},
      {'cuisine':'Italian'}
    ]
  },
  {'_id':0,
  'restaurant_id':1,
  'name':1,
  'borough':1,
  'cuisine':1}
).pretty()
```

### Assignment 3

1.

```
db.restaurants.find({}).sort({'cuisine':1,'borough':-1}).pretty()
```

2.

```
db.restaurants.find().count()
db.restaurants.find({ 'address.coord': { $exits: true } }).count()

db.restaurants.find().count()
db.restaurants.find({ 'address.coord': { $type: "double" } }).count()
```

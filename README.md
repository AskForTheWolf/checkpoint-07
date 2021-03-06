# Week 10

## Mongoose

### Question 1

Describe the differences between a SQL and NoSQL database, and when you might use each.

```text
NoSQL has no relations. You could use it for objects/models that don't necessarily "belong" to each other, closer to OOP. Or if you need to add/modify fields it's easier.
```

### Question 2

What's wrong with this Mongoose code and how might we fix it?

```js
var results = AuthorModel.find({name: "Bob"})
console.log(results)
```

> Hint: Assuming there is a document with a name of "Bob", why does `results` not contain an author model on the second line?

```js
// Do you need to change it to results.name?  I'm not entirely sure about returning a whole model
```

### Question 3

Convert the Ruby and ActiveRecord code below into Javascript and Mongoose code...

```rb
@andy = Instructor.find_by(name: "Andy")
@andy.wishlist_items.create(description: "Resin Laying Deer Figurine, Gold")
```

```js
function findName(instructor){
  Instructor.findOne({name: instructor})
}
var andy = Instructor.findName("andy")

andy.wishlist_items.create({ description: 'Resin Laying Deer Figurine, Gold'})

```


### Question 4

Convert the following create method in Mongoose to ActiveRecord...

```js
var author = new Author({name: req.body.name})
author.save(function(err){
  if (!err){
    res.redirect("/authors")
  }
})
```

```rb
#class AuthorController < ApplicationController
#   def create
#     author = Author.createauthor(params[:name])
#     author.save
#   end
# end
# I think.
```

## Express

### Question 5

What is `module.exports` and why do we use it?

```text
It's the object that gets returned as the result of a require call.
```

### Question 6

Write one Express route for each of the four CRUD actions.

Then, make each route respond with a one-word string containing the RESTful action that would most likely be associated with this route.

```js
var express = require("express")
var app = express()

// Your code starts here...
app.get('/get', function (req, res) {
  res.send('Read')
});

app.post('/post', function (req, res) {
  res.send('create')
});

app.put('/put', function (req, res) {
  res.send('Update')
});

app.delete('/delete', function (req, res) {
  res.send('destroy')

});

```

### Question 7

Describe the differences between Express and Rails as backend frameworks.

```text
Your answer...
Rails seems easier if you have all your data, models, etc planned out beforehand with simple CRUD functions.  Express seems more flexible and less tightly structured
```

### Question 8

What do the following lines of code do?

```js
var bodyParser = require("body-parser")
app.use(bodyParser.json())
app.use(bodyParser.urlencoded({extended: true}))
```

```text
Your answer...
Handles specific urlencoded requests and the data that's returned
```

### If You Finish Early...

Take a look at these [front end developer interview questions](https://github.com/h5bp/Front-end-Developer-Interview-Questions/blob/master/README.md)

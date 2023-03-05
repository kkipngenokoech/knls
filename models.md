# KNLS MODELS

it's a library model: so it will have information about:

1. Book
   - title : string
   - author : Author(1)
   - summary : String
   - genre : Genre[0...*]
   - ISBN number : String
   - url : String
2. BookInstance
   - book : Book
   - imprint : String
   - status : enum
   - due_back : Date
   - url : String
3. Genre
   - name : String
   - url : String
4. Author
   - FirstName : String
   - FamilyName : String
   - DateOfBirth : Date
   - DateOfDeath : Date
   - name : String
   - lifespan : String
   - url : String

## mongoose

we need mongoose package to help us provide a high-level api for working with MongoDB databases.

mongoose is an Object relational library.

to install it and add it to our package.json dependencies we are going to use `npm install mongoose`.

this command adds mongoose to the list of our dependencies.

## connecting to mongoDB

first thing is you need to require your mongoose in app.js

`const mongoose = require('mongoose')`

then you `mongoose.set('strictQuery', false)`.

The strictQuery option controls whether Mongoose should throw an error if a query includes fields that are not defined in the schema for the associated model.

By default, the strictQuery option is set to true, which means that Mongoose will throw an error if a query includes fields that are not defined in the schema. However, setting strictQuery to false can be useful in some cases, such as when you want to allow clients to send additional query parameters that are not defined in the schema.

then after there we are now going to import our db.

`const mongoDB = 'your link to your database'`

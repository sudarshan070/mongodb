1. Create a database named `blog`.
use blog

2. Create a collection called 'articles'.
db.createCollection("articles")

3. Insert multiple documents(at least 3) into articles. It should have fields
db.articles.insert({titel: "Yugandhar", author:"Shivaji Sawant", age:65, details:"It is based on life of Krish
na"})

db.articles.insert({titel: "Chawa", author:"Shivaji Sawant", age:65, details:"It is based on life of  Sambhaji
, one of the grea Maratha  warrior"})

db.articles.insert({titel: "Mrityunjay", author:"Shivaji Sawant", age:65, details:"It is based on life of Karn
a"})

db.articles.insert({titel: "Panipat", author:"Vishwas Patil", age:60, details:"Third battsl of Panipat"})



4. Find all the articles using `db.COLLECTION_NAME.find()`

db.articles.find()
{ "_id" : ObjectId("5ea6fd15af7067671580c2d5"), "titel" : "Chawa", "author" : "Shivaji Sawant", "age" : 65, "details" : "It is based on life of  Sambhaji, one of the grea Maratha  warrior" }
{ "_id" : ObjectId("5ea6ffe4af7067671580c2d6"), "titel" : "Yugandhar", "author" : "Shivaji Sawant", "age" : 65, "details" : "It is based on life of Krishna" }
{ "_id" : ObjectId("5ea70033af7067671580c2d7"), "titel" : "Mrityunjay", "author" : "Shivaji Sawant", "age" : 65, "details" : "It is based on life of Karna" }
{ "_id" : ObjectId("5ea704f7af7067671580c2d8"), "titel" : "Panipat", "author" : "Vishwas Patil", "age" : 60, "details" : "Third battsl of Panipat" }


5. Find a document using _id field.

db.articles.find({_id:ObjectId("5ea704f7af7067671580c2d8")})



6. Find documents using title and author's name field.
db.articles.find({}, {titel:1, author:1})



7. Find document using a specific tag.


8. Update title of a document using its _id field.
db.articles.update({_id:ObjectId("5ea6fd15af7067671580c2d5")}, {$set:{titel: "Sambaji"}})

9. Update a author's name using article's title.
db.articles.update({"titel":"Sambaji"},{$set:{author: "Vishwas Patil"}})

10. rename details field to description from articles collection. 
db.articles.updateMany( {}, { $rename: { "details": "description" } } )


11. Add additional tag in a specific document.
db.articles.insert(tags:"details")
db.articles.update({id:ObjectId("5ea70033af7067671580c2d7")}, {$push:{tags: 'Best Celler'}})

12. Update an article's tags using $set and without $set.
  - Write the differences here ?


13. Increment an auhtor's age by 5. 
db.articles.update({_id:ObjectId("5ea6fd15af7067671580c2d5")}, {$inc:{age: 5} }) 
db.articles.find().pretty()

14. Delete a document using _id field with `db.COLLECTION_NAME.remove()`.
db.articles.remove({_id: ObjectId("5ea6ffe4af7067671580c2d6" )})

Use sample.js data for below queries.

1. Find all males who play cricket.

2. Update user with extra golf field in sports array whose name is "Steve Ortega".

3. Find all users who play either 'football' or 'cricket'.

4. Find all users whose name includes 'ri' in their name.

#### write commands for following mongodb opertaions

1. create a database named `sports`
// Answer here ..
use sports

2. list all databases present in local mongod server.
// Answer here..
admin   0.000GBs
config  0.000GB
local   0.000GB
test    0.000GB

3. create 3 collections named `cricket`, `football`, `TT` in sports database.
db.createCollection("cricket")
db.createCollection("football")
db.createCollection("TT")

4. add 3 players in each of above collections which should have fields like `name`, `age`, `email`, state and auction_price.
for cricket
{  "name" : "palyer1", "age" : 19, "email" : "palyer1@gmail.com" }
{  "name" : "palyer2", "age" : 21, "email" : "palyer2@gmail.com" }
{  "name" : "palyer3", "age" : 22, "email" : "palyer3@gmail.com" }

for football
{  "name" : "palyer1", "age" : 21, "email" : "palyer1@gmail.com" }
{"name" : "palyer2", "age" : 23, "email" : "palyer2@gmail.com" }
{  "name" : "palyer3", "age" : 20, "email" : "palyer3@gmail.com" }


for TT
 {"name" : "palyer1", "age" : 20, "email" : "palyer1@gmail.com" }
{  "name" : "palyer2", "age" : 25, "email" : "palyer2@gmail.com" }
{  "name" : "palyer3", "age" : 22, "email" : "palyer3@gmail.com" }

5. list all collections in sports database.

db.cricket.find()
{ "_id" : ObjectId("5ea6dce14120338622dc6a4a"), "name" : "palyer1", "age" : 19, "email" : "palyer1@gmail.com" }
{ "_id" : ObjectId("5ea6dd944120338622dc6a4b"), "name" : "palyer2", "age" : 21, "email" : "palyer2@gmail.com" }
{ "_id" : ObjectId("5ea6ddb04120338622dc6a4c"), "name" : "palyer3", "age" : 22, "email" : "palyer3@gmail.com" }


 db.football.find()
{ "_id" : ObjectId("5ea6dde34120338622dc6a4d"), "name" : "palyer1", "age" : 21, "email" : "palyer1@gmail.com" }
{ "_id" : ObjectId("5ea6de1e4120338622dc6a4e"), "name" : "palyer2", "age" : 23, "email" : "palyer2@gmail.com" }
{ "_id" : ObjectId("5ea6de314120338622dc6a4f"), "name" : "palyer3", "age" : 20, "email" : "palyer3@gmail.com" }

db.TT.find()
{ "_id" : ObjectId("5ea6de4a4120338622dc6a50"), "name" : "palyer1", "age" : 20, "email" : "palyer1@gmail.com" }
{ "_id" : ObjectId("5ea6de5a4120338622dc6a51"), "name" : "palyer2", "age" : 25, "email" : "palyer2@gmail.com" }
{ "_id" : ObjectId("5ea6de6f4120338622dc6a52"), "name" : "palyer3", "age" : 22, "email" : "palyer3@gmail.com" }

6. rename `TT` collection to `tennis`.\
db.TT.renameCollection("tennis")

7. create a capped collection called `khokho` which should have max 3 documents.
  Try inserting more than 3 and output the result here ?
  db.createCollection("khokho", {capped:true, size:30, max: 3})

8. check whether a collection is capped or not?
db.khokho.isCapped()
true

9. remove all documents from `football` collection.
db.football.remove({})

10. delete cricket collection completely.
db.cricket.drop()

11. rename database sports to games

12. delete sports database. 
db.dropDatabase()
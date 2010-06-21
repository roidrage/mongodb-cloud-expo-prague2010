!SLIDE bullets

<ul>
<li>Introduction</li>
<li>Basic CRUD</li>
<li><span class="current">Schema Design</span></li>
<li>Scaling Up</li>
</ul>

!SLIDE

## Schemaless = Flexibility ##

!SLIDE

## Simply add or remove data. ##

!SLIDE

## Data belonging together ##
## can be stored together. ##

!SLIDE

## Read vs. write patterns ##

!SLIDE

# Blog posts #

!SLIDE javascript

    @@@ javascript
    var post = {
      title: "MongoDB",
      published: Date(),
      author: "mathias",
      contents: "MongoDB is a schemaless..",
      tags: ["mongodb", "nosql"]
    }
    
    db.posts.save(post)

!SLIDE javascript

## Finding Documents ##

    @@@ javascript
    db.posts.find({title: "MongoDB"})

!SLIDE javascript

## Multiple Conditions ##

    @@@ javascript
    db.posts.find(
      {title: "MongoDB", author: "mathias"}
    )

!SLIDE

# $ #

## Query Operators ##

!SLIDE javascript

## $or ##

    @@@ javascript
    db.posts.find({
      $or: [
        {tags: "nosql"},
        {tags: "mongodb"}
      ]
    })

!SLIDE javascript

## $gt and $lt ##

    @@@ javascript
    db.posts.find({
      created: {$gt: Date()})

!SLIDE javascript

## $in ##

    @@@ javascript
    db.posts.find({
      tags: {$in: ["nosql", "mongodb"]}
    })

!SLIDE javascript

## $where ##

    @@@ javascript
    db.posts.find({
      $where: 'this.author = "mathias"'
    })

!SLIDE javascript

## Operators can be combined ##

    @@@ javascript
    db.posts.find({
      created: {$lt: Date()},
      tags: {$in: ["nosql", "mongodb"]},
      $where: 'this.author = "mathias"'
    })

!SLIDE

## [Many more operators](http://www.mongodb.org/display/DOCS/Advanced+Queries) ##

!SLIDE javascript

## Sorting ##

    @@@ javascript
    db.users.find({author: 'mathias'}).
      sort({created: -1})

!SLIDE javascript

## Grouping ##

    @@@ javascript
    db.users.group({
      key: {name: 1},
      reduce: function(doc, total) {
        total.sum += 1
      },
      initial: {sum: 0}
    })

!SLIDE javascript

## Index relevant data ##

    @@@ javascript
    db.posts.ensureIndex({author: 1})

!SLIDE bullets incremental

## Indexes and Collections ##

* Store only similar data
* For efficient indexes

!SLIDE

# Rich documents #

!SLIDE bullets incremental

* Simplify related data
* Store document metadata

!SLIDE bullets incremental

## Simplifying Relationships ##

* External data as embedded documents

!SLIDE javascript

    @@@ javascript
    db.posts.update(
      {"_id": post._id},
      {
        $push: {
          comments: {
            author: 'mathias',
            created: Date(),
            body: 'This is great!'
          }
        }
      })

!SLIDE javascript

## Queries on Embedded Documents ##

    @@@ javascript
    db.posts.find(
      {'comments.author': 'mathias'})

!SLIDE

## Index Embedded Documents ##

!SLIDE javascript

## Embed metadata ##

    @@@ javascript
    db.posts.update(
      {"_id": post._id},
      {
        $inc: {views: 1}
      }
    )

!SLIDE bullets incremental

# Why embed data? #

* No joins necessary
* All data in one place

!SLIDE bullets incremental

# Why not embed data? #

* Denormalization vs. Normalization
* Document size exceeds 4 MB

!SLIDE bullets incremental

## Capped Collections ##

* Pre-allocated size
* Roll over through LRU

!SLIDE bullets incremental

## GridFS ##

* Chunked binary storage

!SLIDE bullets incremental

## Map/Reduce ##

* Aggregate and manipulate data

!SLIDE javascript



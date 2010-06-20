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

## Many options to design documents. ##

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

!SLIDE

## [Many more operators](http://www.mongodb.org/display/DOCS/Advanced+Queries) ##

!SLIDE javascript

## Index search relevant data ##

    @@@ javascript
    db.posts.ensureIndex({author: 1})

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

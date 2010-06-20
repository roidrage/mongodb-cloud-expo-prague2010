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

## Embed metadata ##

    @@@ javascript
    db.posts.update(
      {"_id": post._id},
      {
        $inc: {views: 1}
      }
    )

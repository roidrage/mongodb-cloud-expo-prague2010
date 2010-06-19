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

## Data can be migrated on the fly. ##

!SLIDE

## No schema migrations necessary. ##

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

* Embed external data

!SLIDE javascript

    @@@ javascript
    purchase = {
      buyer: {
        name: "Mathias Meyer",
        address: {
          street: "...",
          zip: 12345,
          city: "Berlin"
        }
      }
    }

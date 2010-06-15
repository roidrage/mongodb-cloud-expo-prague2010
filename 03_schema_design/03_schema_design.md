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



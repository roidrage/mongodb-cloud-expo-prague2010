!SLIDE bullets

<ul>
<li>Introduction</li>
<li><span class="current">Basic CRUD</span></li>
<li>Schema Design</li>
<li>Scaling Up</li>
</ul>

!SLIDE

# The MongoDB Shell #

## JavaScript Interface ##

!SLIDE commandline

    $ mongo
    MongoDB shell version: 1.4.1
    url: test
    connecting to: test
    type "help" for help
    >

!SLIDE javascript

## Basic CRUD ##

    @@@ javascript
    var user = {
      name: 'Mathias',
      company: 'Peritor',
      dark_side: false
    };
 
!SLIDE javascript

## Creating Objects ##

    @@@ javascript
    db.users.save(user)

!SLIDE

## `users` is a Collection. ##

!SLIDE bullets incremental

## A collection holds similar documents. ##

* Like a relational table
* For example: Users

!SLIDE javascript

## Finding Objects ##

    @@@ javascript
    user = db.users.find({dark_side: false})
    
    {
      "_id" : ObjectId("4c178d1c761f4db3c71bd"),
      "name" : "Mathias",
      "company" : "Peritor",
      "dark_side" : false
    }

!SLIDE bullets incremental

## _id = Primary Key ##

* a.k.a. ObjectId

!SLIDE bullets incremental

## ObjectId ##

* Added automatically
* Unique document identifier
* Or pick your own key

!SLIDE javascript

## Updating Objects ##

    @@@ javascript
    user.dark_side = true
    db.users.save(user)

!SLIDE javascript

## Deleting Objects ##

    @@@ javascript
    db.users.remove(user)

!SLIDE javascript

## Delete by predicate ##

    @@@ javascript
    db.users.remove({dark_side: true})

!SLIDE

# MongoDB Niceties #

!SLIDE bullets incremental

## Atomic modifier operations ##

* Increment and decrement for counters
* Push, pop and pull for arrays
* Set specific attributes

!SLIDE javascript

## Increment and decrement ##

    @@@ javascript
    db.users.update(
      {dark_side: true},
      {$inc: {age: 1}}
    )

!SLIDE javascript

## Push ##

    @@@ javascript
    db.users.update(
      {dark_side: true},
      {$push: {tags: 'clouds'}}
    )

!SLIDE javascript

## Pop ##

    @@@ javascript
    db.users.update(
      {dark_side: true},
      {$pop: {tags: 'clouds'}}
    )

!SLIDE javascript

## Set attributes ##

    @@@ javascript
    db.users.update(
      {dark_side: true},
      {$set: {helmet: true}}
    )
!SLIDE center first-slide

!SLIDE bullets incremental

# Hello #

* [Mathias Meyer](http://paperplanes.de)
* Chief Visionary at [Peritor](http://peritor.com)
* [@roidrage](http://twitter.com)

!SLIDE center

<a href="http://scalarium.com"><img src="scalarium.png" class="no-shadow"/></a>

# EC2 Cloud Management and Deployment #

[@scalarium](http://twitter.com/scalarium)

!SLIDE bullets

# Agenda #

<ul>
<li><span class="current">Introduction</span></li>
<li>Basic CRUD</li>
<li>Schema Design</li>
<li>Scaling Up</li>
<li>Famous Last Words</li>
</ul>

!SLIDE bullets incremental

# What is MongoDB? #

* Open source
* High-performance
* Document-oriented database

!SLIDE center

<a href="http://10gen.com"><img src="10gen.png"/></a>

!SLIDE bullets incremental

# Documents? #

* Think Records
* Unstructured
* Self-contained
* Schemaless

!SLIDE javascript

## JSON-style Documents ##

    @@@ javascript
    {"name": "Cloud Expo Europe"}

!SLIDE ruby

## Stored as BSON ##

    @@@ javascript
    "!\000\000\000\002name\000\022\000
    \000\000Cloud Expo Europe\000\000"

!SLIDE bullets incremental

## BSON = Binary JSON ##

* Date type
* Binary data
* Regular expressions

!SLIDE

## Requires Language Drivers ##

!SLIDE javascript

## Flexible schema ##

    @@@ javascript
    {
      "name": "Cloud Expo Europe",
      "tags": ["cloud"]
    }

!SLIDE javascript

## Simple to add and remove data. ##

    @@@ javascript
    {
      "name": "Cloud Expo Europe",
      "location": "Prague",
      "tags": ["cloud"]
    }

!SLIDE

# Dynamic Queries #

!SLIDE

# Secondary Indexes #

!SLIDE

# Map/Reduce #

!SLIDE

## Relational database + Schemaless ##

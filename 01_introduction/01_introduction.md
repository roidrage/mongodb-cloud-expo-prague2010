!SLIDE center first-slide

!SLIDE bullets incremental

# `whoami` #

* Mathias Meyer

!SLIDE bullets

# Agenda #

<ul>
<li><span class="current">Introduction</span></li>
<li>Basic CRUD</li>
<li>Distinctive Features</li>
<li>Scaling Up</li>
</ul>

!SLIDE bullets incremental

# What is MongoDB? #

* Open source
* High-performance
* Document-oriented database

!SLIDE javascript

# Data Model #

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

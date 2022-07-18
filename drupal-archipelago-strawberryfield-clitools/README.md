# drupal-archipelago-strawberryfield-clitools
Some tools I've Made for CLI scripting of importing/manipulating Archipelago Digital Objects (and Collections) with strawberryfield manipulation

Note: this is quick and dirty, and doesn't do a lot of error checking.  Use at your own risk.

Required packages:
  jq
  php

A little bit about my setup for context:
* There is a "digital object collection" heirarchy where there are collections nested inside publishers.
* each collection has one or more "digital objects" that represent different models (or a group of the same model in different poses)
* Most of the end objects are copyrighted, so for now I mark them as private until I spend more time customizing that object appropriately.
* At each level, I am using "subjects local" to tag the object with various characteristics
  * I have the display of that field set to produce a hyperlink to /search_grid to easy find all things related to that tag

So what I want in my solution is to:
* easily and programatically create a collection
* easily and programatically sweep up objects into the collection (set to private)
* tag objects and collections appropriately.
  * List those tags and quickly update without going into each and every object/collection on the web


Usage:  arch OBJ ACTION ....

OBJ:  do or dc (for digital_object or digital_object_collection)

ACTIONS:

list
* Lists all objects of type x (limit of 50, need to add pagination) in summary form

fetch UUID
* Fetches raw object

fetchstrawberry UUID
* extracts the strawberryfields data item

summarize UUID
* gets summary of a single object

search string
* Lists summary of all objects with title containing string

uploadfiles UUID file1 [file2 ...]
* Uploads files and adds into images/documents/models in strawberryfields

new title description tags memberof [file1 ...]
* Creates new object with title and description
* tags are mapped to subjects_local.  comma separated, make it one argument (can contain the whole argument in quotes)
* memberof is the sid of the object that is the parent of this one

tag UUID(s) set|add|remove tags
* uuids space seperated in same argument if used
* tags comma seperated in same arg

private UUID(s) true|false
* uuids space seperated in same argument if used

setgroup|group  UUID group
* sets ismemberof to sid of a collection

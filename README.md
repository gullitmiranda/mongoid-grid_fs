NAME
----
  mongoid_grid_fs

INSTALL
-------
  gem install mongoid_grid_fs

SYNOPSIS
--------

````ruby

  require 'mongoid-grid_fs'

  g = GridFs.put readable

  GridFS.get id

  GridFS.delete id


````

DESCRIPTION
-----------
mongoid_grid_fs is pure mongoid 3  / moped implementation of the mongodb
grid_fs specification

ref: http://www.mongodb.org/display/DOCS/GridFS+Specification

it has the following features:

- implementation is on top of mongoid for portability.  moped (the drive)
  is barely used

- simple, REST-like api

- support for custom namespaces (fs.files vs. image.files)

- pathnames and io-like objects can be written to the grid

- auto-unique pathnames are generated (by default) to avoid collisions using #put

    'path/info/a.rb' -> '$object_id/a.rb'

- [] and []= methods which allow the grid to be used like a giant file
  hash in the sky

- supprt for data_uris

  ````erb

    <%= image_tag :src => file.data_url %>

  ````

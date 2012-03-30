Wordpress to Plone importer
===========================

A self-contained script that will import all the posts and the comments from
a Wordpress 3.x database to a Plone site.

Introduction
------------

After reading davisagli's excellent post titled "Notes on migrating this blog
from Wordpress to Plone" ( URL ), I created this script that will automate all
the operations needed to perform a data migration from a Wordpress database to
a Plone 4 site.

The script will do the following:

    - Perform security authentication procedures so it has the necessary rights
      to create content in Plone;
    - Connect to a MySQL database-server and read a Wordpress database;
    - Extract a subset of content and metadata, from posts and comments;
    - Convert this information in a number of 'News Item' and Comment objects;
    - Recatalog and publish the newly created items.


Status
------

Right now, the script will connect and read data from a MySQL database server.

It uses the MySQL-python library to connect and execute SQL queries.


Usage
-----

Before running, open the script in an editor and modify the MySQL database
connection parameters.

The script will create a temporary directory (e.g.
"wp-import-wp-import-2012-03-30t13-28-12-180396" and start creating content
inside it.

IMPORTANT! Run the script first on a staging or development server.
           DO NOT blindly run this on a production instance!

Run with:

    bin/instance run wp2plone.py


Credits
-------

davisagli (http://www.davisagli.com)
zedr (http://github.com/zedr)


License and warning
-------------------
Permission is hereby granted, free of charge, to any person obtaining a
copy of this software and associated documentation files (the "Software"),
to deal in the Software without restriction, subject to the following
conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL
THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER
DEALINGS IN THE SOFTWARE.

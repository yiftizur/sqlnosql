<span style="color:#000000;font-family:Calibri;font-size:15">To </span><span style="color:#e49436;font-weight:bold;font-family:Calibri;font-size:30">SQL</span><span style="color:#000000;font-family:Calibri;font-size:15"> or </span><span style="color:#e49436;font-weight:bold;font-family:Calibri;font-size:30">NO</span><span style="color:#000000;font-family:Calibri;font-size:15">t to</span> <span style="color:#e49436;font-weight:bold;font-family:Calibri;font-size:30">SQL</span>

---

# What is SQL?

- _**S**tructured **Q**uery **L**anguage_ <!-- .element: class="fragment" -->
- Used to Query structured data <!-- .element: class="fragment" -->
- Using Relational Databases <!-- .element: class="fragment" -->

---

# Relational DBs

- MySQL <!-- .element: class="fragment" -->
- PostgreSQL <!-- .element: class="fragment" -->
- MS SQL <!-- .element: class="fragment" -->
- SQLite <!-- .element: class="fragment" -->
- Many more <!-- .element: class="fragment" -->

+++

# Relational DBs

- Collection of Data items organized in a table, using a schema <!-- .element: class="fragment" -->
- Very (Very) usefull when we know how the data will look like (it's structure) <!-- .element: class="fragment" -->
- Break down data (de-normalize) to tables (Relations) to increase performance and reduce data duplication <!-- .element: class="fragment" -->
- Powerful JOIN operations on tables to intersect data <!-- .element: class="fragment" -->

+++

# Relational DBs

- Data is stored in rows on file system <!-- .element: class="fragment" -->
- Fields of tables can be Indexed - faster searching and sorting, but more storage space <!-- .element: class="fragment" -->
- All coloumns of a row  are read <!-- .element: class="fragment" -->
- More Scale-Up oriented (Although changing now)<!-- .element: class="fragment" -->

+++

# MySQL 

- Most popular open-source relational DB, stable and consistenet for a while now <!-- .element: class="fragment" -->
- Used as the DB for our Admin application (both in intel and in DY) <!-- .element: class="fragment" -->
- Postgresql is slowly getting more traction because of it's great community <!-- .element: class="fragment" -->
- MySQL has a Drop-In replacement called MariaDB, that is also gaining more followers <!-- .element: class="fragment" -->

---

# So what does NoSQL mean?

- It just means data is not in tables as Relational DBs define.... <!-- .element: class="fragment" -->
- No predefiend schema <!-- .element: class="fragment" -->
- Comes in many different sizes and shapes <!-- .element: class="fragment" -->
- Very scale and HA oriented <!-- .element: class="fragment" -->

---

# NoSQL Types

- Key Value DBs <!-- .element: class="fragment" -->
- Document Stores <!-- .element: class="fragment" -->
- Column Oriented DBs <!-- .element: class="fragment" -->
- Graph DBs <!-- .element: class="fragment" -->

+++

# Key Value DBs

- Redis <img src="https://scottlinux.com/wp-content/uploads/2014/10/redis-logo.png" width="120px" height="120px" style="float: right;border: #000000 0px"/>
- AeroSpike <img src="https://res.cloudinary.com/crunchbase-production/image/upload/v1495317741/xdb3tzzpyrcyje4bwmdg.png" width="120px" height="120px" style="float: right;border: #000000 0px"/>
- Memcached <img src="https://blog.elijaa.org/wp-content/uploads/2012/02/Memcached_Logo_White.png" width="120px" height="120px" style="float: right;border: #000000 0px"/>
- DynamoDB <img src="https://www.celayix.com/wp-content/uploads/2017/06/DynamoDB-Amazon-Web-Services.png" width="120px" height="120px" style="float: right;border: #000000 0px"/>

+++

# Key Value DBs

- Manage data in a _Hashtable_* like structure(* not really)
- Key points to data value, which can be a any object from primitives to set/list/hashtables....
- Most famous is Redis (we use it a lot!)
- Redis saves all data in RAM (syncs data to disk periodically) - Fast access
- Redis currently Scales Up, however clustering is not figured out yet completely

+++

# Document DBs

- ElasticSearch <img src="https://static-www.elastic.co/assets/blt6050efb80ceabd47/elastic-logo%20(2).svg?q=540" width="120px" height="120px" style="float: right;border: #000000 0px"/>
- MongoDB <img src="http://cdn.rancher.com/wp-content/uploads/2016/01/26001728/mongodb-logo.png" width="120px" height="120px" style="float: right;border: #000000 0px"/>
- CouchDB <img src="https://wiki.apache.org/couchdb/FrontPage?action=AttachFile&do=get&target=couch.png" width="120px" height="120px" style="float: right;border: #000000 0px"/>

+++

# Document DBs

- Data is mapped as Key to Document (relative of Key-Value Store)
- Each document can be totally differnt  (no schema)
- Offers richer querying on data (query on data) - Document Stores use the metadata in the document to classify the content

+++

# ElasticSearch

- Was created by an Israeli!! (Shay Banon) <img src="http://www.abflags.com/_flags/flags-of-the-world/Israel%20flag/Israel%20flag-XXL-anim.gif" width="120px" height="120px" style="float: right;border: #000000 0px"/>
- Based on Apache Lucene (indexing and searching library)
- Offers rich Querying and Metadata on the documents stored
- Used for recommendations (offers internal scoring of documents on likeness to others)

+++

# Column Oriented DBs

- HBase <img src="https://mapr.com/products/product-overview/apache-hbase/assets/apache-hbase-image.png" width="80px" height="80px" style="float: right;border: #000000 0px"/>
- Cassandra <img src="http://redglue.eu/wp-content/uploads/Cassandra-300x201.png" width="80px" height="80px" style="float: right;border: #000000 0px"/>
- ScyllaDB <img src="http://www.scylladb.com/wp-content/uploads/mascot.svg" width="80px" height="80px" style="float: right;border: #000000 0px"/>
- Parquet <img src="https://cdn.dribbble.com/users/299/screenshots/1625979/parquet-drib.png" width="80px" height="80px" style="float: right;border: #000000 0px"/>

+++
# Column Oriented DBs

- Stores tables by *Column* and not by row
- Still uses *Row* as concept - key to list of columns
- Better optimized for storage and compression of data, as well as querying and filtering data
- Can be queried with (_similar to_) SQL queries

+++

# Column Oriented DBs

- HBase is used in DY extensivley - both for raw data and aggregated data
- ScyllaDB - written as a Cassandra drop-in replacement in C++ (instead of Java) - Yoav POC
- Parquet - a Data Store that we use in Intel for a more effienct way of querying raw data over S3

+++

# Graph DBs

- <p>Neo4J <img src="http://info.neo4j.com/rs/773-GON-065/images/neo4j_logo_globe.png" width="80px" height="80px" style="float: right;border: #000000 0px"/></p>
- <p>ArangoDB <img src="https://www.arangodb.com/wp-content/uploads/2013/03/ArangoDB-logo.png" width="80px" height="80px" style="float: right;border: #000000 0px"/></p>
- <p>OrientDB <img src="http://orientdb.com/wp-content/uploads/2014/09/orientdb_logo_2x11.png" width="80px" height="80px" style="float: right;border: #000000 0px"/></p>

+++

# Graph DBs

- New(ish) kind of DBs that saves data as Grpahs (nodes and edges)
- Nodes = Entities, Edges = Relationship
- The Graph structure is used for querying and traversing the data
- Each DB has it's own querying language

---

# What's next?

- NoSQL started as a big movement to break away from the conventional Relational DBs
- Driven mostly by Web and Big Data (Google Big Map is source of HBase and much more)
- Now days... everybody is doing everything
- Postgresql offers JSON (document) type of storage and queries
- SQL Queries over Column or Key-Value data (like Presto or Apache Drill)

---

# (NO) Questions?

<img src="https://s-media-cache-ak0.pinimg.com/originals/0e/97/c2/0e97c2314c93c688142f38b8c496b34b.jpg" width="400px" height="500px" style="float: center;border: #000000 0px"/>





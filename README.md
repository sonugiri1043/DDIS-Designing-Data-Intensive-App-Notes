# Designing Data Intensive Application

We call an application data-intensive if data is its primary challenge - the quantity of data, the complexity of data, or the speed at which it is changing - as opposed to compute-intensive, where CPU cycles are the bottleneck.

# Chapter 1

# Reliable, Scalable, and Maintainable Applications

A data-intensive application is typically built from standard building blocks that provide commonly needed functionality. Many applications need to:

- Store data so that they, or another application, can find it again later (**databases**)
- Remember the result of an expensive operation, to speed up reads (**caches**)
- Allow users to search data by keyword or filter it in various ways (**search indexes**)
- Send a message to another process, to be handled asynchronously (**stream processing**)
- Periodically crunch a large amount of accumulated data (**batch processing**)

Although a database and a message queue have some superficial similarity - both store data for some time - **they have very different access patterns, which means different characterstics**, and thus very different implementation.

There are datastores that are also used as message queues (Redis), and there are message queues with database-like durability guarantees (Apache Kafka).

If you have an application-managed caching layer (using Memcached or similar), or a full-text search server (such as Elasticsearch or Solr) separate from your main database, it is normally the application code’s responsibility to keep those caches and indexes in sync with the main database.

Figure 1-1 One possible architecture for a data system that combines several components.

![alt text](http://url/to/img.png)


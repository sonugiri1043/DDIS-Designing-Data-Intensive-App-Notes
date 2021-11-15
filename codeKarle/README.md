# codeKarle
## Database Design Tips ([video](https://www.youtube.com/watch?v=cODCpXtPHbQ))
Choice of database depends on three factors:
- Structure of data
- Query pattern
- Scale

### Cache
**Redis, Memcached, etcd, Hazelcast**
- Used when same data is queried many times, querying from the primary data source has a high latency.

### File/Blob Storage
**Amazon S3**
- Used storing images, videos, etc.
- Usually used together with a CDN.

### Text Search
**ElasticSearch, Solr (Both built on Apache Lucene)**
- Used for searching in text data like Amazon product information or Netflix movie/show information.
- Supports fuzzy search (search within a certain edit distance)
- These are not databases and there is no guarantee against data loss, so they should be used with some other primary source of data.

### Metrics
**InfluxDB, OpenTSDB**
- Time series database
- Optimised for:
  - Sequential, append only writes
  - Bulk read for a given time range
  - No random read/write

### Analytics
**Hadoop**
- Large amount of data
- Data warehouse

### Relational vs. Non-relational database
![relational-vs-non-relational](images/relational_vs_non_relational.drawio.svg)

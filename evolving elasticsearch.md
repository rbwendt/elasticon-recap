# Evolving Elasticsearch


## Usability

* query / filter merge
* query auto-caching
* structured exceptions
* admin safeguards, "requested 10000 results" warning


## What's a columnar store?

* store data on disk as columns instead of rows.

![columnar comparison](columnar.png)


## better data structures

Doc Values:
* doc values are stored (columnar) on disk, leading to less memory pressure, but slower
* Some data structures use a lot of memory (aggregations, sorting)
* field length norms (way of boosting relevance of shorter records) rewritten
  using lucence doc values
* parent child will use doc values, faster joins


## Security

* Now taking security seriously.
* JarHell check, looks for duplicate jars. For removing stale dependencies
* Java Security Manager. Authorization for java code. Now using minimal privileges.
* Modularization of core so that privileges are only granted where needed


## Tests

* You can't claim to support it unless it is tested.
* Unit testable code. refactor and rewritten so things could be unit tested
* core plugins get tests
* real integration tests. Take zip file, unpack, install, start node, form a cluster, run tests of what a user would do


## query profiler


## Post process results of other aggregations

* Position → velocity
* anomaly detection


## release schedule

* users want quick bug fixes but also stability.
* developers want frequent releases and few versions to support.
* release schedule
  * bugfix (current minor, last minor of previous major)
  * minor (frequent, small, no breaking changes)
  * major (more frequent, smaller, breaking, reindexing)
* any minor of previous major should move forward


## reindex api

* query to reindex a subset of your data
* update by query


## task manager
* long running tasks
* stats, cancellation, throttling


## ingest node

* power of logstash filters available in es
* data transformation (e.g. tabular to json)
* wraps index/bulk api


## painless scripting
* new experimental scripting language called "painless"
* ships, but disabled by default
* fast and secure
* detects infinite loops
* dynamic / static
* static is 10x faster


## data structures
* string mappings
  * text field: full analysis
  * keyword field: concrete string value: limited keyword analysis, sorting
* replace encoding for numeric, date, ipv4.
 * can start supporting arbitrary lengths, e.g. big integer
* Geo fields: combine geo points and geo shapes (experimental)


### completion suggester
* document oriented!
* boost by prefix length, etc


### search after
* deep paging with linear performance

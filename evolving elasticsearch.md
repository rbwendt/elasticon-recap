#Evolving Elasticsearch


* breaking change to mapping. Now consistent.
* durable transaction log

## Usability

* query / filter merge
* query auto-caching
* merge auto-throttling
* structured exceptions
* admin safeguards, "requested 10000 results" warning

## heap usage better data structures

* doc values are columnar on disk, less memory pressure but fast
* Some data structures use a lot of memory (aggregations, sorting)
* Columnar store file system cache on by default
* field length norms rewritten using lucence doc values
* parent child, doc values, faster joins
* geo points v2, doc values, 50% index size, up to 10x query speed

## Security

* Now taking security seriously.
* JarHell check, looks for duplicate jars. For removing stale dependencies
* Java Security Manager. Authorization for java code. Now using minimal privileges.
* Modularization of core so that privileges are only granted where needed
* remove java serialization (java security bug)

## Tests

* You can't claim to support it unless it is tested.
* Unit testable code. refactor and rewritten so things could be unit tested
* core plugins get tests
* real integration tests. Take zip file, unpack, install, start node, form a cluster, run tests of what a user would do

## Stability

## Post process results of other aggregations

* Position -> velocity
* anomaly detection
* geo centroid aggregation

## query profiler

## release schedule

* users want quick bug fixes but also stability.
* developers want frequent releases and few versions to support.
* release schedule
** bugfix (current minor, last minor of previous major)
** minor (frequent, small, no breaking changes)
** major (more frequent, smaller, breaking, reindexing)
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

## scripting
* disable scripting by default

## painless scripting
* new experimental scripting language called "painless"
* ships, but disabled by default
* fast
* secure
* detects infinite loops
* dynamic / static
* static is 10x faster

## data structures
* string mappings
** text field: full analysis
** keyword field: concrete string value: limited keyword analysis, sorting
* point field encoding: k-dimensional tree, replace encoding for numeric, date, ipv4.
** can start supporting arbitary lengths, e.g. big integer
* Geo fields: combine geo points and geo shapes (experimental)

## search

### completion suggester
* document oriented!
* boost by prefix length, etc

### search after
* deep paging with linear performance

### search refactor
* stricter parsing
* improved caching
* flexible search phrases

# Java HTTP client
* decouple server client
* core becomes server
* single system boundary
* aligns clients across languages
* minimal dependencies


# Resiliency

* refactor settings api

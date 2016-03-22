
## heap usage better data structures

* doc values are columnar on disk, less memory pressure but fast
* Some data structures use a lot of memory (aggregations, sorting)
* Columnar store file system cache on by default
* field length norms rewritten using lucence doc values
* parent child, doc values, faster joins
* geo points v2, doc values, 50% index size, up to 10x query speed

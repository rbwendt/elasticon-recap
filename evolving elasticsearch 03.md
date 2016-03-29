
## better data structures

Doc Values:
* doc values are columnar on disk, leading to less memory pressure, but slower
* Some data structures use a lot of memory (aggregations, sorting)
* field length norms (way of boosting relevance of shorter records) rewritten
  using lucence doc values
* parent child will use doc values, faster joins

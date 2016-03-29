# Stored events

* Using rollups grants better latency than log style records.
* 1 day rollup: url, date, visitors (exlude from source due to high cardinality), metics (views, engaged seconds, etc), meta data (meta data of document: author, section, etc)
* 5 minute rollup: same structure as day, but with 5 minute span. For more granular or real time reporting
* raw event: formatted just like a rollup document. Single page view. Capture millions per day
* These each are in different document types, with different indexes.

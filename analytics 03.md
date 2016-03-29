# Data tips

* Avoid fielddata. Use doc_values where possible.
* Don't use _source especially if your schema has high cardinality multi value fields

## Two ways to boosting solr search result
1. Add priority score value in indexed fields within solr schema.
2. Add priority score value during search query.

For 2<sup>nd</sup> option below query parameter can be use to prioritize the result.
* **q** = Define the raw input string for the query. eg: _text_:"test"
* **deftype** = Used to define query parser. eg: "defType": "dismax"
* **qf** = Query fields specifies the fields in the index on which to perform the query. eg: "qf": "title^10.0 description^10.0 author^5.0"




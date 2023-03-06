## Delete solr index code in xml format from solr server ui.
```
<delete><query>country:"CA" AND language:"fr_ca"</query></delete>
```

## Delete solr data through curl command
```
curl -X POST -H 'Content-Type: application/json' --data-binary '{"delete":{"query":"*:*" }}' http://localhost:8983/solr/my_collection/update
```

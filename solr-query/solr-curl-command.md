## Index data (add/update) into solr server
```
curl --location --request POST 'http://localhost:8983/solr/techieCollection/update?commit=true' \
--header 'Authorization: Basic {auth_token}' \
--header 'Content-Type: application/json; charset=latin1' \
--data-raw '[
	{
		"id":"2241se121",
		"title":"testing data01 index",
		"country":"US",
		"language":["en_us"]		
	},
	{
		"id":"43352fw3213",
    "title":"testing data02 index",
		"country":"US",
		"language":["en_us"]
	}
]'
```

## Delete solr data from server
```
curl --location --request POST 'http://localhost:8983/solr/techieCollection/update?commit=true' \
--header 'Authorization: Basic {auth_token}' \
--data-raw '{
  "delete": [{
        "id":"2241se121"
        },
        {
        "id":"43352fw3213"
        }
      ]
   }'
```   

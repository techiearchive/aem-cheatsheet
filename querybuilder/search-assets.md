To fetch only activated assets.
====================================================

### Tool
* [QueryBuilder Debugger](http://localhost:4502/libs/cq/search/content/querydebug.html)

### Search activated pdf files
```
path=/content/dam/we-retail
type=dam:Asset
p.limit=-1
1_property=@jcr:content/metadata/dc:format
1_property.1_value=application/pdf
2_property=@jcr:content/cq:lastReplicationAction
2_property.value=Activate
3_property=@jcr:content/metadata/dc:site-nodes
3_property.operation=exists
```

### Search pdf files from "/content/dam/we-retail" path and ignore "/content/dam/we-retail/en/products" path in search result.
```
p.limit=-1
group.p.and=true
group.1_group.path=/content/dam/we-retail
group.1_group.type=dam:Asset
group.2_group.p.not=true
group.2_group.path=/content/dam/we-retail/en/products
group.2_group.path.self=true
group.1_group.1_property=@jcr:content/metadata/dc:format
group.1_group.1_property.1_value=application/pdf
group.1_group.2_property=@jcr:content/cq:lastReplicationAction
group.1_group.2_property.value=Activate
group.1_group.3_property=@jcr:content/metadata/dc:site-nodes
group.1_group.3_property.operation=exists
```

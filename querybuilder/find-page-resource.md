### Tool
* [QueryBuilder Debugger](http://localhost:4502/libs/cq/search/content/querydebug.html)

### find the page content based on page resource type.
```
path=/content/we-retail/language-masters/en
type=cq:PageContent
p.limit=-1
1_property=sling:resourceType
1_property.1_value=we-retail/components/pages/page-article
```
### Find the pages where particular component resource used.
```
path=/content/we-retail
type=nt:unstructured
p.limit=-1
property=sling:resourceType
property.value=we-retail/components/content/carousel
```

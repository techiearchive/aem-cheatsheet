Sample group query
=========

### Tool
* [QueryBuilder Debugger](http://localhost:4502/libs/cq/search/content/querydebug.html)

### Example

Grouping two different condition with or operation.
* Page offtime is exists
* Page offtime should be greater than current datetime.

```
p.limit=10
p.nodedepth=1
p.offset=0
p.hits=full
type=cq:Page
orderby.sort=desc
orderby=@jcr:content/publishDate
excludepaths=/content/we-retail/us/en/demo-page
group.p.or=true
group.1_group.1_group.p.and=true
group.2_group.1_group.p.and=true

group.1_group.path=/content/we-retail/us/en
group.1_group.1_group.1_property=@jcr:content/cq:template
group.1_group.1_group.1_property.1_value=/conf/we-retail/settings/wcm/templates/product-page
group.1_group.1_group.2_property=@jcr:content/contentType
group.1_group.1_group.2_property.1_value=we-retail:apparel/coat
group.1_group.1_group.property=@jcr:content/offTime
group.1_group.1_group.property.operation=exists
group.1_group.1_group.property.value=false

group.2_group.path=/content/we-retail/us/en
group.2_group.1_group.daterange.property=@jcr:content/offTime
group.2_group.1_group.daterange.lowerBound=2021-07-28
group.2_group.1_group.daterange.lowerOperation=>=
group.2_group.1_group.1_property=@jcr:content/cq:template
group.2_group.1_group.1_property.1_value=/conf/we-retail/settings/wcm/templates/product-page
group.2_group.1_group.2_property=@jcr:content/contentType
group.2_group.1_group.2_property.1_value=we-retail:apparel/coat
```

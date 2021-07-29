To fetch only those pages which are not expired.
=========

### Tool
* [QueryBuilder Debugger](http://localhost:4502/libs/cq/search/content/querydebug.html)

### Example 1

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
group.2_group.1_group.daterange.lowerBound=2021-07-28T19:18:59.845561
group.2_group.1_group.1_property=@jcr:content/cq:template
group.2_group.1_group.1_property.1_value=/conf/we-retail/settings/wcm/templates/product-page
group.2_group.1_group.2_property=@jcr:content/contentType
group.2_group.1_group.2_property.1_value=we-retail:apparel/coat
```

### Example 2

Another example about group inside parent group.

```
p.limit=12
p.nodedepth=1
orderby.sort=desc
p.offset=0
orderby=@jcr:content/publishDate
p.hits=full
type=cq:Page
group.p.or=true
excludepaths=/content/we-retail/us/en/demo-page

group.1_group.1_group.property=@jcr:content/offTime
group.1_group.1_group.property.operation=exists
group.1_group.1_group.property.value=false

group.1_group.1_group.p.and=true
group.2_group.1_group.p.and=true
group.1_group.1_group.group.p.or=true
group.2_group.1_group.group.p.or=true

group.2_group.path=/content/we-retail/us/en
group.2_group.1_group.daterange.property=@jcr:content/offTime
group.2_group.1_group.daterange.lowerBound=2021-07-29T16:07:53.996113800

group.1_group.1_group.group.2_property=jcr:content/gender
group.1_group.1_group.group.2_property.1_value=we-retail:gender/men

group.1_group.1_group.group.3_property=jcr:content/season
group.1_group.1_group.group.3_property.1_value=we-retail:season/summer

group.2_group.1_group.group.2_property=jcr:content/gender
group.2_group.1_group.group.2_property.1_value=we-retail:gender/men

group.2_group.1_group.group.3_property=jcr:content/season
group.2_group.1_group.group.3_property.1_value=we-retail:season/summer

group.1_group.path=/content/we-retail/us/en
group.1_group.1_group.1_property=@jcr:content/cq:template
group.1_group.1_group.1_property.1_value=/conf/we-retail/settings/wcm/templates/product-page
group.2_group.1_group.1_property=@jcr:content/cq:template
group.2_group.1_group.1_property.1_value=/conf/we-retail/settings/wcm/templates/product-page
```

The xpath query will look like below

```
(
  /jcr:root/content/we-retail/us/en//element(*, cq:Page)
  [
  ((jcr:content/@gender = 'we-retail:gender/men')
  or (jcr:content/@season = 'we-retail:season/summer'))
  and (not(jcr:content/@offTime)
  and (jcr:content/@cq:template = '/conf/we-retail/settings/wcm/templates/product-page'))
  ]
|
  /jcr:root/content/we-retail/us/en//element(*, cq:Page)
  [
  ((jcr:content/@gender = 'we-retail:gender/men')
  or (jcr:content/@season = 'we-retail:season/summer'))
  and ((jcr:content/@offTime > xs:dateTime('2021-07-29T16:07:53.996+05:30'))
  and (jcr:content/@cq:template = '/conf/we-retail/settings/wcm/templates/product-page'))
  ]
  order by jcr:content/@publishDate descending
)

## Filtering predicates

{excludepaths=excludepaths: excludepaths=/content/we-retail/us/en/demo-page}
```

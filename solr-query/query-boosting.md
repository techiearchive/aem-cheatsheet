## Solr query boosting to fetch the sorted result based on maximum matching search term
```
q=(name:"suresh")^=1 OR (name:"vikas")^=1 OR (name:"ramesh")^=1 OR (age:"30")^=1
fq=template:"article-page"
fq=country:"us"
fq=language:"en_us"
fl=id,name,publishDate,template,score
```

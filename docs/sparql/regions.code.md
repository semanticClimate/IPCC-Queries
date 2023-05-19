# regions.rq
**Code examples:** [curl](#curl)
### SPARQL
```sparql
PREFIX wdt: <https://kg-ipclimatec-reports.wikibase.cloud/prop/direct/>
PREFIX wd:  <https://kg-ipclimatec-reports.wikibase.cloud/entity/>
PREFIX p:   <https://kg-ipclimatec-reports.wikibase.cloud/prop/>
PREFIX pq:  <https://kg-ipclimatec-reports.wikibase.cloud/prop/qualifier/>

PREFIX rwdt: <http://www.wikidata.org/prop/direct/>

SELECT ?specialScope ?specialScopeLabel (COUNT(DISTINCT ?statement) AS ?count) WHERE {
  ?paragraph p:P3 ?statement .
  ?statement pq:P9 ?specialScope .
  ?specialScope wdt:P1 wd:Q42 .
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
} GROUP BY ?specialScope ?specialScopeLabel
  ORDER BY DESC(?count)
```
[run](https://kg-ipclimatec-reports.wikibase.cloud/query/embed.html#PREFIX%20wdt%3A%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fdirect%2F%3E%0APREFIX%20wd%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fentity%2F%3E%0APREFIX%20p%3A%20%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2F%3E%0APREFIX%20pq%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fqualifier%2F%3E%0A%0APREFIX%20rwdt%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fprop%2Fdirect%2F%3E%0A%0ASELECT%20%3FspecialScope%20%3FspecialScopeLabel%20%28COUNT%28DISTINCT%20%3Fstatement%29%20AS%20%3Fcount%29%20WHERE%20%7B%0A%20%20%3Fparagraph%20p%3AP3%20%3Fstatement%20.%0A%20%20%3Fstatement%20pq%3AP9%20%3FspecialScope%20.%0A%20%20%3FspecialScope%20wdt%3AP1%20wd%3AQ42%20.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22.%20%7D%0A%7D%20GROUP%20BY%20%3FspecialScope%20%3FspecialScopeLabel%0A%20%20ORDER%20BY%20DESC%28%3Fcount%29%0A) or [edit](https://kg-ipclimatec-reports.wikibase.cloud/query/#PREFIX%20wdt%3A%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fdirect%2F%3E%0APREFIX%20wd%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fentity%2F%3E%0APREFIX%20p%3A%20%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2F%3E%0APREFIX%20pq%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fqualifier%2F%3E%0A%0APREFIX%20rwdt%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fprop%2Fdirect%2F%3E%0A%0ASELECT%20%3FspecialScope%20%3FspecialScopeLabel%20%28COUNT%28DISTINCT%20%3Fstatement%29%20AS%20%3Fcount%29%20WHERE%20%7B%0A%20%20%3Fparagraph%20p%3AP3%20%3Fstatement%20.%0A%20%20%3Fstatement%20pq%3AP9%20%3FspecialScope%20.%0A%20%20%3FspecialScope%20wdt%3AP1%20wd%3AQ42%20.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22.%20%7D%0A%7D%20GROUP%20BY%20%3FspecialScope%20%3FspecialScopeLabel%0A%20%20ORDER%20BY%20DESC%28%3Fcount%29%0A)


### Output
<table>
  <tr>
    <td><b>specialScope</b></td>
    <td><b>count</b></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q44">Africa</a></td>
    <td>5</td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q47">South America</a></td>
    <td>5</td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q48">Arctic</a></td>
    <td>5</td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q45">Asia</a></td>
    <td>4</td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q46">Central America</a></td>
    <td>4</td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q301">Europe</a></td>
    <td>3</td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q298">Greenland ice sheet</a></td>
    <td>2</td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q312">Australasia</a></td>
    <td>2</td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q51">North America</a></td>
    <td>2</td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q299">West Antarctic Ice Sheet</a></td>
    <td>1</td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q306">Arctic sea</a></td>
    <td>1</td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q307">Northern Hemisphere</a></td>
    <td>1</td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q308">South Asia</a></td>
    <td>1</td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q311">East Africa</a></td>
    <td>1</td>
  </tr>
</table>
## Code examples
### curl
```shell
curl -s https://raw.githubusercontent.com/egonw/IPCC-Queries/master/sparql/regions.rq \
  | sed 's+<lang/>+en+' > regions.rq

curl -H "Accept: text/tab-separated-values" \
  -G https://kg-ipclimatec-reports.wikibase.cloud/query/sparql \
  --data-urlencode query@regions.rq
```
This SPARQL query is available under CCZero.

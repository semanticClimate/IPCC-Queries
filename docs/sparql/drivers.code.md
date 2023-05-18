# drivers.rq
**Code examples:** [curl](#curl)
### SPARQL
```sparql
PREFIX wdt: <https://kg-ipclimatec-reports.wikibase.cloud/prop/direct/>
PREFIX wd:  <https://kg-ipclimatec-reports.wikibase.cloud/entity/>
PREFIX p:   <https://kg-ipclimatec-reports.wikibase.cloud/prop/>
PREFIX pq:  <https://kg-ipclimatec-reports.wikibase.cloud/prop/qualifier/>

SELECT ?driver ?driverLabel (COUNT(DISTINCT ?statement) AS ?count) WHERE {
  ?paragraph p:P3 ?statement .
  ?statement pq:P18 ?driver .
  ?driver wdt:P6+ wd:Q276 .
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
} GROUP BY ?driver ?driverLabel
  ORDER BY DESC(?count)
```
[run](https://kg-ipclimatec-reports.wikibase.cloud/query/embed.html#PREFIX%20wdt%3A%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fdirect%2F%3E%0APREFIX%20wd%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fentity%2F%3E%0APREFIX%20p%3A%20%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2F%3E%0APREFIX%20pq%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fqualifier%2F%3E%0A%0ASELECT%20%3Fdriver%20%3FdriverLabel%20%28COUNT%28DISTINCT%20%3Fstatement%29%20AS%20%3Fcount%29%20WHERE%20%7B%0A%20%20%3Fparagraph%20p%3AP3%20%3Fstatement%20.%0A%20%20%3Fstatement%20pq%3AP18%20%3Fdriver%20.%0A%20%20%3Fdriver%20wdt%3AP6%2B%20wd%3AQ276%20.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22.%20%7D%0A%7D%20GROUP%20BY%20%3Fdriver%20%3FdriverLabel%0A%20%20ORDER%20BY%20DESC%28%3Fcount%29%0A) or [edit](https://kg-ipclimatec-reports.wikibase.cloud/query/#PREFIX%20wdt%3A%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fdirect%2F%3E%0APREFIX%20wd%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fentity%2F%3E%0APREFIX%20p%3A%20%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2F%3E%0APREFIX%20pq%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fqualifier%2F%3E%0A%0ASELECT%20%3Fdriver%20%3FdriverLabel%20%28COUNT%28DISTINCT%20%3Fstatement%29%20AS%20%3Fcount%29%20WHERE%20%7B%0A%20%20%3Fparagraph%20p%3AP3%20%3Fstatement%20.%0A%20%20%3Fstatement%20pq%3AP18%20%3Fdriver%20.%0A%20%20%3Fdriver%20wdt%3AP6%2B%20wd%3AQ276%20.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22.%20%7D%0A%7D%20GROUP%20BY%20%3Fdriver%20%3FdriverLabel%0A%20%20ORDER%20BY%20DESC%28%3Fcount%29%0A)


### Output
<table>
  <tr>
    <td><b>driver</b></td>
    <td><b>count</b></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q279">volcanic</a></td>
    <td>1</td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q280">solar</a></td>
    <td>1</td>
  </tr>
</table>
## Code examples
### curl
```shell
curl -s https://raw.githubusercontent.com/egonw/IPCC-Queries/master/sparql/drivers.rq \
  | sed 's+<lang/>+en+' > drivers.rq

curl -H "Accept: text/tab-separated-values" \
  -G https://kg-ipclimatec-reports.wikibase.cloud/query/sparql \
  --data-urlencode query@drivers.rq
```
This SPARQL query is available under CCZero.

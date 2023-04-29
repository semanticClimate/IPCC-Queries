# sectionsWithStatements.rq
**Code examples:** [curl](#curl)
### SPARQL
```sparql
PREFIX wdt: <https://kg-ipclimatec-reports.wikibase.cloud/prop/direct/>
PREFIX wd:  <https://kg-ipclimatec-reports.wikibase.cloud/entity/>

SELECT DISTINCT ?section ?sectionLabel (COUNT(?statement) AS ?count) WHERE {
  ?section wdt:P1 wd:Q18 ;
           wdt:P3 ?statement .
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
} GROUP BY ?section ?sectionLabel
  ORDER BY DESC(?count)
```
[run](https://kg-ipclimatec-reports.wikibase.cloud/query/embed.html#PREFIX%20wdt%3A%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fdirect%2F%3E%0APREFIX%20wd%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fentity%2F%3E%0A%0ASELECT%20DISTINCT%20%3Fsection%20%3FsectionLabel%20%28COUNT%28%3Fstatement%29%20AS%20%3Fcount%29%20WHERE%20%7B%0A%20%20%3Fsection%20wdt%3AP1%20wd%3AQ18%20%3B%0A%20%20%20%20%20%20%20%20%20%20%20wdt%3AP3%20%3Fstatement%20.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22.%20%7D%0A%7D%20GROUP%20BY%20%3Fsection%20%3FsectionLabel%0A%20%20ORDER%20BY%20DESC%28%3Fcount%29%0A) or [edit](https://kg-ipclimatec-reports.wikibase.cloud/query/#PREFIX%20wdt%3A%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fdirect%2F%3E%0APREFIX%20wd%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fentity%2F%3E%0A%0ASELECT%20DISTINCT%20%3Fsection%20%3FsectionLabel%20%28COUNT%28%3Fstatement%29%20AS%20%3Fcount%29%20WHERE%20%7B%0A%20%20%3Fsection%20wdt%3AP1%20wd%3AQ18%20%3B%0A%20%20%20%20%20%20%20%20%20%20%20wdt%3AP3%20%3Fstatement%20.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22.%20%7D%0A%7D%20GROUP%20BY%20%3Fsection%20%3FsectionLabel%0A%20%20ORDER%20BY%20DESC%28%3Fcount%29%0A)


### Output
<table>
  <tr>
    <td><b>section</b></td>
    <td><b>count</b></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q31">paragraph 2.1.2.c</a></td>
    <td>11</td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q49">paragraph 2.1.2.d</a></td>
    <td>7</td>
  </tr>
</table>
## Code examples
### curl
```shell
curl -s https://raw.githubusercontent.com/egonw/IPCC-Queries/master/sparql/sectionsWithStatements.rq \
  | sed 's+<lang/>+en+' > sectionsWithStatements.rq

curl -H "Accept: text/tab-separated-values" \
  -G https://kg-ipclimatec-reports.wikibase.cloud/query/sparql \
  --data-urlencode query@sectionsWithStatements.rq
```
This SPARQL query is available under CCZero.

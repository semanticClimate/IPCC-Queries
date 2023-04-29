# statementOnMap.rq
**Code examples:** [curl](#curl)
### SPARQL
```sparql
#defaultView:Map
PREFIX wdt: <https://kg-ipclimatec-reports.wikibase.cloud/prop/direct/>
PREFIX wd:  <https://kg-ipclimatec-reports.wikibase.cloud/entity/>
PREFIX p:   <https://kg-ipclimatec-reports.wikibase.cloud/prop/>
PREFIX pq:  <https://kg-ipclimatec-reports.wikibase.cloud/prop/qualifier/>
PREFIX ps:  <https://kg-ipclimatec-reports.wikibase.cloud/prop/statement/>
PREFIX psv: <https://kg-ipclimatec-reports.wikibase.cloud/prop/statement/value/>

PREFIX rwdt: <http://www.wikidata.org/prop/direct/>

SELECT ?paragraph ?paragraphLabel ?confidenceLabel ?text ?coordinates WHERE {
  ?paragraph p:P3 ?statement .
  ?statement pq:P9 ?specialScope ;
             pq:P5 ?confidence ;
             ps:P3 ?text .
  ?specialScope wdt:P2 ?wikidata .
  SERVICE <https://query.wikidata.org/sparql> {
    ?wikidata rwdt:P625 ?coordinates .
  }
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
}
```
[run](https://query.wikidata.org/embed.html#%23defaultView%3AMap%0APREFIX%20wdt%3A%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fdirect%2F%3E%0APREFIX%20wd%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fentity%2F%3E%0APREFIX%20p%3A%20%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2F%3E%0APREFIX%20pq%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fqualifier%2F%3E%0APREFIX%20ps%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fstatement%2F%3E%0APREFIX%20psv%3A%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fstatement%2Fvalue%2F%3E%0A%0APREFIX%20rwdt%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fprop%2Fdirect%2F%3E%0A%0ASELECT%20%3Fparagraph%20%3FparagraphLabel%20%3FconfidenceLabel%20%3Ftext%20%3Fcoordinates%20WHERE%20%7B%0A%20%20%3Fparagraph%20p%3AP3%20%3Fstatement%20.%0A%20%20%3Fstatement%20pq%3AP9%20%3FspecialScope%20%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20pq%3AP5%20%3Fconfidence%20%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20ps%3AP3%20%3Ftext%20.%0A%20%20%3FspecialScope%20wdt%3AP2%20%3Fwikidata%20.%0A%20%20SERVICE%20%3Chttps%3A%2F%2Fquery.wikidata.org%2Fsparql%3E%20%7B%0A%20%20%20%20%3Fwikidata%20rwdt%3AP625%20%3Fcoordinates%20.%0A%20%20%7D%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22.%20%7D%0A%7D%0A) or [edit](https://query.wikidata.org/#%23defaultView%3AMap%0APREFIX%20wdt%3A%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fdirect%2F%3E%0APREFIX%20wd%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fentity%2F%3E%0APREFIX%20p%3A%20%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2F%3E%0APREFIX%20pq%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fqualifier%2F%3E%0APREFIX%20ps%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fstatement%2F%3E%0APREFIX%20psv%3A%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fstatement%2Fvalue%2F%3E%0A%0APREFIX%20rwdt%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fprop%2Fdirect%2F%3E%0A%0ASELECT%20%3Fparagraph%20%3FparagraphLabel%20%3FconfidenceLabel%20%3Ftext%20%3Fcoordinates%20WHERE%20%7B%0A%20%20%3Fparagraph%20p%3AP3%20%3Fstatement%20.%0A%20%20%3Fstatement%20pq%3AP9%20%3FspecialScope%20%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20pq%3AP5%20%3Fconfidence%20%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20ps%3AP3%20%3Ftext%20.%0A%20%20%3FspecialScope%20wdt%3AP2%20%3Fwikidata%20.%0A%20%20SERVICE%20%3Chttps%3A%2F%2Fquery.wikidata.org%2Fsparql%3E%20%7B%0A%20%20%20%20%3Fwikidata%20rwdt%3AP625%20%3Fcoordinates%20.%0A%20%20%7D%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22.%20%7D%0A%7D%0A)


### Output
<table>
  <tr>
  </tr>
</table>
## Code examples
### curl
```shell
curl -s https://raw.githubusercontent.com/egonw/SARS-CoV-2-Queries/master/sparql/statementOnMap.rq | sed 's+<lang/>+en+' > statementOnMap.rq

curl -H "Accept: text/tab-separated-values" -G https://query.wikidata.org/bigdata/namespace/wdq/sparql --data-urlencode query@statementOnMap.rq
```
This SPARQL query is available under CCZero.

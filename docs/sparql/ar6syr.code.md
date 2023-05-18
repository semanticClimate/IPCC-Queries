# ar6syr.rq
**Code examples:** [curl](#curl)
### SPARQL
```sparql
PREFIX wdt: <https://kg-ipclimatec-reports.wikibase.cloud/prop/direct/>
PREFIX wd:  <https://kg-ipclimatec-reports.wikibase.cloud/entity/>

SELECT ?section ?sectionLabel ?paragraph ?paragraphLabel WHERE {
  VALUES ?report { wd:Q99 } # Q99 = AR6 Synthesis Report: Climate Change 2023
  ?section wdt:P4 ?report ; ^wdt:P4 ?paragraph .
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
} ORDER BY ASC(?sectionLabel) ASC(?paragraphLabel)
```
[run](https://kg-ipclimatec-reports.wikibase.cloud/query/embed.html#PREFIX%20wdt%3A%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fdirect%2F%3E%0APREFIX%20wd%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fentity%2F%3E%0A%0ASELECT%20%3Fsection%20%3FsectionLabel%20%3Fparagraph%20%3FparagraphLabel%20WHERE%20%7B%0A%20%20VALUES%20%3Freport%20%7B%20wd%3AQ99%20%7D%20%23%20Q99%20%3D%20AR6%20Synthesis%20Report%3A%20Climate%20Change%202023%0A%20%20%3Fsection%20wdt%3AP4%20%3Freport%20%3B%20%5Ewdt%3AP4%20%3Fparagraph%20.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22.%20%7D%0A%7D%20ORDER%20BY%20ASC%28%3FsectionLabel%29%20ASC%28%3FparagraphLabel%29%0A) or [edit](https://kg-ipclimatec-reports.wikibase.cloud/query/#PREFIX%20wdt%3A%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fdirect%2F%3E%0APREFIX%20wd%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fentity%2F%3E%0A%0ASELECT%20%3Fsection%20%3FsectionLabel%20%3Fparagraph%20%3FparagraphLabel%20WHERE%20%7B%0A%20%20VALUES%20%3Freport%20%7B%20wd%3AQ99%20%7D%20%23%20Q99%20%3D%20AR6%20Synthesis%20Report%3A%20Climate%20Change%202023%0A%20%20%3Fsection%20wdt%3AP4%20%3Freport%20%3B%20%5Ewdt%3AP4%20%3Fparagraph%20.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22.%20%7D%0A%7D%20ORDER%20BY%20ASC%28%3FsectionLabel%29%20ASC%28%3FparagraphLabel%29%0A)


### Output
<table>
  <tr>
    <td><b>section</b></td>
    <td><b>paragraph</b></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q67">2.1.1 Observed Warming and its Causes</a></td>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q66">2.1.1.a</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q30">2.1.2 Observed Climate System Changes and Impacts to Date</a></td>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q31">2.1.2.c</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q30">2.1.2 Observed Climate System Changes and Impacts to Date</a></td>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q49">2.1.2.d</a></td>
  </tr>
</table>
## Code examples
### curl
```shell
curl -s https://raw.githubusercontent.com/egonw/IPCC-Queries/master/sparql/ar6syr.rq \
  | sed 's+<lang/>+en+' > ar6syr.rq

curl -H "Accept: text/tab-separated-values" \
  -G https://kg-ipclimatec-reports.wikibase.cloud/query/sparql \
  --data-urlencode query@ar6syr.rq
```
This SPARQL query is available under CCZero.

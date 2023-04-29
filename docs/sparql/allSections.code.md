# allSections.rq
**Code examples:** [curl](#curl)
### SPARQL
```sparql
PREFIX wdt: <https://kg-ipclimatec-reports.wikibase.cloud/prop/direct/>
PREFIX wd:  <https://kg-ipclimatec-reports.wikibase.cloud/entity/>

SELECT ?section ?sectionLabel WHERE {
  ?section wdt:P1 wd:Q18 .
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
}
```
[run](https://kg-ipclimatec-reports.wikibase.cloud/query/embed.html#PREFIX%20wdt%3A%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fdirect%2F%3E%0APREFIX%20wd%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fentity%2F%3E%0A%0ASELECT%20%3Fsection%20%3FsectionLabel%20WHERE%20%7B%0A%20%20%3Fsection%20wdt%3AP1%20wd%3AQ18%20.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22.%20%7D%0A%7D%0A) or [edit](https://kg-ipclimatec-reports.wikibase.cloud/query/#PREFIX%20wdt%3A%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fdirect%2F%3E%0APREFIX%20wd%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fentity%2F%3E%0A%0ASELECT%20%3Fsection%20%3FsectionLabel%20WHERE%20%7B%0A%20%20%3Fsection%20wdt%3AP1%20wd%3AQ18%20.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22.%20%7D%0A%7D%0A)


### Output
<table>
  <tr>
    <td><b>section</b></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q19">WGII SPM B.1.1</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q20">WGII SPM B.1.2</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q21">WGII Figure SPM.2.A</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q22">WGII TS.B.1</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q23">SRCCL SPM A.1.5</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q24">SRCCL SPM A.2</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q25">SRCCL SPM A.2.6</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q26">SRCCL Figure SPM.1</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q27">SROCC SPM A.6.1</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q28">SROCC SPM A.6.4</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q29">SROCC SPM A.7</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q30">2.1.2 Observed Climate System Changes and Impacts to Date</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q31">paragraph 2.1.2.c</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q49">paragraph 2.1.2.d</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q52">WGII SPM B.1.3</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q53">WGII SPM.B.2.3</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q54">WGII Figure SPM.2</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q55">WGII TS B.2.3</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q56">WGII TS Figure TS. 6</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q57">SRCCL SPM A.2.8</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q58">SRCCL SPM A.5.3</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q59">SROCC SPM A.5.4.</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q60">SROCC SPM A.7.1</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q61">SROCC SPM A.8.1</a></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q62">SROCC Figure SPM.2</a></td>
  </tr>
</table>
## Code examples
### curl
```shell
curl -s https://raw.githubusercontent.com/egonw/IPCC-Queries/master/sparql/allSections.rq \
  | sed 's+<lang/>+en+' > allSections.rq

curl -H "Accept: text/tab-separated-values" \
  -G https://kg-ipclimatec-reports.wikibase.cloud/query/sparql \
  --data-urlencode query@allSections.rq
```
This SPARQL query is available under CCZero.

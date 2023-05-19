# dpsir.rq
**Code examples:** [curl](#curl)
### SPARQL
```sparql
PREFIX wdt: <https://kg-ipclimatec-reports.wikibase.cloud/prop/direct/>
PREFIX wd:  <https://kg-ipclimatec-reports.wikibase.cloud/entity/>
PREFIX p:   <https://kg-ipclimatec-reports.wikibase.cloud/prop/>
PREFIX pq:  <https://kg-ipclimatec-reports.wikibase.cloud/prop/qualifier/>

SELECT DISTINCT ?driver ?driverLabel ?pressure ?pressureLabel ?state ?stateLabel ?impact ?impactLabel ?response ?responseLabel WITH {
  SELECT DISTINCT ?driver ?pressure ?state ?impact ?response WHERE {
    ?fact ^p:P3 / wdt:P1 wd:Q18 .
    OPTIONAL { ?fact pq:P18 ?driver ; pq:P19 ?pressure }
    OPTIONAL { ?fact pq:P19 ?pressure ; pq:P20 ?state }
    OPTIONAL { ?fact pq:P20 ?state ; pq:P10 ?impact }
    OPTIONAL { ?fact pq:P10 ?impact ; pq:P21 ?response }
  }
} AS %PARAGRAPHS WHERE {
  INCLUDE %PARAGRAPHS
  BIND (COALESCE(?driver, ?pressure, ?state, ?impact, ?response) AS ?someDPSIR)
  FILTER (BOUND(?someDPSIR))
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
}
```
[run](https://kg-ipclimatec-reports.wikibase.cloud/query/embed.html#PREFIX%20wdt%3A%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fdirect%2F%3E%0APREFIX%20wd%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fentity%2F%3E%0APREFIX%20p%3A%20%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2F%3E%0APREFIX%20pq%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fqualifier%2F%3E%0A%0ASELECT%20DISTINCT%20%3Fdriver%20%3FdriverLabel%20%3Fpressure%20%3FpressureLabel%20%3Fstate%20%3FstateLabel%20%3Fimpact%20%3FimpactLabel%20%3Fresponse%20%3FresponseLabel%20WITH%20%7B%0A%20%20SELECT%20DISTINCT%20%3Fdriver%20%3Fpressure%20%3Fstate%20%3Fimpact%20%3Fresponse%20WHERE%20%7B%0A%20%20%20%20%3Ffact%20%5Ep%3AP3%20%2F%20wdt%3AP1%20wd%3AQ18%20.%0A%20%20%20%20OPTIONAL%20%7B%20%3Ffact%20pq%3AP18%20%3Fdriver%20%3B%20pq%3AP19%20%3Fpressure%20%7D%0A%20%20%20%20OPTIONAL%20%7B%20%3Ffact%20pq%3AP19%20%3Fpressure%20%3B%20pq%3AP20%20%3Fstate%20%7D%0A%20%20%20%20OPTIONAL%20%7B%20%3Ffact%20pq%3AP20%20%3Fstate%20%3B%20pq%3AP10%20%3Fimpact%20%7D%0A%20%20%20%20OPTIONAL%20%7B%20%3Ffact%20pq%3AP10%20%3Fimpact%20%3B%20pq%3AP21%20%3Fresponse%20%7D%0A%20%20%7D%0A%7D%20AS%20%25PARAGRAPHS%20WHERE%20%7B%0A%20%20INCLUDE%20%25PARAGRAPHS%0A%20%20BIND%20%28COALESCE%28%3Fdriver%2C%20%3Fpressure%2C%20%3Fstate%2C%20%3Fimpact%2C%20%3Fresponse%29%20AS%20%3FsomeDPSIR%29%0A%20%20FILTER%20%28BOUND%28%3FsomeDPSIR%29%29%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22.%20%7D%0A%7D%0A) or [edit](https://kg-ipclimatec-reports.wikibase.cloud/query/#PREFIX%20wdt%3A%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fdirect%2F%3E%0APREFIX%20wd%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fentity%2F%3E%0APREFIX%20p%3A%20%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2F%3E%0APREFIX%20pq%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fqualifier%2F%3E%0A%0ASELECT%20DISTINCT%20%3Fdriver%20%3FdriverLabel%20%3Fpressure%20%3FpressureLabel%20%3Fstate%20%3FstateLabel%20%3Fimpact%20%3FimpactLabel%20%3Fresponse%20%3FresponseLabel%20WITH%20%7B%0A%20%20SELECT%20DISTINCT%20%3Fdriver%20%3Fpressure%20%3Fstate%20%3Fimpact%20%3Fresponse%20WHERE%20%7B%0A%20%20%20%20%3Ffact%20%5Ep%3AP3%20%2F%20wdt%3AP1%20wd%3AQ18%20.%0A%20%20%20%20OPTIONAL%20%7B%20%3Ffact%20pq%3AP18%20%3Fdriver%20%3B%20pq%3AP19%20%3Fpressure%20%7D%0A%20%20%20%20OPTIONAL%20%7B%20%3Ffact%20pq%3AP19%20%3Fpressure%20%3B%20pq%3AP20%20%3Fstate%20%7D%0A%20%20%20%20OPTIONAL%20%7B%20%3Ffact%20pq%3AP20%20%3Fstate%20%3B%20pq%3AP10%20%3Fimpact%20%7D%0A%20%20%20%20OPTIONAL%20%7B%20%3Ffact%20pq%3AP10%20%3Fimpact%20%3B%20pq%3AP21%20%3Fresponse%20%7D%0A%20%20%7D%0A%7D%20AS%20%25PARAGRAPHS%20WHERE%20%7B%0A%20%20INCLUDE%20%25PARAGRAPHS%0A%20%20BIND%20%28COALESCE%28%3Fdriver%2C%20%3Fpressure%2C%20%3Fstate%2C%20%3Fimpact%2C%20%3Fresponse%29%20AS%20%3FsomeDPSIR%29%0A%20%20FILTER%20%28BOUND%28%3FsomeDPSIR%29%29%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22.%20%7D%0A%7D%0A)


### Output
<table>
  <tr>
    <td><b>driver</b></td>
    <td><b>pressure</b></td>
    <td><b>state</b></td>
    <td><b>impact</b></td>
    <td><b>response</b></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q279">volcanic</a></td>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q281">aerosol emissions</a></td>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q294">global surface temperature</a></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q279">volcanic</a></td>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q290">greenhouse gas emission</a></td>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q294">global surface temperature</a></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q280">solar</a></td>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q281">aerosol emissions</a></td>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q294">global surface temperature</a></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q280">solar</a></td>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q290">greenhouse gas emission</a></td>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q294">global surface temperature</a></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q291">human activities</a></td>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q281">aerosol emissions</a></td>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q294">global surface temperature</a></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q291">human activities</a></td>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q290">greenhouse gas emission</a></td>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q293">concentrations of well-mixed GHG</a></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q291">human activities</a></td>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q290">greenhouse gas emission</a></td>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q294">global surface temperature</a></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q291">human activities</a></td>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q296">CO₂ emission</a></td>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q294">global surface temperature</a></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q291">human activities</a></td>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q297">methane emission</a></td>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q294">global surface temperature</a></td>
    <td></td>
    <td></td>
  </tr>
</table>
## Code examples
### curl
```shell
curl -s https://raw.githubusercontent.com/egonw/IPCC-Queries/master/sparql/dpsir.rq \
  | sed 's+<lang/>+en+' > dpsir.rq

curl -H "Accept: text/tab-separated-values" \
  -G https://kg-ipclimatec-reports.wikibase.cloud/query/sparql \
  --data-urlencode query@dpsir.rq
```
This SPARQL query is available under CCZero.

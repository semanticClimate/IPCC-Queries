# statementsWithConfidence.rq
**Code examples:** [curl](#curl)
### SPARQL
```sparql
PREFIX wdt: <https://kg-ipclimatec-reports.wikibase.cloud/prop/direct/>
PREFIX wd:  <https://kg-ipclimatec-reports.wikibase.cloud/entity/>
PREFIX p:   <https://kg-ipclimatec-reports.wikibase.cloud/prop/>
PREFIX pq:  <https://kg-ipclimatec-reports.wikibase.cloud/prop/qualifier/>
PREFIX ps:  <https://kg-ipclimatec-reports.wikibase.cloud/prop/statement/>

SELECT DISTINCT ?fact ?factLabel (GROUP_CONCAT(?value_string; separator=", ") as ?confidences) WHERE {
  VALUES ?section { wd:Q49 }
  ?section p:P3 ?factStatement .
  BIND (?section AS ?fact)
  ?factStatement ps:P3 ?factLabel .
  ?factStatement pq:P5 ?confidence .
  ?confidence rdfs:label ?value_string . 
  FILTER (LANG(?value_string) = 'en')
} GROUP BY ?fact ?factLabel
```
[run](https://kg-ipclimatec-reports.wikibase.cloud/query/embed.html#PREFIX%20wdt%3A%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fdirect%2F%3E%0APREFIX%20wd%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fentity%2F%3E%0APREFIX%20p%3A%20%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2F%3E%0APREFIX%20pq%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fqualifier%2F%3E%0APREFIX%20ps%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fstatement%2F%3E%0A%0ASELECT%20DISTINCT%20%3Ffact%20%3FfactLabel%20%28GROUP_CONCAT%28%3Fvalue_string%3B%20separator%3D%22%2C%20%22%29%20as%20%3Fconfidences%29%20WHERE%20%7B%0A%20%20VALUES%20%3Fsection%20%7B%20wd%3AQ49%20%7D%0A%20%20%3Fsection%20p%3AP3%20%3FfactStatement%20.%0A%20%20BIND%20%28%3Fsection%20AS%20%3Ffact%29%0A%20%20%3FfactStatement%20ps%3AP3%20%3FfactLabel%20.%0A%20%20%3FfactStatement%20pq%3AP5%20%3Fconfidence%20.%0A%20%20%3Fconfidence%20rdfs%3Alabel%20%3Fvalue_string%20.%20%0A%20%20FILTER%20%28LANG%28%3Fvalue_string%29%20%3D%20%27en%27%29%0A%7D%20GROUP%20BY%20%3Ffact%20%3FfactLabel%0A) or [edit](https://kg-ipclimatec-reports.wikibase.cloud/query/#PREFIX%20wdt%3A%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fdirect%2F%3E%0APREFIX%20wd%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fentity%2F%3E%0APREFIX%20p%3A%20%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2F%3E%0APREFIX%20pq%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fqualifier%2F%3E%0APREFIX%20ps%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fstatement%2F%3E%0A%0ASELECT%20DISTINCT%20%3Ffact%20%3FfactLabel%20%28GROUP_CONCAT%28%3Fvalue_string%3B%20separator%3D%22%2C%20%22%29%20as%20%3Fconfidences%29%20WHERE%20%7B%0A%20%20VALUES%20%3Fsection%20%7B%20wd%3AQ49%20%7D%0A%20%20%3Fsection%20p%3AP3%20%3FfactStatement%20.%0A%20%20BIND%20%28%3Fsection%20AS%20%3Ffact%29%0A%20%20%3FfactStatement%20ps%3AP3%20%3FfactLabel%20.%0A%20%20%3FfactStatement%20pq%3AP5%20%3Fconfidence%20.%0A%20%20%3Fconfidence%20rdfs%3Alabel%20%3Fvalue_string%20.%20%0A%20%20FILTER%20%28LANG%28%3Fvalue_string%29%20%3D%20%27en%27%29%0A%7D%20GROUP%20BY%20%3Ffact%20%3FfactLabel%0A)


### Output
<table>
  <tr>
    <td><b>fact</b></td>
    <td><b>confidences</b></td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q49">Although overall agricultural productivity has increased, climate change has slowed this growth in agricultural productivity over the past 50 years globally (medium confidence), with related negative crop yield impacts mainly recorded in mid- and low latitude regions, and some positive impacts in some high latitude regions (high confidence).</a></td>
    <td>high confidence, medium confidence</td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q49">Climate change has reduced food security and affected water security due to warming, changing precipitation patterns, reduction and loss of cryospheric elements, and greater frequency and intensity of climatic extremes, thereby hindering efforts to meet Sustainable Development Goals (high confidence).</a></td>
    <td>high confidence</td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q49">Ocean warming in the 20th century and beyond has contributed to an overall decrease in maximum catch potential (medium confidence), compounding the impacts from overfishing for some fish stocks (high confidence).</a></td>
    <td>high confidence, medium confidence</td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q49">Ocean warming and ocean acidification have adversely affected food production from shellfish aquaculture and fisheries in some oceanic regions (high confidence).</a></td>
    <td>high confidence</td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q49">Roughly half of the world’s population currently experiences severe water scarcity for at least some part of the year due to a combination of climatic and non-climatic drivers (medium confidence) (Figure 2.3).</a></td>
    <td>medium confidence</td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q49">Unsustainable agricultural expansion, driven in part by unbalanced diets, increases ecosystem and human vulnerability and leads to competition for land and/or water resources (high confidence).</a></td>
    <td>high confidence</td>
  </tr>
  <tr>
    <td><a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q49">Increasing weather and climate extreme events have exposed millions of people to acute food insecurity and reduced water security, with the largest impacts observed in many locations and/or communities in Africa, Asia, Central and South America, LDCs, Small Islands and the Arctic, and for small-scale food producers, low-income households and Indigenous Peoples globally (high confidence).</a></td>
    <td>high confidence</td>
  </tr>
</table>
## Code examples
### curl
```shell
curl -s https://raw.githubusercontent.com/egonw/IPCC-Queries/master/sparql/statementsWithConfidence.rq \
  | sed 's+<lang/>+en+' > statementsWithConfidence.rq

curl -H "Accept: text/tab-separated-values" \
  -G https://kg-ipclimatec-reports.wikibase.cloud/query/sparql \
  --data-urlencode query@statementsWithConfidence.rq
```
This SPARQL query is available under CCZero.

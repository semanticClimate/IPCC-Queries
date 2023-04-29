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
[run](https://kg-ipclimatec-reports.wikibase.cloud/query/embed.html#%23defaultView%3AMap%0APREFIX%20wdt%3A%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fdirect%2F%3E%0APREFIX%20wd%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fentity%2F%3E%0APREFIX%20p%3A%20%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2F%3E%0APREFIX%20pq%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fqualifier%2F%3E%0APREFIX%20ps%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fstatement%2F%3E%0APREFIX%20psv%3A%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fstatement%2Fvalue%2F%3E%0A%0APREFIX%20rwdt%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fprop%2Fdirect%2F%3E%0A%0ASELECT%20%3Fparagraph%20%3FparagraphLabel%20%3FconfidenceLabel%20%3Ftext%20%3Fcoordinates%20WHERE%20%7B%0A%20%20%3Fparagraph%20p%3AP3%20%3Fstatement%20.%0A%20%20%3Fstatement%20pq%3AP9%20%3FspecialScope%20%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20pq%3AP5%20%3Fconfidence%20%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20ps%3AP3%20%3Ftext%20.%0A%20%20%3FspecialScope%20wdt%3AP2%20%3Fwikidata%20.%0A%20%20SERVICE%20%3Chttps%3A%2F%2Fquery.wikidata.org%2Fsparql%3E%20%7B%0A%20%20%20%20%3Fwikidata%20rwdt%3AP625%20%3Fcoordinates%20.%0A%20%20%7D%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22.%20%7D%0A%7D%0A) or [edit](https://kg-ipclimatec-reports.wikibase.cloud/query/#%23defaultView%3AMap%0APREFIX%20wdt%3A%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fdirect%2F%3E%0APREFIX%20wd%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fentity%2F%3E%0APREFIX%20p%3A%20%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2F%3E%0APREFIX%20pq%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fqualifier%2F%3E%0APREFIX%20ps%3A%20%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fstatement%2F%3E%0APREFIX%20psv%3A%20%3Chttps%3A%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fprop%2Fstatement%2Fvalue%2F%3E%0A%0APREFIX%20rwdt%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fprop%2Fdirect%2F%3E%0A%0ASELECT%20%3Fparagraph%20%3FparagraphLabel%20%3FconfidenceLabel%20%3Ftext%20%3Fcoordinates%20WHERE%20%7B%0A%20%20%3Fparagraph%20p%3AP3%20%3Fstatement%20.%0A%20%20%3Fstatement%20pq%3AP9%20%3FspecialScope%20%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20pq%3AP5%20%3Fconfidence%20%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20ps%3AP3%20%3Ftext%20.%0A%20%20%3FspecialScope%20wdt%3AP2%20%3Fwikidata%20.%0A%20%20SERVICE%20%3Chttps%3A%2F%2Fquery.wikidata.org%2Fsparql%3E%20%7B%0A%20%20%20%20%3Fwikidata%20rwdt%3AP625%20%3Fcoordinates%20.%0A%20%20%7D%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22.%20%7D%0A%7D%0A)


### Output
<table>
  <tr>
    <td><b>paragraph</b></td>
    <td><b>text</b></td>
    <td><b>coordinates</b></td>
  </tr>
  <tr>
    <td><a href="https://scholia.toolforge.org/ikibase.cloud/entity/Q49">paragraph 2.1.2.d</a> (<a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q49">edit</a>)</td>
    <td>Increasing weather and climate extreme events have exposed millions of people to acute food insecurity and reduced water security, with the largest impacts observed in many locations and/or communities in Africa, Asia, Central and South America, LDCs, Small Islands and the Arctic, and for small-scale food producers, low-income households and Indigenous Peoples globally (high confidence).</td>
    <td>Point(7.1881 21.09375)</td>
  </tr>
  <tr>
    <td><a href="https://scholia.toolforge.org/ikibase.cloud/entity/Q49">paragraph 2.1.2.d</a> (<a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q49">edit</a>)</td>
    <td>Increasing weather and climate extreme events have exposed millions of people to acute food insecurity and reduced water security, with the largest impacts observed in many locations and/or communities in Africa, Asia, Central and South America, LDCs, Small Islands and the Arctic, and for small-scale food producers, low-income households and Indigenous Peoples globally (high confidence).</td>
    <td>Point(-59.0 -21.0)</td>
  </tr>
  <tr>
    <td><a href="https://scholia.toolforge.org/ikibase.cloud/entity/Q49">paragraph 2.1.2.d</a> (<a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q49">edit</a>)</td>
    <td>Increasing weather and climate extreme events have exposed millions of people to acute food insecurity and reduced water security, with the largest impacts observed in many locations and/or communities in Africa, Asia, Central and South America, LDCs, Small Islands and the Arctic, and for small-scale food producers, low-income households and Indigenous Peoples globally (high confidence).</td>
    <td>Point(87.331111111 43.681111111)</td>
  </tr>
  <tr>
    <td><a href="https://scholia.toolforge.org/ikibase.cloud/entity/Q49">paragraph 2.1.2.d</a> (<a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q49">edit</a>)</td>
    <td>Increasing weather and climate extreme events have exposed millions of people to acute food insecurity and reduced water security, with the largest impacts observed in many locations and/or communities in Africa, Asia, Central and South America, LDCs, Small Islands and the Arctic, and for small-scale food producers, low-income households and Indigenous Peoples globally (high confidence).</td>
    <td>Point(0.0 89.9997)</td>
  </tr>
  <tr>
    <td><a href="https://scholia.toolforge.org/ikibase.cloud/entity/Q31">paragraph 2.1.2.c</a> (<a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q31">edit</a>)</td>
    <td>Impacts on some ecosystems are approaching irreversibility such as the impacts of hydrological changes resulting from the retreat of glaciers, or the changes in some [..] Arctic ecosystems driven by permafrost thaw.</td>
    <td>Point(0.0 89.9997)</td>
  </tr>
  <tr>
    <td><a href="https://scholia.toolforge.org/ikibase.cloud/entity/Q49">paragraph 2.1.2.d</a> (<a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q49">edit</a>)</td>
    <td>Increasing weather and climate extreme events have exposed millions of people to acute food insecurity and reduced water security, with the largest impacts observed in many locations and/or communities in Africa, Asia, Central and South America, LDCs, Small Islands and the Arctic, and for small-scale food producers, low-income households and Indigenous Peoples globally (high confidence).</td>
    <td>Point(0.0 89.9997)</td>
  </tr>
  <tr>
    <td><a href="https://scholia.toolforge.org/ikibase.cloud/entity/Q31">paragraph 2.1.2.c</a> (<a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q31">edit</a>)</td>
    <td>Impacts on some ecosystems are approaching irreversibility such as the impacts of hydrological changes resulting from the retreat of glaciers, or the changes in some [..] Arctic ecosystems driven by permafrost thaw.</td>
    <td>Point(0.0 89.9997)</td>
  </tr>
  <tr>
    <td><a href="https://scholia.toolforge.org/ikibase.cloud/entity/Q49">paragraph 2.1.2.d</a> (<a href="https://kg-ipclimatec-reports.wikibase.cloud/entity/Q49">edit</a>)</td>
    <td>Increasing weather and climate extreme events have exposed millions of people to acute food insecurity and reduced water security, with the largest impacts observed in many locations and/or communities in Africa, Asia, Central and South America, LDCs, Small Islands and the Arctic, and for small-scale food producers, low-income households and Indigenous Peoples globally (high confidence).</td>
    <td>Point(-86.0 12.0)</td>
  </tr>
</table>
## Code examples
### curl
```shell
curl -s https://raw.githubusercontent.com/egonw/IPCC-Queries/master/sparql/statementOnMap.rq | sed 's+<lang/>+en+' > statementOnMap.rq

curl -H "Accept: text/tab-separated-values" -G https://https://kg-ipclimatec-reports.wikibase.cloud/bigdata/namespace/wdq/sparql --data-urlencode query@statementOnMap.rq
```
This SPARQL query is available under CCZero.

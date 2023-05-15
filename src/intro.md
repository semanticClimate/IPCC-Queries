# Introduction

This book takes advantage of the semantic representation of the AR6 Synthesis Report
[<cite>Q117820486</cite>], part of the IPCC Sixth Assessment Report [<cite>Q103843442</cite>].
The wraps around a Wikibase at [kg-ipclimatec-reports.wikibase.cloud](https://kg-ipclimatec-reports.wikibase.cloud/).

## Confidence levels

The report links statements to <topic>confidence levels</topic>. These are, along with the number of
statements with that level:

<sparql>confidenceLevels</sparql>

With gives:

<out>confidenceLevels</out>

## Data model

This knowledge graph has a number of types used to semantically model the data.

### Sections and Statements

The AR6 Synthesis report is organized as a collections of [sections](https://kg-ipclimatec-reports.wikibase.cloud/wiki/Item:Q18) that consist of one or
more paragraphs, where each paragraphs cites other parts of the IPCC reports. Each
paragraph consists of statements, each with a confidence level (see above). This is explained more
in the [next section](section.md).

This model is captured in the shape expression [E1](https://kg-ipclimatec-reports.wikibase.cloud/wiki/EntitySchema:E1) (see [<cite>Q105037759</cite>]):

```
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>

PREFIX p: <http://www.wikidata.org/prop/>
PREFIX pq: <http://www.wikidata.org/prop/qualifier/>
PREFIX wd:  <https://kg-ipclimatec-reports.wikibase.cloud/entity/>
PREFIX wdt: <https://kg-ipclimatec-reports.wikibase.cloud/prop/direct/>

# SELECT ?section WHERE { ?section wdt:P1 wd:Q18 . }

# Run with: https://shex-simple.toolforge.org/wikidata/packages/shex-webapp/doc/shex-simple.html?data=Endpoint:%20https://kg-ipclimatec-reports.wikibase.cloud/sparql&hideData&manifest=[]&textMapIsSparqlQuery&schemaURL=%2F%2Fkg-ipclimatec-reports.wikibase.cloud%2Fwiki%2FSpecial%3AEntitySchemaText%2FE1

START = @<Section>

<Section> {
  wdt:P1 [ wd:Q18 ] ; # instance of
  wdt:P4 . * ; # part of
  wdt:P11 @<Section> * ; # cites
  p:P3 @<Statement> * # has the statement
}

<Statement> {
  pq:P1 . ? ; # instance of
  pq:P5 @<Confidence> ? ; # confidence
  pq:P8 xsd:integer ? ; # series ordinal
  pq:P9 @<SpacialScope> ? # spacial scope
}

<Confidence> {
  wdt:P1 [ wd:Q1 ] # instance of 'confidence'
}

<SpacialScope> {
  wdt:P1 [ wd:Q32 ] ; # instance of 'ecosystem'
  wdt:P2 IRI ? # same as
}
```

## References

<references/>

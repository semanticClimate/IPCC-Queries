# Introduction

This book takes advantage of the semantic representation of the AR6 Synthesis Report
[<cite>Q117820486</cite>], part of the IPCC Sixth Assessment Report [<cite>Q103843442</cite>].
The wraps around a Wikibase at [kg-ipclimatec-reports.wikibase.cloud](https://kg-ipclimatec-reports.wikibase.cloud/).

## Confidence levels

The report links statements to confidence levels. These are, along with the number of
statements with that level:

<sparql>confidenceLevels</sparql>

With gives:

<out>confidenceLevels</out>

## Putting statements on the map

With the following SPARQL query we can show statements on the world map, if they
mention regions and have been annotated accordingly, of course:

<sparql>statementOnMap</sparql>

This should show something like this (pending a solution for a `'X-Frame-Options' to 'sameorigin'` problem:

<iframe>statementOnMap</iframe>

For now, this is what the results look like as table:

<out>statementOnMap</out>

## References

<references/>

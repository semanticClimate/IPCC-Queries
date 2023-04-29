# Statement Annotations

Statements are annotated with their confidence level, but more interesting is their annotation
with other topics. This section shows how statements can be annotated.

## Regional annotation

Statements can be annotated with the region they are about. We can the list all such regions
and the number of statements about that region:

<sparql>regions</sparql>

With gives:

<out>regions</out>

### Putting statements on the map

With the following SPARQL query we can show statements on the world map,
taking advantage of Wikidata [<cite>Q27042516</cite>] to provide geographical coordinates for regions,
using a <topic>federated SPARQL query</topic>:

<sparql>statementOnMap</sparql>

This should show something like this (pending a solution for a `'X-Frame-Options' to 'sameorigin'` problem:

<iframe>statementOnMap</iframe>

For now, this is what the results look like as table:

<out>statementOnMap</out>


## References

<references/>

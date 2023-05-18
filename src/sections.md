# Sections, Paragraphs and Statements

The <topic>AR6 Syntheses Report</topic> consists of many sections, each of which has one or more
<topic>paragraphs</topic> [<cite>Q117820486</cite>]. Each paragraph, in turn, contains one or more <topic>facts</topic>.

## Sections

We can list all the <topic>sections</topic> in the book:

<sparql>allSections</sparql>

Which gives:

<out limit="5">allSections</out>

Instead, we can also focus on paragraphs (also typed as section):

<sparql>sectionsWithStatements</sparql>

Which gives:

<out>sectionsWithStatements</out>

## Paragraphs

For each section we can list the paragraphs and their <topic>confidence levels</topic>,
for example for paragraph <i>paragraph 2.1.2.d</i> ([Q49](https://kg-ipclimatec-reports.wikibase.cloud/wiki/Item:Q49)):

<sparql>statementsWithConfidence</sparql>

Which gives for this paragraph:

<out>statementsWithConfidence</out>

## References

<references/>

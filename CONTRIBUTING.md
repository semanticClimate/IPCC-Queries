Everyone is invited to contribute to this ebook. It is written in Markdown, and
the Markdown sources are the `.md` files in the `src/` folder. The `docs/` folder is output
and should not be manually edited. All the SPARQL queries are found in the `sparql/`
folder. They are included in an `.md` file with the following command (on an
otherwise empty line):

```xml
<sparql>someQuery</sparql>
```

The build script will look for the file `someQuery.rq` in the `sparql/` folder.

The output is added with a similar command:

```xml
<out>someQuery</out>
```

If you want to cite an article, make sure the article is found in Wikidata and
include the following code in the `.md` file: `<cite>Qxxxx</cite>`.

## Adding a new query

Additional content can be contributed with a pull request. The Markdown content
is assumed to have a CC-BY-SA license, while the SPARQL query (-ies) must have
the CCZero license/waiver.

 * step 1: write the SPARQL query and create a `.rq` file in the `sparql/` folder
 * step 2: edit the `.md` file where the query should be added and add some written explanation
 * step 3: (Linux) run `cd sparql/; make`
 * step 4: (Linux) run `make` (so, in the root folder)

If that works, add the files like this:

 * step 5: (Linux) run `git add -f sparql/someQuery.rq` (the `-f` is important)
 * step 6: (Linux) run `git add docs/sparql/someQuery.code.md`
 * step 7: (Linux) run `git add -u`
 * step 7: (Linux) run `git commit -m "Added a query to do some lookup"`

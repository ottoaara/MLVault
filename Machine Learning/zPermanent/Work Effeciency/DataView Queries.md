---
"tags: dataview": obsidian
---

4 types

LIST 

```dataview
LIST 
FROM ""

```


Table


```dataview
Table file.ctime, tags
FROM ""
```


#Dataview


```dataview
calendar file.mtime 
from ""
```


[[Obsidian Introduction]]
[[Mermaid syntax- Lets you build diagrams in Obsidian]]
[[DataView Queries]]

How to use Data View
==[DATA COMMANDS](https://blacksmithgu.github.io/obsidian-dataview/queries/data-commands/)==

Dataview Docs (https://blacksmithgu.github.io/obsidian-dataview/)

Dataview Query Langauge  (https://blacksmithgu.github.io/obsidian-dataview/queries/structure/)

```dataview <QUERY-TYPE> <fields> 
FROM <source> 
<DATA-COMMAND> <expression> 
<DATA-COMMAND> <expression> ...

## Choose a Output Format

The output format of a query is determined by its **Query Type**. There are four available:

1. **TABLE**: A table of results with one row per result and one or many columns of field data.
2. **LIST**: A bullet point list of pages which match the query. You can output one field for each page alongside their file links.
3. **TASK**: An interactive task list of tasks that match the given query.
4. **CALENDAR**: A calendar view displaying each hit via a dot on its referred date.

The Query Type is the **only mandatory command in a query**. Everything else is optional.

## Choose your source

Additionally to the Query Types, you have several **Data Commands** available that help you restrict, refine, sort or group your query. One of these query commands is the **FROM** statement. `FROM`takes a [source](https://blacksmithgu.github.io/obsidian-dataview/reference/sources) or a combination of [sources](https://blacksmithgu.github.io/obsidian-dataview/reference/sources) as an argument and restricts the query to a set of pages that match your source.

It behaves differently from the other Data Commands: You can add **zero or one** `FROM` data command to your query, right after your Query Type. You cannot add multiple FROM statements and you cannot add it after other Data Commands.

` Lists all pages inside the folder Books and its sub folders ```dataview LIST FROM "Books" ```  Lists all pages that include the tag #status/open or #status/wip ```dataview LIST FROM #status/open OR #status/wip ```  Lists all pages that have either the tag #assignment and are inside folder "30 School" (or its sub folders), or are inside folder "30 School/32 Homeworks" and are linked on the page School Dashboard Current To Dos ```dataview LIST FROM (#assignment AND "30 School") OR ("30 School/32 Homeworks" AND outgoing([[School Dashboard Current To Dos]])) ``` `

## Filter, sort, group or limit results

In addition to the Query Types and the **Data command** `FROM` that's explained above, you have several other **Data Commands** available that help you restrict, refine, sort or group your query results. 

All data commands except the `FROM` command can be used **multiple times in any order** (as long as they come after the Query Type and `FROM`, if `FROM` is used at all). They'll be executed in the order they are written.

Available are:

1. **FROM** like explained [above](https://blacksmithgu.github.io/obsidian-dataview/queries/structure/#choose-your-source).
2. **WHERE**: Filter notes based on information **inside** notes, the meta data fields.
3. **SORT**: Sorts your results depending on a field and a direction.
4. **GROUP BY**: Bundles up several results into one result row per group.
5. **LIMIT**: Limits the result count of your query to the given number.
6. **FLATTEN**: Splits up one result into multiple results based on a field or calculation.

`` Lists all pages that have a metadata field `due` and where `due` is before today ```dataview LIST WHERE due AND due < date(today) ```  Lists the 10 most recently created pages in your vault that have the tag #status/open ```dataview LIST FROM #status/open SORT file.ctime DESC LIMIT 10 ```  Lists the 10 oldest and incompleted tasks of your vault as an interactive task list, grouped by their containing file and sorted from oldest to newest file. ```dataview TASK WHERE !completed SORT created ASC LIMIT 10 GROUP BY file.link SORT rows.file.ctime ASC ``` ``

## Examples

Following are some example queries. Find more examples [here](https://blacksmithgu.github.io/obsidian-dataview/resources/examples/).

` ```dataview TASK ``` `

` ```dataview TABLE recipe-type AS "type", portions, length FROM #recipes ``` `

` ```dataview LIST FROM #assignments WHERE status = "open" ``` `

` ```dataview TABLE file.ctime, appointment.type, appointment.time, follow-ups FROM "30 Protocols/32 Management" WHERE follow-ups SORT appointment.time ``` `

` ```dataview TABLE L.text AS "My lists" FROM "dailys" FLATTEN file.lists AS L WHERE contains(L.author, "Surname") ``` `

` ```dataview LIST rows.c WHERE typeof(contacts) = "array" AND contains(contacts, [[Mr. L]]) SORT length(contacts) FLATTEN contacts as c SORT link(c).age ASC ``` `


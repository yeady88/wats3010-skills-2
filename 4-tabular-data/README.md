# Tabular Data  

## Table Tags NOT to be used for layout

We've used the CSS `display:table`, `display:row`, and `display:cell` so that we could use a table metaphor for layout because we like to think in terms of rows and columns for layout.  There is a set HTML tag that are used to create a table when we are displaying tabular data like numbers or data that you might see in a spreadsheet or database table.  The HTML `table`, `tr` (table row), `td` (table data), `th` are not meant to be used for layout. They are semantically intended for data.  

In this exercise we'll create a table for tabular data.  Tables are not responsive by nature.  Their size is dictated by their contents.  To make our table more repsonsive we'll put it  in a container that allows us to scroll horizontally.  We'll also set a height on our table, and set an overflow property so that we can scroll vertically.  

We'll also add features to the table to increase its accessbility: captions to the table and scope to the headers.

## Assignment  

1. Create an HTML File and build a table structure
```
table
  caption
  thead
    tr
      th...
  tbody
    tr, th, td...
```
2. The caption is **Flights from Amsterdam**
3. The `th` in the `thead` should be **To**, **Duration**, **Flight**, **Cost**, **Nonstop**.
4. Add data from `table-content.txt` file.  The data in the text file is in order and you should be able to wrap with `th` or `td`.
5. All header data in `thead` should use the `th` tag.  All city names in `tbody` should use the `th` tag. The rest of the data in `tbody` should use the `td` tag.
5. For the `th` in the `thead` provide a `scope="col"` attribute and for the `th` in `tbody` provide a `scope="row"` attribute.
6. Add a style sheet to the index.html
7. Set the table `border-collape:collapse` to remove gaps between rows and columns. Set the table width to 100%.
8. 


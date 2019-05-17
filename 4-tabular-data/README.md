# Tabular Data  

## Table Tags shoult NOT to be used for layout

We've used the CSS `display:table`, `display:row`, and `display:cell` so that we could use a table metaphor for layout because we like to think in terms of rows and columns for layout.  There is a set of HTML tags that are used to create a table when we are displaying tabular data like numbers or data that you might see in a spreadsheet or database table.  The HTML `table`, `tr` (table row), `td` (table data), `th` are not meant to be used for layout. They are semantically intended for data.  

In this exercise we'll create a table for tabular data.  Tables are not responsive by nature.  Their size is dictated by their contents.  To make our table more repsonsive we'll put it  in a container that allows us to scroll horizontally.  We'll also set a height on our table, and set an overflow property so that we can scroll vertically.  

We'll also add features to the table to increase its accessbility: captions to the table and scope to the headers.

## Assignment  

### HTML 

Create a an index.html file.

1. Start by creating a container for the table.  We'll make this container horizontally scrollable with CSS.
Place the following under the `body` tag.  All of the table tags will go inside this container.
```
<div class="container">
</div>
```
2.  Create an HTML File and build a table structure
```
table
  caption
  thead
    tr
      th...
  tbody
    tr, th, td...
```
The table structure with just the rows will be coded like this. There is a single row in the `thead`.  The code below shows a single row in the `tbody`.  There shouldl be a total of 7 rows in the body and only one is show below
```
 <table>
      <caption></caption>
      <thead>
        <tr>         
        </tr>
      </thead>
      <tbody>
        <tr>     
        </tr>
        <!-- make 7 rows for data in the tbody -->
      <tbody>
    </table>
  ```
3. The caption is **Flights from Amsterdam**
4. Add 5 `th` (header cells) in the `thead` The `th` data in the  `thead` should be **To**, **Duration**, **Flight**, **Cost**, **Nonstop**.  These are column headers.
```
<th>To</th>
<th>Duration</th>
<th>Flight</th>
<th>Cost</th>
<th>Nonstop</th>
```
5. Wrap the data below with `th` or `td`.  The first column should be wrapped in a table-header `th` tag and the rest in table-data `td` tags.  We are considering the City name to be a row header.  This is useful for accessibility as screen readers can pick up on these tag meanings.
```
  row 1
  New York City (NYC)
  8h 15m
  3456
  $300
  No

  row 2           
  Washington (WAS)
  8h 25m
  1111
  $500
  Yes

  row 3         
  New York City (NYC)
  8h 40m
  3343
  $600
  Yes

  row 4      
  Chicago (CHI)
  8h 45m
  7654
  $200
  No

  row 5     
  Miami (MIA)
  10h 20m
  5566
  $250
  No

  row 6     
  Los Angeles (LAX)
  11h
  7788
  $700
  Yes

  row 7
  Miami (MIA)
  11h 6m
  9988
  $150
  No
```
6. Add the `scope` attribute to all of the `th` tags. For the columns add `scope="col"` and for the rows ad `scope="row"`. The scope attribute helps to associate header and data cells.

### CSS 
1. Add a style sheet to the index.html
2. Tables are not responsive in themselves but we can make the table data accessible by providing a horizontal scroll bar. We create a horizontal scroll bar by setting a width on the container and setting the overflow in the X direction to auto. A little horizontal padding is applied.
```
.container {
      padding: 0px 5%;
      width: 70%;
      overflow-x:auto;
    }
```
3. Apply styles directly to the table tag.  If you had multiple tables on your page, you might want to give the table class names for specificity   
  - `border-collape:collapse` to remove gaps between rows and columns. Set the table width to 100%.
  - set `table-layout` to `fixed` to tell the browser to judge cell width based on header content. This can really improve rendering speed on large tables.
  - look and feel
    - background color should be `darkgray`
    - border should be a 3px, solid `lightgray` line
    - font family is `'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;`
    ```
    table {
      /* more control */
      border-collapse: collapse;
      table-layout: fixed; 
      background-color: darkgray; 
      border: 3px solid lightgray;
      font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    }
    ```
4. Styling the `caption`.  Apply the following styles to the caption tag directly.
  - 2% padding in all directions 
  - font style italic
  - place the caption at the top left by setting `caption-side` to `top` and `text-align` to `left`
  -  set color to `#667788`
  - set letter spacing to 1px for readability
  ```
 caption {
      padding: 2%;
      font-style: italic;
      caption-side: top;
      color: #678;
      text-align: left;
      /* letter-spacing: 1px; */
    }
  ```
5. Because we have a fixed size table we can set width dimensions on the `thead` elements and they will apply to the whole table.  We have 5 columns in the table so create 5 entries and set the width of each entry according to the following spec: col 1: 30%, col 2: 20%, col 3:10%, col 4:20%, col5: 20%.  The percentages should add up to 100%. We're using nth-child to select each header column or row by number. We're also left aligning the text in the first column.
```
  thead th:nth-child(1) {
      width: 30%;
      text-align:left;
  }

  thead th:nth-child(2) {
    width: 20%;
  }

  thead th:nth-child(3) {
    width: 10%;
  }

  thead th:nth-child(4) {
    width: 20%;
  }

  thead th:nth-child(5) {
    width: 20%;
  }
  tbody th:nth-child(1){
    text-align:left;
  }
```
6. Assign `text-align:center` to all `tbody td` to make all data in the body of the table centered. Make the col 1 text left aligned by adding the `text-align: left` to the thead `th:nth-child(1)` style shown above.
```
 tbody td {
    text-align: center;
 }
```
7. Provide data cell spacing by adding a padding of `20px` to all sides of the `th` and `td`.
```
  th, td {
      padding: 20px;
    }
```
8. Zebra stripe the rows by adding alternating colors for odd and even rows (shown below). We're using a pseudo selector to choose nth child based on even/odd.
```
tbody tr:nth-child(odd) {
  background-color: lightgray;
}

tbody tr:nth-child(even) {
  background-color: white;
}
``` 
### Test
Compare your table to the once shown in the image below.  Also test in the browser, using dev tools, to see if the table has a horizontal scroll at lower image sizes.

### Solution  

![Tabular Data](images/tabular-data.png)



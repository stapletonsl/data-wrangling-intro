# The Layout of OpenRefine, Rows vs Records

- *Teaching:* 15 minutes.
- *Exercises:* 10 minutes.

## Objectives

- Locate controls for navigating data in OpenRefine
- Find options to work with data through the OpenRefine dropdown menus

### Explore the layout of OpenRefine

OpenRefine displays data in a tabular format. Each row will usually represent a 'record' or 'observation' in the data, 
while each column represents a type of information or 'variable'. This is very similar to how you might view data 
in a spreadsheet or database. As with a spreadsheet, the individual bits of data or 'values' live in 'cells' at the intersection 
of a row and a column. OpenRefine displays only a limited number of rows of data at one time. Ten is the default.

However, the program is working on ALL rows - the limit of the number of rows displayed saves memory being wasted.

You can adjust the number of rows displayed by choosing between 5, 10, 25 and 50 at the top left of the table of data. 
You can navigate through the records by using the previous/next/first/last navigation options at the top right of the table of data.

### Working with data in OpenRefine

Most options to work with data in OpenRefine are accessed from drop-down menus at the top of the data columns. 
When you select an option in a particular column (e.g., to make a change to the data), it will affect all the 
cells in that column. If you want to make changes across several columns, you will need to do this one column at a time.


###  Rows and Records

OpenRefine has two modes of viewing data: 'Rows' and 'Records'. At the moment we are in Rows mode, 
where each row represents a single record in the data set - in this case, a respondent's survey answers. 
In Records mode, OpenRefine can link together multiple rows as belonging to the same Record. 
This is useful when working with `xml` files, MARC records, as well as `csv` files. We will see an example of this later.

### The sample dataset

We will be using open data from Transport & Main Roads obtained from the Queensland, Australia government's [open 
data portal](https://data.qld.gov.au). The original dataset presents 17 years of traffic accidents, their location, 
type of accident, level of injury, and other features, with over 300,000 observations.  

The data used in this lesson is a smaller four-year subset and has had changes made for training purposes.

### Saving projects

Projects are saved automatically as you work on them,  so there is no need to save copies as you go along. 
To open an existing project in OpenRefine, click **Open Project** from the main OpenRefine screen (in the left-hand menu). 
When you click this, you will see a list of the existing projects and can click on a project's name to open it.

[Go to the next part of the lesson](data-wrangling-intro-for-hass-4.md).

[Go to the previous part of the lesson](data-wrangling-intro-for-hass-2.md).

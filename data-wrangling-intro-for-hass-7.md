# Examining Numbers in OpenRefine

*Teaching:* 10 minutes.

*Exercises:* 15 minutes.

## Objectives

Let's explore what we can do with numbers.

When a table is imported into OpenRefine, all data is formatted as text. We saw earlier how we can sort column values as numbers, but this does not change the data type in a column from text to numbers. Rather, this interprets the values as numbers for the purposes of sorting but keeps the underlying data type as is.

We can, however, transform columns to other data types (e.g., number or date) using the `Edit cells > Common transforms` feature. Here we will experiment changing columns to numbers and see what additional capabilities that gives us.

Be sure to close any facets you have enabled from the left panel before this step, so that we can be sure we are working on the complete dataset. You can close an existing facet by clicking the `x` in the upper left of that facet window.

#### Activity 23

To transform cells in the `Crash_Hour` column to numbers:

- Click the down arrow for the `Crash_Hour` column

- Select `Edit cells > Common transforms ... ` and chose the option `number`

The `Crash_Hour` values change from left-justified to right-justified, and from black to green in colour.

#### Numeric facets

Sometimes there are non-numeric values or blanks within a column which may represent errors in data entry. We can find these by using a **numeric** facet.

#### Activity 24

- Go to the `Postcode` column which was transformed to numbers.

- Edit a few cells, replacing the numbers with text, such as "abc", and make a few other cells blank.

- Apply a numeric facet to the column you edited.

Notice that there are several checkboxes in this facet: 

- Numeric
- Non-numeric
- Blank
- Error 

Below these are counts of the number of cells in each category. You should see checks for *Non-numeric* and *Blank* if you changed or deleted some values.

Experiment with checking or unchecking these boxes to select subsets of your data.

When you have finished examining the numeric data, close this facet by clicking the `x` in the upper left corner of its panel.

Note that closing a facet will not undo the edits you have made to the cells in this column.

Use the `Undo / Redo` function to reverse these changes.

[<-- BACK](data-wrangling-intro-for-hass-6.md) | [NEXT -->](data-wrangling-intro-for-hass-8.md)

## Filtering and Sorting with OpenRefine

*Teaching:* 10 minutes.

*Exercises:* 10 minutes.

### Objectives

#### Work on a subset of data by filtering

There are many records in our dataset. We can filter them to work on a subset. In this exercise, we want to filter by a word within the text values of a column.

#### Activity 11: work on a subset of data by filtering

Click the down arrow next to `Suburb_PostCode > Text filter`. A filter box will appear in the left margin.

Type in heights and press return. There are 208 matching rows of the original 27528 rows (and these rows are selected for the subsequent steps).

#### Exercise: Limit the results to one of the suburbs with 'Heights' in the name.

Work with your neighbour to find out.

There are a couple of possibilities.

> #### Solution

> Do `Facet > Text facet` on the `Suburb_PostCode` column after filtering.

> This will show 20 suburbs with names that match your filter.

> To restrict to only one of these suburbs, select one to include.

Faceting and filtering look very similar. A good distinction is that faceting gives you an overview, description and count of all of the data that is currently selected, while filtering allows you to select a subset of your data by a string - of text in this case - for analysis or cleaning.

### Sorting data

Using `Crash_Street`, let's explore data together in another way, using sorting.

You can sort data in a column by selecting drop-down menu and `Sort`.  Options include

- sort by text
- sort by numbers
- sort by dates
- sort by booleans (TRUE or FALSE values). 

You can also specify what order to put Blanks and Errors in the sorted results.

If this is your first time sorting this table, then the drop-down menu for the selected column shows Sort ... Select what you would like to sort by (such as text). Additional options will then appear for you to fine-tune your sorting.

If you try to re-sort a column that you have already used, the drop-down menu changes slightly, to > Sort without the ..., to remind you that you have already used this column. It will give you additional options:

- Sort > Sort ... - This option enables you to modify your original sort.

- Sort > Reverse - This option allows you to reverse the order of the sort.

- Sort > Remove sort - This option allows you to undo your sort.

### Sorting by multiple columns

You can also sort by multiple columns and this makes it easier to explore data easily before analysis and processing.   We can sort by multiple columns by performing sort on additional columns.

The sort will depend on the order in which you select columns to sort.

To restart the sorting process with a specific column, check the sort by this column alone box in the Sort pop-up menu.

If you go back to one of the already sorted columns and select Sort > Remove sort, that column is removed from your multiple sort. If it is the only column sorted, then data reverts to its original order.

#### Activity 12: sorting by multiple columns

Sort `Crash_Street` again, select Sort... > text and a-z

Add an additional sort by `Crash_Street_Intersection`, select Sort... > text and a-z

Examine the first page of results for multiple accidents at the same location

Remove sort.

Sorts in OpenRefine are temporary. If you remove the Sort, the data will go back to its original unordered state.

The Sort drop-down menu at the top of the screen also lets you amend the existing sort (e.g. reverse the sort order), remove existing sorts, and/or make sorts permanent.

#### Activity 13

Sort the data by `Crash_Longitude` by number. What are the results?

> ---------
> Solution

> In the Crash_Longitude column, select Sort... > numbers and select smallest first and reposition Errors & Blanks to the top of the column.

> The first value is missing, from record 243929.

> ----------

### Find the missing value

We want to map this data later, so it is important to have complete latitude and longitude information.  We may be able to identify the missing value by other variable attributes.  When you know your data or look at the variable in context with other similar observations you can identify what type of data problem might be occurring and possible solutions.  In this case, we could search other variables such as Crash_Street , Crash_Street_Intersection and Suburb_PostCode to identify similar locations.

#### Exercise:  now that we know about sorting, filtering and faceting work with your neighbour to

Find the missing Crash_Longitude value for record 243929. There are a few possibilities.

*Hint:* my first step is to:

Write down the values in the columns Crash_Street , Crash_Street_Intersection and Suburb_PostCode, for record 243929

>------

> Solution

> Values are: Mary St; Miles St; Mount Isa City, (4825);


Remove the sort.

Filter `Crash_Street` by Mary.

Filter `Crash_Street_Intersection` by Miles St.

Examine results for similarities.

Copy and paste `Crash_Longitude` value to the record missing the value.

### Key Points

OpenRefine provides a way to sort and filter data without affecting or changing the raw data.

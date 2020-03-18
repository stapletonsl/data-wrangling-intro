# Transforming data using GREL (General Refine Expression Language)

*Teaching:* 15 minutes
*Exercises:8 15 minutes

## Objectives

Transformations in OpenRefine enable manipulations of data in columns. Such types of changes include:

- Splitting data from a single column into multiple columns (e.g., splitting an address into multiple parts) to enable tidy data – one variable per column.

- Standardising the format of data in a column without changing the values (e.g., removing punctuation or standardising a date format)

- Extracting data from a longer text string (e.g., finding DOIs within a bibliographic citation)

It can be difficult to read, ingest and process data which has multiple values within the one cell.  OpenRefine has methods to split those values into multiple cells or columns. OpenRefine has several ways to do this. 

First we will split data using the in-built programming capabilities of GREL within OpenRefine.  GREL stands for **General Refine Expression Language**. GREL expressions are a little like Excel formulae, although they tend to focus on text manipulations rather than numeric functions.

The data in the `Suburb_PostCode` column has more than one value in each cell. The values include the suburb name and a postcode inside brackets. This is difficult to process and analyse and needs splitting to make the data tidy. Before we can split the values into individual columns, we first need to remove the extra characters such as brackets and leading (or trailing) whitespace.

#### Activity 14: transforming data using GREL

We are going to remove all the extra characters by using the GREL command `value.replace`.

`Value.replace` is the command. What needs to be added to make it work are first *what* needs to be replaced, and then *what it needs to be replaced with*.

Click the down arrow at the top of the `Suburb_PostCode` column.

Select `Edit Cells > Transform ...`    This will open a window in which you can enter a GREL expression. An expression is a combination of the command you will being using, and the arguments you will be using to modify the command, i.e. the values that will be changed.

In the Expression box type value.replace("(", "")  to remove all left brackets “(“

Look at the Preview screen to see what is occurring

Click OK.

This expression means: In each cell in the selected column, replace all the values “(” with “” (i.e. nothing - delete).

















The Suburb_PostCode column should now contain no left parentheses.
Page Break
Activity 15: Remove another character

Use the strategy above to remove the right-hand bracket ()) from the Suburb_PostCode column.

 (write value.replace(“)“, “”) on white board, with different colours to illustrate)

Solution

 value.replace(")", "") to remove )

There is quick method to reuse GREL expressions, as OpenRefine provides a history of commands. You can select them and reuse as is or make changes. Let’s try this with the remainder of the extraneous characters in the Suburb_PostCode  column. We want only to have a separator left between our two values in each cell.  The comma is the separator in this variable.

Activity 16: Repeat transformation steps by using History

At Suburb_PostCode  column Edit cells > transform

click the History tab

click on the first Reuse option

click inside the expression box, change character “)”, to “(”,

preview and ok

repeat steps 1 to 3 above

click inside the expression box to change comma & space character“, “ to comma no space “,”

preview and ok

Question (prize)

Why did we need to include the comma in our GREL expression, rather than just remove the white space?

As there are spaces between multi word suburb names and these would have been affected if removing whitespace without the comma.

Now that we have cleaned out extraneous characters from our Suburb_PostCode column, we can  explore the data and see which postcodes were the most or least prominent traffic crash locations.

Splitting cells

Splitting multi-valued cells will enable faceting by text. This is also useful for splitting full names in first and last name columns and more.

Activity 17

Click down arrow at the top of the Suburb_PostCode column.

Choose Edit cells > Split multi-valued cells

At the separator Expression box check the correct separator is used

Click OK.

Note that the rows are still numbered sequentially and that there are now 55056 rows, which no longer reflects one row per accident record. These are compound data objects.

Click the Records option to change to Records mode and then go back to Rows.

Note how the numbering changes as you toggle – indicating that several rows are related to the same record. This method is useful for JSON and xml files which have compound data objects.

Can perform a text facet, but this is not the most efficient method.



Undo and Redo

It’s common while exploring and cleaning a dataset to discover after you’ve made a change that you really should have done something else first. OpenRefine provides Undo and Redo operations to make this easy.

Activity 18

Click where it says Undo / Redo on the left side of the screen. All the changes you have made so far are listed here.

Click on the previous step, to remove the split in the cell values of Suburb_PostCode  column

Visually confirm that the columns data is re-joined

Activity 19

Before moving on to the next lesson:

Undo

to the step before we first used GREL to remove all the extra characters in Suburb_PostCode

Go back to Facet/filter tab.

Joining up GREL expression commands

Let’s perform the earlier clean up steps and customized text faceting for Suburb_PostCode column. We can do this more efficiently by joining up the GREL expressions.

Activity 20

Select Suburb_PostCode column.  All three cleaning steps can be performed by combining .replace statements.

Edit cells > transform

In the Expression box type  value.replace("(", "").replace(")", "").replace(“, “, ",")

Preview, OK

Splitting multi value cells into multiple columns (tidy data)

Let’s split Suburb_PostCode  data into two columns for suburb and postcode

Activity 21

Select Suburb_PostCode column

Edit Column > Split into several columns….

Keep the Separator as a comma, Split into 2 columns,

keep the After Splitting boxes checked

OK

The original column has been replaced with two columns.

A column named Suburb_PostCode 1 contains the names of suburbs

A column named Suburb_PostCode 2 contains postcodes in green.  The change in colour denotes that OpenRefine has changed the underlying format of the data from “text” to “number”.

Let’s change the column headings to represent the data.

Activity 22

Go to Suburb_PostCode 1

Edit Column > Rename this column to Suburb

Repeat for Suburb_PostCode 2 and rename to Postcode
Page Break


Examining Numbers in OpenRefine

Teaching: ? min
Exercises: 0? min

Objectives



Let’s explore what we can do with numbers.

Numbers

When a table is imported into OpenRefine, all data is formatted as text. We saw earlier how we can sort column values as numbers, but this does not change the data type in a column from text to numbers. Rather, this interprets the values as numbers for the purposes of sorting but keeps the underlying data type as is.

We can, however, transform columns to other data types (e.g. number or date) using the Edit cells > Common transforms feature. Here we will experiment changing columns to numbers and see what additional capabilities that grants us.

Be sure to remove any facets you have enabled from the left panel so that we can examine our whole dataset. You can remove an existing facet by clicking the x in the upper left of that facet window.

Activity 23

To transform cells in Crash_Hour column to numbers:

Click the down arrow for that column

then Edit cells > Common transforms… > To number

The Crash_Hour values change from left-justified to right-justified, and black to green in colour.



Numeric facets

Sometimes there are non-number values or blanks in a column which may represent errors in data entry. We can find these with a Numeric facet.

Activity 24

Go to Postcode column which was transformed to numbers

Edit a few cells, replacing the numbers with text, such as “abc”, and make other cells blank

Apply a numeric facet to the column you edited

Notice that there are several checkboxes in this facet: Numeric, Non-numeric, Blank, and Error. Below these are counts of the number of cells in each category. You should see checks for Non-numeric and Blank if you changed some values.

Experiment with checking or unchecking these boxes to select subsets of your data.

When finished examining the numeric data, remove this facet by clicking the x in the upper left corner of its panel

Note that this does not undo the edits you made to the cells in this column

Use the Undo / Redo function to reverse these changes.
Page Break


Using scripts

Teaching: ? min
Exercises: 0? min

Objectives



How OpenRefine documents changes made to the data

As you conduct your data cleaning and preliminary analysis, OpenRefine saves every change you make to the dataset. These changes are saved in a format known as JSON (JavaScript Object Notation). You can export this JSON script and apply it to other data files. If you had 20 files to clean, and they all had the same type of errors (e.g. misspellings, leading white spaces), and all files had the same column names, you could save the JSON script, open a new file to clean in OpenRefine, paste in the script and run it. This gives you a quick way to clean all your related data.

Save your data wrangling work as a script

Activity 25

A script is a programming language that enables you to automate the execution of tasks.

Open Undo / Redo tab

Select Extract...

Currently all operations you have made to the dataset are highlighted

Select the steps that you want to apply to other datasets by clicking the check boxes.



Copy the code from the right-hand panel and paste it into a text editor (like NotePad on Windows or TextEdit on Mac). Save it as a plain text file.
In TextEdit, do this by selecting Format > Make plain text and save the file as a .txt file.

Page Break


Importing a script to use with another dataset

Let’s practice running these steps on a new dataset. We’ll test this on an uncleaned version of the dataset we’ve been working with.

Activity 26

Create a new project in OpenRefine using the QLDtrafficAccidentsOpenDataVer1.csv dataset you downloaded at the start of the workshop (see Activity 5 for help)

Give the project a different name

Click the Undo / Redo tab > Apply

Paste the contents of .txt file you saved.

Click Perform operations.

The dataset should now be the same as your other cleaned dataset.

For convenience, we used the same dataset.

You could use this process to clean related datasets.

For example, data that you had collected over different time periods or data that was collected by different researchers (provided everyone uses the same column headings).

The data in this file was generated from a database, so the column headings are pretty much guaranteed to be the same.

Page Break


Save & export data from OpenRefine

Teaching: ? min
Exercises: 0? min

Objectives



In OpenRefine you can save or export the cleaned data or the entire project. This means you’re saving the data and all the information about the cleaning and data transformation steps you’ve done. Once you’ve saved a project, you can open it up again and be just where you stopped before.

Save

By default, OpenRefine is saving your project continuously. If you close OpenRefine and open it up again, you’ll see a list of your projects. You can click on any one of them to open it up again.

Export cleaned data

You can export your cleaned data, with different file formats, for use in other tools for analysis.

Activity 27

Click Export in the top right and select the file type you want to export the data in. Tab-separated values (tsv) or Comma-separated values (csv) are good choices, as they are non-proprietary.

That file will be exported to your default Download directory. That file can then be opened in a spreadsheet program or imported into programs like R or Python.

Exporting a project

You can also export the project files. This is helpful if you wanted to send your raw data and cleaning steps to a collaborator, or share the information as a supplement to a publication.

Activity 28

Click the Export button in the top right and select Export project.

A tar.gz file will download to your default Download directory. Depending on your browser you may have to confirm that you want to save the file. The downloaded tar.gz file is a folder of files which have been compressed. Linux and Mac machines will have software installed to automatically expand this type of file when you double-click on it. For Windows based machines you may have to install a utility like ‘7-zip’ to expand the file and see the files in the folder.

After you have expanded the file look at the files that appear in this folder. What files are here? What information do you think these files contain?

Solution

a history folder which contains a collection of zip files. Each of these files itself contains a change.txt file. These change.txt files are the records of each individual transformation that you did to your data.

a data.zip file. When expanded, this zip file includes a file called data.txt which is a copy of your raw data. You may also see other files.



Page Break


Support and help

Will send via email after workshop

Set up troubleshooting

Installing OpenRefine in Window OS may require two things

JAVA install

Move OpenRefine program folder to c:\program files

Windows

Check that you have Firefox or Chrome browsers installed and set as your default browser. OpenRefine runs in your default browser. It will not run correctly in Internet Explorer.

Download software version 3.2 from http://openrefine.org 

Unzip the downloaded file into a directory by right-clicking and selecting “Extract…”. Name that directory something like OpenRefine.

Go to your newly created OpenRefine directory.

Move the folder to your c:\programs files\

Launch OpenRefine

Click the openrefine.exe (this will launch a command prompt window, but you can ignore that and wait for the browser to launch)

If you are using a different browser, or OpenRefine does not automatically open for you, point your browser at http://127.0.0.1:3333/ or http://localhost:3333 to launch the program.

Troubleshooting

you may also need to install Java for Windows

Check if your Windows is 32-bit or 64-bit help via: https://support.microsoft.com/en-au/help/15056/windows-32-64-bit-faq

Select appropriate bit download

(32-bit via: https://www.java.com/en/download/ 

(64-bit  via:  https://www.java.com/en/download/manual.jsp  and

select Windows Offline (64-bit) version

Choose the folder location. Save the file to c:\program files\

Close all applications including the browser.

Double-click on the saved file icon to start the installation process

https://www.howtogeek.com/129178/why-does-64-bit-windows-need-a-separate-program-files-x86-folder/



Going Further

Look at the other options on the Import screen - try changing some of these options and see how that changes the Preview and how the data appears after import.

Do you have access to JSON or XML data? If so the first stage of the import process will prompt you to select a ‘record path’ - that is the parts of the file that will form the data rows in the OpenRefine project. I have used this process with an xml file of a university’s records from Research Data Australia.

# Using scripts

*Teaching:* 10 minutes

*Exercises:* 15 minutes


## Objectives

### How OpenRefine documents changes made to the data

As you conduct your data cleaning and preliminary analysis, OpenRefine saves every change you make to the dataset. (Please note that the original dataset remains unchanged - the changes are solely made within OpenRefine and your raw data files are unaffected. Were you to export the changed data at any point, OpenRefine would offer this under a revised filename.)

These changes are saved in a format known as JSON (JavaScript Object Notation). You can export this JSON script and apply it to other data files. If you had 20 files to clean, and they all had the same type of errors (e.g., misspellings, leading white spaces), and all files had the same column names, you could save the JSON script, open a new file in OpenRefine, paste in the script, and run it to apply the changes to the new dataset. This gives you a quick way to clean all your related data.

### Save your data wrangling work as a script

#### Activity 25

A script is a series of programming steps to automate the execution of tasks.

- Open `Undo / Redo` tab

- Select `Extract ...`

Currently all the operations you have made to the dataset are highlighted within the script window.

- Select the steps that you want to apply to other datasets by using the check boxes.

- Copy the code from the right-hand panel and paste it into a text editor (like NotePad on Windows or TextEdit on Mac). 

- Save it as a plain text file.

In TextEdit, do this by selecting `Format > Make plain text` and save the file as a `.txt` file.

### Importing a script to use with another dataset

Let's practise running the script on a new dataset. We'll test this on an uncleaned version of the dataset we've been working with.

#### Activity 26

- Create a new project in OpenRefine using the `QLDtrafficAccidentsOpenDataVer1.csv` dataset you downloaded at the start of the workshop.

[See Activity 5 for what to do](data-wrangling-intro-for-hass-1.md).

- Give the project a different name this time

- Click the `Undo / Redo tab > Apply`

- Paste in the contents of .txt file you saved.

- Click `Perform operations`

The dataset should now be the same as your other cleaned dataset.

For convenience, we used the same dataset.

You could use this process to clean related datasets.

For example, you could apply your changes to data that you had collected over different time periods or data that was collected by different researchers (provided everyone uses the same column headings).

The data in this file was generated from a database, so the column headings are pretty much guaranteed to be the same.

# Save & export data from OpenRefine

*Teaching:* 5 minutes

*Exercises:* 10 minutes

## Objectives

In OpenRefine you can save or export the cleaned data or the entire project. Exporting the project as a whole means you are saving the data and all the information about the cleaning and data transformation steps you have done. Once you have saved a project, you can open it up again and pick up where you left off. The options for saving or exporting are:

**Save**

By default, OpenRefine saves your project continuously. If you close OpenRefine and open it up again, you will see a list of your projects. You can click on any one of them to reopen it.

**Export cleaned data**

You can export your cleaned data, with different file formats, for use in other tools for analysis.

#### Activity 27

- Click `Export` in the top right and select the file type for the data export. Tab-separated values (`tsv`) or Comma-separated values (`csv`) are good choices, as they are non-proprietary, but can easily be opened in programs like Excel, R, Python or the Unix shell.

Any exported file will be saved to your default `Download` directory. 

**Exporting a project**

You can also export project files as a whole. This is helpful if you wanted to send your raw data and cleaning steps to a collaborator, or share the information as a supplement to a publication.

#### Activity 28

- Click the `Export` button in the top right and select `Export project`.

A `tar.gz` file will download to your default `Download` directory. Depending on your browser, you may have to confirm that you want to save the file. The downloaded `tar.gz` file is a folder of files which have been compressed. Linux and Mac machines will have software installed to automatically expand this type of file when you double-click on it. For Windows-based machines, you may have to install a utility like '7-zip' to expand the zip file.

After you have expanded the file, look at the files that appear in this folder. What files are here? What information do you think these files contain?

> **Solution**

> - a history folder which contains a collection of zip files. Each of these files itself contains a `change.txt` file. 
> These `change.txt` files are the records of each individual transformation that you performed on your data.

> - a data.zip file. When expanded, this zip file includes a file called `data.txt` which is a copy of your raw data. You may also see other files.





### Going Further

Look at the other options on the Import screen - try changing some of these options and see how that changes the `Preview` and how the data appears after import.

Do you have access to JSON or XML data? If so, the first stage of the import process will prompt you to select a 'record path' - that is, the parts of the file that will form the data rows in the OpenRefine project. 

[Go to the previous part of the lesson](data-wrangling-intro-for-hass-7.md).
[Go back to the start](data-wrangling-intro-for-hass-1.md).

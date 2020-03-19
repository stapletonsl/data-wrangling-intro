# Using scripts

*Teaching:* ? minutes

*Exercises:* 0? minutes


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



### Going Further

Look at the other options on the Import screen - try changing some of these options and see how that changes the Preview and how the data appears after import.

Do you have access to JSON or XML data? If so the first stage of the import process will prompt you to select a ‘record path’ - that is the parts of the file that will form the data rows in the OpenRefine project. I have used this process with an xml file of a university’s records from Research Data Australia.


[Go to the previous part of the lesson](data-wrangling-intro-for-hass-7.md).
[Go back to the start](data-wrangling-intro-for-hass-1.md).

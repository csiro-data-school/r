---
# Please do not edit this file directly; it is auto generated.
# Instead, please edit 01-R-and-RStudio.md in _episodes_rmd/
title:   Introduction to R and R Studio 
teaching: 45
exercises: 10
questions:
objectives:
keypoints:
source: Rmd
---



## Why should you use R?


[What is R and what makes it different from the other software packages out there?] (https://select-statistics.co.uk/blog/what-is-r-and-why-should-you-use-it/)
Well, R is designed specifically for statistical computing and graphics.
It is free and open source, the latter meaning that anyone can interrogate the code to see what’s going on –  there’s no black box involved.
R provides a flexible analysis toolkit where all of the standard statistical techniques are built-in. 
Not only that, but there is a large R community who regularly contribute new functionality through add-on ‘packages’.
In fact, finding a particular statistical model or technique that is not already available through R is a tricky task indeed!

## Tour of R Studio
*Basic layout**

When you first open RStudio, you will be greeted by three panels:

  * The interactive R console/terminal (entire left)
  * Environment/History (tabbed in upper right)
  * Files/Plots/Packages/Help/Viewer (tabbed in lower right)

<!--![RStudio layout](../fig/01-rstudio.png) -->

Once you open files, such as R scripts, an editor panel will also open
in the top left.

<!--![RStudio layout with .R file open](../fig/01-rstudio-script.png) -->

You can move the panels around in RStudio so that their arrangement suits you.

Your time in R will be split between the R interactive
console working in scripts. The console is where you will run all of your code, and can be a useful environment to try out ideas before adding them to an R script
file. This console in RStudio is the same as the one you would get if
you typed in `R` in your command-line environment.


## Show code in R

The simplest thing you could do with R is do arithmetic:


~~~
1 + 100
~~~
{: .language-r}



~~~
[1] 101
~~~
{: .output}
And R will print out the answer, with a preceding “[1]”. Don’t worry about this for now, we’ll explain that later. For now think of it as indicating output.

## Show code in R Studio

Now you will enter some calculations into your script file, and either copy this to the 
console window or highlight the code and Control Enter to run the code.  Notice that
the output is show in the console window.

~~~
(3 + 5) * 2
~~~
{: .language-r}



~~~
[1] 16
~~~
{: .output}




## Work flow within RStudio
There are two main ways one can work within RStudio.

1. Test and play within the interactive R console then copy code into
a .R file to run later.
   *  This works well when doing small tests and initially starting off.
   *  It quickly becomes laborious
2. Start writing in an .R file and use RStudio's short cut keys for the Run command
to push the current line, selected lines or modified lines to the
interactive R console.
   * This is a great way to start; all your code is saved for later
   * You will be able to run the file you create from within RStudio
   or using R's `source()`  function.

> ## Tip: Running segments of your code
>
> RStudio offers you great flexibility in running code from within the editor
> window. There are buttons, menu choices, and keyboard shortcuts. To run the
> current line, you can 1. click on the `Run` button above the editor panel,
> or 2. select "Run Lines" from the "Code" menu, or 3. hit
> <kbd>Ctrl</kbd>+<kbd>Return</kbd> in Windows or Linux or
> <kbd>&#8984;</kbd>+<kbd>Return</kbd> on OS X. (This shortcut can also 
> be seen by hovering
> the mouse over the button). To run a block of code, select it and then `Run`.
> If you have modified a line of code within a block of code you have just run,
> there is no need to reselct the section and `Run`, you can use the next button
> along, `Re-run the previous region`. This will run the previous code block
> including the modifications you have made.
{: .callout}


# Projects

R Studio provides in-built support for keeping all files associated with a project 
together.  This includes the input data, R Scripts, analytical results and figures.

A good project layout will ultimately make your life easier:

* It will help ensure the integrity of your data;
* It makes it simpler to share your code with someone else
(a lab-mate, collaborator, or supervisor);
* It allows you to easily upload your code with your manuscript submission;
* It makes it easier to pick the project back up after a break.


> ## Challenge: Creating a self-contained project
>
> We're going to create a new project in RStudio:
>
> 1. Click the "File" menu button, then "New Project".
> 2. Click "New Directory".
> 3. Click "Empty Project".
> 4. Type in the name of the directory to store your project, e.g. "my_project".
> 5. If available, select the checkbox for "Create a git repository."
> 6. Click the "Create Project" button.
{: .challenge}

Now when we start R in this project directory, or open this project with RStudio,
all of our work on this project will be entirely self-contained in this directory.

## Best practices for project organization

Although there is no "best" way to lay out a project, there are some general
principles to adhere to that will make project management easier:

### Treat data as read only

This is probably the most important goal of setting up a project. Data is
typically time consuming and/or expensive to collect. Working with them
interactively (e.g., in Excel) where they can be modified means you are never
sure of where the data came from, or how it has been modified since collection.
It is therefore a good idea to treat your data as "read-only".

### Data Cleaning

In many cases your data will be "dirty": it will need significant preprocessing
to get into a format R (or any other programming language) will find useful. This
task is sometimes called "data munging". I find it useful to store these scripts
in a separate folder, and create a second "read-only" data folder to hold the
"cleaned" data sets.

### Treat generated output as disposable

Anything generated by your scripts should be treated as disposable: it should
all be able to be regenerated from your scripts.

There are lots of different ways to manage this output. I find it useful to
have an output folder with different sub-directories for each separate
analysis. This makes it easier later, as many of my analyses are exploratory
and don't end up being used in the final project, and some of the analyses
get shared between projects.

> ## Tip: Good Enough Practices for Scientific Computing
>
> [Good Enough Practices for Scientific Computing](https://github.com/swcarpentry/good-enough-practices-in-scientific-computing/blob/gh-pages/good-enough-practices-for-scientific-computing.pdf) gives the following recommendations for project organization:
>
> 1. Put each project in its own directory, which is named after the project.
> 2. Put text documents associated with the project in the `doc` directory.
> 3. Put raw data and metadata in the `data` directory, and files generated during cleanup and analysis in a `results` directory.
> 4. Put source for the project's scripts and programs in the `src` directory, and programs brought in from elsewhere or compiled locally in the `bin` directory.
> 5. Name all files to reflect their content or function.
>
{: .callout}
> ## Tip: ProjectTemplate - a possible solution
>
> One way to automate the management of projects is to install the third-party package, `ProjectTemplate`.
> This package will set up an ideal directory structure for project management.
> This is very useful as it enables you to have your analysis pipeline/workflow organised and structured.
> Together with the default RStudio project functionality and Git you will be able to keep track of your
> work as well as be able to share your work with collaborators.
>
> 1. Install `ProjectTemplate`.
> 2. Load the library
> 3. Initialise the project:
>
> 
> ~~~
> install.packages("ProjectTemplate")
> library("ProjectTemplate")
> create.project("../my_project", merge.strategy = "allow.non.conflict")
> ~~~
> {: .language-r}
>
> For more information on ProjectTemplate and its functionality visit the
> home page [ProjectTemplate](http://projecttemplate.net/index.html)
{: .callout}
### Separate function definition and application

One of the more effective ways to work with R is to start by writing the code you want to run directly in an .R script, and then running the selected lines (either using the keyboard shortcuts in RStudio or clicking the "Run" button) in the interactive R console.

When your project is in its early stages, the initial .R script file usually contains many lines
of directly executed code. As it matures, reusable chunks get pulled into their
own functions. It's a good idea to separate these functions into two separate folders; one
to store useful functions that you'll reuse across analyses and projects, and
one to store the analysis scripts.

> ## Tip: avoiding duplication
>
> You may find yourself using data or analysis scripts across several projects.
> Typically you want to avoid duplication to save space and avoid having to
> make updates to code in multiple places.
>
> In this case I find it useful to make "symbolic links", which are essentially
> shortcuts to files somewhere else on a filesystem. On Linux and OS X you can
> use the `ln -s` command, and on Windows you can either create a shortcut or
> use the `mklink` command from the windows terminal.
{: .callout}
### Save the data in the data directory

Now we have a good directory structure we will now place/save the data file in the `data/` directory.

> ## Challenge 1
> Download the gapminder data from [here]({{ page.root }}/data/gapminder-FiveYearData.csv).
>
> 1. Download the file (right mouse click -> "Save as")
> 2. Make sure it's saved under the name `gapminder-FiveYearData.csv`
> 3. Save the file in the `data/` folder within your project.
>
> We will load and inspect these data later.
{: .challenge}
> ## Challenge 2
> It is useful to get some general idea about the dataset, directly from the
> command line, before loading it into R. Understanding the dataset better
> will come in handy when making decisions on how to load it in R. Use the command-line
> shell to answer the following questions:
> 1. What is the size of the file?
> 2. How many rows of data does it contain?
> 3. What kinds of values are stored in this file?
>
> > ## Solution to Challenge 2
> >
> > By running these commands in the shell:
> > 
> > ~~~
> > ls -lh data/gapminder-FiveYearData.csv
> > ~~~
> > {: .language-r}
> > 
> > 
> > 
> > 
> > ~~~
> > -rw-r--r--  1 pea25i  348785    80K 27 Feb 09:23 data/gapminder-FiveYearData.csv
> > ~~~
> > {: .output}
> > The file size is 80K.
> > 
> > ~~~
> > wc -l data/gapminder-FiveYearData.csv
> > ~~~
> > {: .language-r}
> > 
> > 
> > 
> > 
> > ~~~
> >     1705 data/gapminder-FiveYearData.csv
> > ~~~
> > {: .output}
> > There are 1705 lines. The data looks like:
> > 
> > ~~~
> > head data/gapminder-FiveYearData.csv
> > ~~~
> > {: .language-r}
> > 
> > 
> > 
> > 
> > ~~~
> > country,year,pop,continent,lifeExp,gdpPercap
> > Afghanistan,1952,8425333,Asia,28.801,779.4453145
> > Afghanistan,1957,9240934,Asia,30.332,820.8530296
> > Afghanistan,1962,10267083,Asia,31.997,853.10071
> > Afghanistan,1967,11537966,Asia,34.02,836.1971382
> > Afghanistan,1972,13079460,Asia,36.088,739.9811058
> > Afghanistan,1977,14880372,Asia,38.438,786.11336
> > Afghanistan,1982,12881816,Asia,39.854,978.0114388
> > Afghanistan,1987,13867957,Asia,40.822,852.3959448
> > Afghanistan,1992,16317921,Asia,41.674,649.3413952
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}
> ## Tip: command line in R Studio
>
> You can quickly open up a shell in RStudio using the **Tools -> Shell...** menu item.
{: .callout}



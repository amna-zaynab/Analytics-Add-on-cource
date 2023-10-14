## R4WRDS Introductory Course

Unleasing the power of reproducible workflows with “R for Water Resources Data Science” (R 4 WRDS).

### Who is this course for?

This course is most relevant and targeted at folks who work with data, from analysts and program staff to engineers and scientists. This course provides an introduction to the power and possibility of a reproducible programming language (R) by demonstrating how to import, explore, visualize, analyze, and communicate different types of data. Using water resources based examples, this course guides participants through basic data science skills and strategies for continued learning and use of R.

### Why R?

R is a language for statistical computing and a general purpose programming language. It is one of the primary languages used for data science, modeling, and visualization.

This workshop will provide attendees with a starting point for continued learning and use of R. We will cover a variety of commonly used file types (i.e., .csv, .xlsx, .shp) used in analysis, and provide resources for additional learning.

### What will you learn?

In this course, we start from first principles and assume no prior experience with R. Although each module in this course can serve as a “stand-alone” lesson, we recommend completing modules in order from start to finish.

**In this course you will gain practice in:**

- Data and file management: understanding RProjects and file paths
- Understand and identifying different data formats (i.e., wide, long, tidy)
- Working with different data structures (i.e., vectors, dataframes, lists)
- Importing and exporting various water resources data
- Strategies for Exploratory Data Analysis (EDA)
- Strategies for troubleshooting (reading documentation, intro to reprex)
- Transforming data with {dplyr}
- Data visualization with {ggplot2}
- Data presentation and communication with RMarkdown

# 1. Software Installation & Setup

Welcome! There’s a few things we’d like everyone to try and do before the workshop starts. For this workshop and the following lessons, we need to install the following programs/software in this order (more details below for different operating systems):

Our goal is for you to learn how to use these tools so you can get stuff done. You can learn to be an expert later! These are guidelines to install the necessary tools. Feel free to let us know if you run into trouble!

1. Install R 

2. Install RStudio 

3. Install R Packages & Test They Work

4. Install Geospatial Packages and {sf}

5. Download Data for the Workshop

Below, we provide extra details appropriate for Windows and MacOSX operating systems. For additional installation options, see here.

## **Step 1. Install  R**

R is the underlying statistical computing environment, or the engine we use to do things.

**Windows: Download and install R** 

Go to CRAN and download the R installer for Windows. Make sure to choose the latest stable version. Download the .exe file and double click to install.

- You can click next through the standard dialogs and accept most defaults. But at the destination screen, please verify that R is installing C:\Program Files\R (version number may vary), and you may need administrative privileges to do this if you’re not working on your personal computer.

At the “Select Components” screen, you can accept the default and install both 32-bit and 64-bit versions.

At this screen, uncheck “Create a desktop icon” because non-admin users in Windows will be unable to delete it.

## **Step 2. Install  RStudio Desktop**

Using R alone is possible, but less ideal (and less fun!). RStudio is an open-source graphical Integrated Development Environment or IDE that makes using R much easier and more interactive. In this course, we will use the free RStudio Desktop version.

**Windows: Download and install RStudio Desktop (free)**

- Download and install from RStudio
- Select RStudio x.yy.zz - Windows Vista/7/8/10 (where x, y, z are version numbers)
- Double-click the installer. It will ask for your administrator credentials to install, so you may need IT assistance if using a work computer.
- Accept all the default options for the RStudio install

**macOS: Download and install RStudio Desktop (free)**

- Go to the RStudio download page
- Under Installers select RStudio x.yy.zzz - Mac OS X 10.6+ (64-bit) (where x, y, and z represent version numbers)
- Double click the file to install RStudio
- Once it’s installed, open RStudio to make sure it works and you don’t get any error messages.


**Check Install!** 

Once installed, RStudio should be accessible from the start menu. Start up RStudio.

- Find “Console” window: By default the console window will be on the left side of RStudio. Find that window. It will looking something like:

- Copy and paste the following code: Once in that console window, copy the code below and paste it into the Console window (just to the right of the little >). Then hit ENTER.

```{r}
version$version.string

```
- Verify your installed R version: Ideally you should be running the latest stable release. If you have an older version, please install the newest version using the instructions above.

## **Step 3. Install R Packages**

The core set of packages we will need are as follows. There may be a few more we need to install during the course, but this should be the majority.

We install packages available for all R users from an online repository called CRAN, by pasting the following code into the RStudio Console window and hitting ENTER.

```{r}
install.packages("tidyverse")
install.packages("viridis")
install.packages("openxlsx")
install.packages("readxl")
install.packages("lubridate")
```

Compilation means the code associated with the package needs to be translated into R and built for your operating system. Generally we can use the binary option, so after that message type “No” and hit “Enter” on the keyboard. In some cases we do need/want to compile the package to get the most recent updates. For this course, try installing from binary (type No) first!

## **Step 4. Install Geospatial Packages**

For some of the mapping and spatial lessons, we need a set of geospatial tools/packages. For the majority of the content we will cover, this requires installation of the {sf} package. When we run the lines below, we may get a question in the Console that is preceded by a list of package names and columns with binary, source, and needs_compilation. That’s ok!

The First Option should be to try and install without compilation. So, if you run the lines below:

```{r}
install.packages("sf")
install.packages("mapview")
```

## **Installing from Source (with Compilation)**

However, more commonly, we may need to install/update from source to have the most updated functions and options from a package (don’t worry if you have no idea what this all means yet!). This generally means the code needs to be translated and built or compiled so your computer can interpret it. To do so, we need to follow instructions below for the operating system of your choice.

**Windows Geospatial Instructions (from source):**

To install {sf} successfully from source, Windows users will need to install Rtools. Download the 64-bit compiler. Use the “R-release” version, not the R-devel version. R-release is the stable version, and the devel version is in development.

Ensure that the Rtools installation matches the version of R you downloaded. For example if you downloaded R version 4.2.3, you would want Rtools version 4.2.

**MacOS Geospatial Instructions (from source):**

For MacOS users, follow the recommended instructions on the {sf} webpage, which if possible, requires opening a Terminal window and successfully installing Homebrew with the code at this website. You can test if brew is installed by typing brew config in the Terminal and hitting Enter.

We can then install a few spatial tools (via Terminal still!) with the following code:

At this point, you should now be able to install {sf} from binary on a Mac. Proceed to the next section!

**Install Spatial R Packages**

After this has successfully installed, return to the RStudio “Console”, and install the following packages by typing the following into the console and pressing “return” on the keyboard:

```{r}
install.packages("sf")
install.packages("mapview")
```
For {sf}, try installing from binary first (so type “No” in your R Console window and hit Enter).

Success should return something like this (not an error message) when you load the library with library(sf):

```{r}
library(sf)
```

Additional geospatial installation instructions can be found here, but try the listed approach first.
As a final sanity check, copy/paste the following in the console in RStudio and press Enter. This will open an interactive map of the built-in dataset breweries in the “Viewer” pane, and will look like the map below. Click on points and pan around to celebrate a successful install!

```{r}
library(mapview)
mapview(breweries)
```

## **Step 5. Download Workshop Datasets**


We’ll be working with a few different datasets for this workshop (see here). We’ve zipped all these files into a single folder, which can be downloaded here. Bear in mind this .zip file is ~30 MB in size, and may take a few minutes to download depending on internet connections.

- Download the zipped file of all intro course data.
- We will help you set up a project and put the data in the correct place.

**Quick Test!**

Just to make sure each package installed successfully, do the following:

Open up RStudio
Find the “Console.” This is usually the bottom left pane in RStudio
In the “Console”, find the R Prompt (the part that starts with >)
Type in (or copy and paste from here will also work) the following command at the R Prompt and hit return
```{r}
# check that these packages are installed successfully:
c("tidyverse", "sf", "viridis", "mapview") %in% installed.packages()
```

If you have successfully installed packages, you should see a list of “TRUE” repeated once for each package listed inside the c( ).

## 2. Getting Started with R for Water Resources Data Science

### **Welcome!**

The goals of this training are to expose you to fundamentals and to develop an appreciation of what is possible with R. Importantly, we hope to instill the idea that data science should be transferable and reproducible, no matter the specific tools (i.e., R) or the dataset used. Reproducibility is a framework and mindset. An introductory course will not make you an expert, but hopefully it will draw you in, build excitement about using reproducible approaches to your own work, and show you how to be more efficient and less stressed when faced with messy real-world data!

We hope you will find this workshop both fun and helpful, and we appreciate your patience as we continue to develop this course, both virtually and elsewhere! We would also like to thank Allison Horst for allowing us to use her incredible monsteRs and R illustrations that you will see included throughout this course.

### **Why R? Why Data Science?**


Computer literacy is essential in all aspects of the working world. The ability to reproduce a set of common or repetitive tasks efficiently and reliably is the root goal of reproducibility. Whether in science, management, or other fields, the skills required to increase productivity, maintain transparency, and feel competent and able to tackle multiple tasks all boil down to data science and project management tools.

Data management skills are needed for entering data without errors, storing it in a usable way, and extracting key aspects of the data for analysis. Basic programming is required for everything from accessing and managing data, data visualization, to statistical analysis and modeling. Data science combines the skills and tools that allow for acquisition, processing, analyzing, communicating, and maintenance data of any type.

### **Course Objectives**
This course’s main objective is to provide students with a introduction to the power and possibility that an open source (free) and reproducible programming language such as R provides by demonstrating how to import, explore, visualize, and communicate different types of data. Using water resources based examples, this course will guide students through basic data science skills and strategies for continued learning and use of R. R is a language for statistical computing and a general purpose programming language. It is one of the primary languages used in data science and for data analysis across many of the natural sciences. This course will provide lessons in:

- Data and file management: understanding RProjects and file paths
- Understanding and identifying different data formats (i.e., wide, long, tidy) and data structures (i.e., vectors, dataframes, lists)
- Importing and exporting various water resources data
- Strategies for Exploratory Data Analysis (EDA)
- Strategies for troubleshooting (reading documentation, reproducible examples)
- Transforming data with {dplyr}
- Data visualization with {ggplot2}

### **Why should I invest time in learning R?**
There are many programming languages available and each has specific benefits. R was originally created as a statistical programming language but now is largely viewed as a ‘data science’ language. R is also an open-source programming language - not only is it free, but this means anybody can contribute to its development. Furthermore, R has powerful and nearly limitless plotting/visualization functionality, and you can adjust nearly any aspect of a graph to communicate your data effectively.

As Hadley Wickham, a prominent R developer, states:

>“R is not just a programming language, but it is also an interactive environment for doing data science. To support interaction, R is a much more flexible language than many of its peers… it helps you think about problems as a data scientist, while supporting fluent interaction between your brain and the computer. (R4DS)”


### **R/RStudio Fundamentals**

In the old days, the only way to use R was directly from the Console - this is a bare bones way of running R only with direct input of commands. Now, RStudio is the go-to Interactive Development Environment (IDE) for R. Think of it like a car that is built around an engine. RStudio is built around the R Console (engine) and includes many other features to improve the user’s experience.

Let’s get familiar with RStudio. If you haven’t done so already, download and install RStudio from the link above for the most recent version. After it’s installed, find the RStudio shortcut and fire it up. 
Data presentation and communication with RMarkdown

There are four panes in RStudio (starting from the top right and moving clockwise):

- Source
- Environment, History, etc.
- Files, Plots, etc.
- Console

### Executing code in RStudio (Console)
The first part of RStudio that we will work in is called the Console, which tells you what code R is running. We can use many of the same commands found in a calculator or Microsoft Excel.

Type the following text into the console at the line that ends with >, press Enter, and you should see the following results:

```{r}
# enter in console (after the ">" mark)
8 / 4
```

```{r}
# enter in console (after the ">" mark)
4 + 8
```

### Storing Variables in the Environment

You can also create variables with custom values (we’ll talk much more about this later). But here are the basics, the first part of the code is a name of your choosing. Meaningful variable names are better, but the only rules are: 1) that it can’t start with a number and 2) it must not have any spaces. The second bit, <-, is the assignment operator. This tells R to take the result of whatever is on the right side of the <- and save it as a new object in your R Environment.

Type the following into your Console and press enter after each one to see their output:

```{r}
# assign the value 4 to the variable name "stream"
stream <- 4
```

```{r}
# assign the value 8 to the variable name "pebble"
pebble <- 8
```

You might notice is no output in the Console for the lines of code you have just run. Instead, they have been stored in your R Environment in the top right pane of your RStudio window. Click on that tab and take a look! Because they have been stored, you can print these variables by typing their name in the Console and pressing Enter.

Generally there are two possible outcomes when you run code. First, the code will simply print output directly in the console, as it did with the calculations you entered above. Second, there is no output because you have stored it as a variable in the Environment. The Environment is the collection of named objects that are stored in memory for your current R session. Anything stored in memory will be accessible by the variable name without running the original script that was used to create it.

Add the variables you just created together, and examine the output:

```{r}
stream + pebble
```

You can also create new variables using existing variables like so:

```{r}
habitat <- stream + pebble
```

Keep in mind R is case-sensitive! Details like spacing and spelling matter in coding (the computer will do only exactly what you say, nothing more, nothing less), so if we use Habitat or habitatt or ha_bitat hoping to get the value of habitat, we’re out of luck.

**Please note:** Clicking on the broom button in the Environment will permanently clear out your existing variables. Only do this if you are certain you want to remove/reset all saved variables and datasets.

In this same pane in the RStudio window is the History tab, which will record all the code you’ve run, and the Connections tab will show connections to other databases, etc.

### **Installing Packages (Files etc tab)**

Immediately below the Environment is the third section of RStudio, where all of your Packages are stored. The base or core installation of R is quite powerful, but because R is open-source, there are thousands of packages (pieces of code we can download and use) that dramatically extend the capability of R, from statistical analysis, to modeling, to geospatial mapping, to website and document creation. Packages are the collection of code or functions that are a standardized way of extending R with new methods, techniques, and programming functionality.

**CRAN**

One of the reasons for R’s popularity is CRAN, The Comprehensive R Archive Network. CRAN is where you download R and also where you can gain access to additional packages. All of the packages we will use during this tutorial will be downloaded from CRAN. As of 2023-01-24, there are 19,002 packages on CRAN!

**Installing {tidyverse}**

When a package is installed, that means the source code is downloaded and put into your library. Let’s give it a shot using the {tidyverse}, a set of packages assembled for data tidying and visualization purposes.

We’re going to use our very first function: install.packages() to install this package. Type the following into your Console and press enter:

```{r}
install.packages("tidyverse")
```


You should see it appear in the Packages tab. To find it, you can either scroll through the list, or type the package name into the search bar at the top of the pane.

In order to use a package, you must load it into your current workspace. This is sometimes called attaching a package, but we prefer to avoid clicking whenever possible, so we’ll load this package using the library() function. Type the following into your Console and press Enter:

```{r}
library(tidyverse)
```

Now your package is loaded, and ready to use. You can be certain your package is attached if there is a check mark next to the package name in the Packages tab.

**- General rule of thumb: Load packages once per session, install packages once per computer or R version!**

### Getting Help

Being able to find help and interpret that help is probably one of the most important skills for learning a new language. We have a whole lesson devoted to help and troubleshooting, but here’s a quick overview for “local” help that is already built into R and RStudio. Help on functions and packages can be accessed directly from R.

Help from the Console
Getting help from the Console is straightforward and can be done numerous ways. If you know the name of the function or package we can type that as follows:

```{r}
# Using the help command/shortcut
# When you know the name of a function
help("print") # Help on the print command
?print # Help on the print command using the `?` shortcut

# When you know the name of the package
help(package = "dplyr") # Help on the package `dplyr`
```

If we don’t know the name, or maybe just want to look for a part of something, we can use the following in the Console:

```{r}
# Don't know the exact name or just part of it?

apropos("print") # Returns all available functions with "print" in the name

??print # shortcut, but also searches demos and vignettes in a formatted page

```

## **3. Project Management: Let’s Get Organized**

**LEARNING OBJECTIVES**

- Understand motivation for project based workflows
- Know how to organize code, data, and results
- Know the basics of file paths and directory structures
- Be able to create and use an RStudio project

### **Where Am I?**

Any time you are working on your computer, you must navigate amidst a forest of files and folders.

>One of the most common issues we deal with in R programming is to tell your computer where a file or folder is located.

Thus, one of the most useful habits you can form (whether using R or not), is to intentionally keep a clear structure and use that same structure across all of your projects. This becomes especially important when using computer programming languages like  in your work. You will need to tell R, very specifically, where you are and where your files are located in the forest of your computer.

Where you are is typically referred to as the working directory. The working directory is a folder. In , think of this as your homebase, and everything is relative to this folder on your computer.

### Use Project Workflows

One of the great advantages of using tools like RStudio is they make it easy to use an organized “project” workflow. What do we mean by “using projects”? Projects refer to a general pattern or structure used for each work project or analysis. This approach is not specific to R. Any practiced data scientist will use a folder structure and organization scheme, no matter what programming language they use.

The general idea is to always use the same structure and naming schemes across every project. Do this every single time with every single project you make, in order to make it a habit. This will save you time and brainpower! Imagine quickly moving between tasks or projects with minimal time spent “trying to find where things are and getting oriented”. You’ll always know where things should be!

**Basic Folders for Every Project**

At a minimum, it’s useful to have separate directories (folders) for each of the following:

**- data:** Ideally keep data in a .csv format, because these simple and universal data. You may have other specialized formats as well. This is generally where original, raw data lives.
**- data_output:** This is where you save any data or analysis outputs. Any time you clean, tidy, summarize, or otherwise manipulate the data and save it out, it should end up somewhere clearly different than the raw data location.
**- scripts:** In the  world, “scripts” are generally .R files. However, you may have .do files if wokring with Stata, .py files for Python, and so on. Using a sequential numbering file naming scheme can be useful. Remember to pad with a zero to make file sorting/ordering easy (e.g., 00_script_a.R, 01_script_b.py, etc).
**- results:** These may include model results, data analysis, slides, and so on. Some like to keep figures in this folder and others prefer a specific figures folder.
**- documents:** This is a place you can keep documents, papers, pdfs, etc. These may include files with .docx, .Rmd (for RMarkdown), .pdf or even .html extensions.


**RStudio Projects**

Within the R environment, something that makes project management and organization much easier is the use of RStudio Projects (.Rproj file). RStudio makes the use of Projects straightforward. One of the nicest parts of using RStudio Projects is that they automatically set the working directory to the folder containing a specified .RProj file. You can make any existing folder an RProject folder, or make a new one. RStudio projects are a great way to quickly and easily organize your workflows; each project can be a specific task, or a larger set of objectives you need to complete. With RStudio Projects, it’s easy to switch between projects, or work on different projects simultaneously without much mental overload, especially if you use the same project folder structure across each project!

Avoid using setwd()! More reasons and rationale linked here.

**Setting up an .Rproj**

Let’s create an RStudio Project as part of this course that you can use throughout each module. We highly recommend that no matter what you are working on in R, that you try to do it within the structure of an RStudio Project!

1. Open RStudio and navigate to the upper right-hand side where it says “Project: (None)”. If we click on this button, we should see some options. Select New Project.
2. We can use either a New Directory, or setup a project in an Existing Directory. Both give similar options.
3. Select “New Project”
4. Make a new sub-directory folder (if you don’t have it) under your Documents folder called: Rprojects
5. Finally, we can name our new project (remember no spaces in our folder/file names!): intro_r4wrds


**Make Folders & Add Data**

Great! Now we can create a folder structure in our project as discussed in the Basic Folders for Every Project section above. More importantly, we can also put all our course data into the data folder in your RStudio project.

Let’s go ahead and make the following folders (HINT: you can use the “New Folder” button in RStudio, or use the code below!)

- data
- data_output
- figures
- scripts
Then in your Console tab, you can enter this code to download the data directly into your project!

```{r}
dir.create("data") # warning is ok if already exists!

# downloads the file (data.zip) to your data directory
download.file("https://github.com/r4wrds/r4wrds-data-intro/raw/main/data.zip", destfile = "data/data.zip")

# unzip the data we need for the course:
unzip(zipfile = "data/data.zip")
```

### File Paths

In R, file paths are always wrapped in quotes. There are 2 basic kinds of file paths:

**- Absolute:** Absolute paths list out the full file path, usually starting with your username, which you can also refer to using the shortcut ~. So instead of C:/MyName/Documents or /Users/MyName/Documents, you can type ~/Documents. But generally, the only place an absolute path will work is your computer! It will break on anyone else computer, or anytime you move or rename something!

**- Relative:** Relative paths are relative to your working directory. So if R thinks we’re in that ~/MyName/Documents/Projects/2020 folder, and we want to access a file in a folder inside it called data, we can type data/my_file instead of ~MyName/Documents/Projects/2020/data.

The good news is if you setup an RStudio project as shown above, you can use relative filepaths with ease!

**The Working Directory**

Our working directory should be the root place where our project lives (as shown above). You can always check what R thinks is the working directory with getwd(), and you should see the folder where your .Rproj file lives! Importantly, everything you do should be relative to that working directory.

That means we really don’t want to use things like setwd() (set working directory) to locate a file or folder on our computer, or use a hard path (i.e., a full path like C:/MyUserName/My_Documents/A_Folder_You_May_Have/But_This_One_You_Definitely_Dont/). That’s because this will pretty much never work on anyone’s computer other than your own, and sometimes it may not even work on your own computer if you change a file name or folder! How can we make things reproducible for others, and for our future self? We advise using the {here} package.

**Using the {here} package**

Good news! There’s a package designed to make project-based workflows work so that code is portable between machines (i.e., you can share your project with a collaborator and they don’t need to fiddle with working directories and file paths). The {here} package makes it easy to create a path relative to the top-level directory (the place where your current project is) with a single function: here(). In addition, we can use here() to build a relative path to a file for saving or loading. Let’s say we’re working in our MyName/Documents/Projects/2020 folder.

```{r}
library(here)

# identify your working directory.
here()

# will be something like this:
#> [1] /Users/MyName/Documents/Projects/MyProject

# read a file from our data folder! `data/nwis_sites_american_river.csv`
read.csv(here("data", "nwis_sites_american_river.csv"))
```

Using the {here} package means we can share our project with other folks and it will work, and if something changes around inside the project, it will remain functional and accessible.

In practice however, if we always work from within an RProject, we can simply use relative paths without the here() syntax – that syntax just makes it very explicit what we’re doing.

### Best Practices: Project Organization/Workflow Tips

Although there is no “best” way to lay out a project, there are some general principles to adhere to that will make project management easier. Here’s some sage advice from Jenny Bryan and Jim Hester from What They Forgot to Teach you About R (worth checking out!):

- File system discipline: put all the files related to a single project in a designated folder.
- This applies to data, code, figures, notes, etc.
- Depending on project complexity, you might enforce further organization into subfolders.
- Use a standard naming convention for files & folders (no spaces!).
- Don’t use absolute paths!
- File path discipline: all paths are relative and, by default, relative to the project’s (your working directory) folder.

**Always start R as a blank slate**

When you quit R, do not save the workspace to an .Rdata file. When you launch, do not reload the workspace from an .Rdata file.

In fact, we should all make our default setting a blank slate. We should only be loading and working on data and code that we knowingly and willingly open or import into R.

>In RStudio, set this via Tools > Global Options

**Safe File Naming**

This is really important and will make life easier for everyone in the long run. Jenny Bryan has the best set of slides on this, so take a few minutes and go read them. Then be the change!

>Slides You Need to Read

**TL&DR** (Too long, didn’t read)

- File names should be machine readable (i.e., no spaces)
- Human readable (m_import_clean_data.R)
- Makes default ordering easy (i.e., dates are always YYYY-MM-DD)

**Treat raw data as Read Only**

This is probably the most important tip for making a project reproducible and hassle free. Raw data should never be edited, because you don’t want to permanently change your starting point in an analysis, and you want to have a record of any changes you make to data. Therefore, treat your raw data as “read only”, perhaps even making a raw_data directory that is never modified. If you do some data cleaning or modification, save the modified file separate from the raw data, and ideally keep all the modifying actions in a script so that you can review and revise them as needed in the future.

**Treat generated output as disposable**

Anything generated by your scripts should be treated as disposable: it should all be able to be regenerated with code. Don’t get attached to anything other than your raw data, and your code! There are lots of different ways to manage this output, and what’s best may depend on the particular kind of project.

### Summary
There are many ways to use project-based workflows in R. Importantly, we advise that you find a strategy that works for the majority of the work you do, and then be consistent about organizing things the same way (from folder structure to file naming). This will help folks you work with, it will help you (including your future self), and you spend less time figuring out where you are (and where the pieces you need to do work with are) and more time doing the work you need to do!

>Lesson adapted from R-DAVIS, Jenny Bryan and Jim Hester’s What they forgot to teach you about R, and the Data Carpentry: R for data analysis and visualization of Ecological Data lessons.

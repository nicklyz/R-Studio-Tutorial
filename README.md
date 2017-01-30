# R-Studio-Tutorial

This is a tutorial for R Studio, a tool demo for UCLA CS 239 Data Science in Software Engineering.

To learn the basic syntax of R, here are some useful resources:

* http://www.cyclismo.org/tutorial/R/
* https://www.tutorialspoint.com/r/

## Installation

### 1. Install R

**For windows:**

1. Download the binary setup file for R from the following link. ([R for Windows](https://cran.r-project.org/bin/windows/base/))

2. Open the downloaded .exe file and Install R

**For Mac:**

1. Download the appropriate version of .pkg file form the following link. ([R for Mac](https://cran.r-project.org/bin/macosx/))

2. Open the downloaded .pkg file and Install R

**For Linux:**

1. For complete R System installation in Linux, follow the instructions on the following link ( [R for Linux](https://cran.r-project.org/bin/linux/ubuntu/README) )

2. For Ubuntu with Apt-get installed, execute sudo apt-get install r-base in terminal.

### 2. Install R-Studio

Click the following link [Download R Studio](https://www.rstudio.com/products/rstudio/download/), download the appropriate installer file for your operating system, and run it to install R-studio.

### 3. Install Packages (Optional)

If your need to use R requires a particular package/library to be installed in R-studio. You can follow the instructions below to do so:

1. Run R Studio;

2. Click on the Packages tab in the bottom-right section and then click on install. The following dialog box will appear;

3. In the Install Packages dialog, write the package name you want to install under the Packages field and then click install. This will install the package you searched for or give you a list of matching package based on your package text.


## Basic Data Analysis through R/R Studio

In this tutorial, I'll design a basic data analysis program in R using R Studio by utilizing the features of R Studio to create some visual representation of that data. Following steps will be performed to achieve our goal.

1. Downloading/importing data in R
2. Transforming Data / Running queries on data
3. Basic data analysis using statistical averages
4. Plotting data distribution.

Let's go over the tutorial by performing one step at a time.

### 1. Importing Data in R Studio
For this tutorial we will use the sample census data set ACS . There are two ways to import this data in R. One way is to import the data programmatically by executing the following command in the console window of R Studio

`acs <- read.csv(url("http://stat511.cwick.co.nz/homeworks/acs_or.csv"))`

Once this command is executed by pressing `Enter`, the dataset will be downloaded from the internet, read as a csv file and assigned to the variable name *acs*.
 ![Alt](https://github.com/nicklyz/R-Studio-Tutorial/raw/master/img/9120227.png)

The second way to import the data set into R Studio is to first download it onto you local computer and use the import dataset feature of R Studio. To perform this follow the steps below:

  1.  Click on the import dataset button in the top-right section under the environment tab. Select the file you want to import and then click open. The Import Dataset dialog will appear as shown below
![Alt](https://github.com/nicklyz/R-Studio-Tutorial/raw/master/img/479435_orig.png)
  2. After setting up the preferences of separator, name and other parameters, click on the Import button. The dataset will be imported in R Studio and assigned to the variable name as set before.

Any dataset can be viewed by executing
   `View(acs)`
where acs is the variable dataset is assigned to.

### 2. Transforming Data
Once you are done with importing the data in R Studio, you can use various transformation features of R to manipulate the data. Let's learn few of the basic data access techniques

To access a particular column, Ex. age_husband in our case:
  `acs$age_husband`

To access data as a vector:
  `acs[1,3]`

To run some queries on data, you can use the subset function of R. Let's say I want those rows from the dataset in which the age_husband is greater than age_wife. For this we 'll run the following command in console:

  `a <- subset(acs , age_husband > age_wife)`

The first parameter to the subset function is the 'dataframe' you want to apply that function to and the second parameter is the boolean condition that needs to be checked for each row to be included or not. So the above statement will return the set the rows in which the `age_husband` is greater than `age_wife` and assign those rows to `a`.

### 3. Getting Statistical Averages from data
Following functions can be used to calculate the averages of the dataset:

1. Mean of any column:  `mean(acs$age_husband)`
2. Median: `median(acs$age_husband)`
3. Quantile: `quantile(acs$age_wife)`
4. Variance: `var(acs$age_wife)`
5. Standard Deviation: `sd(acs$age_wife)`

 ![Alt](https://github.com/nicklyz/R-Studio-Tutorial/raw/master/img/7352427_orig.png)

You can also get the statistical summary of the dataset by just running on either a column or the complete dataset: `summary(acs)`

### 4. Plotting Data
A very liked feature of R studio is its built in data visualizer for R. Any data set imported in R can visualized using the plot and several other functions of R.

To create a scatter plot of a data set, you can run the following command in console:

  `plot(x = s$age_husband , y = s$age_wife, type = 'p')`

where s is the subset of the original dataset and type 'p' set the plot type as point. You can aslo choose line and other change type variable to 'L' etc.
 ![Alt](https://github.com/nicklyz/R-Studio-Tutorial/raw/master/img/8156790_orig.png)

For data distribution plots, there are several features tools and packages available in R that you can use to draw any kind of distribution. For example

To draw a Histogram of a dataset, you can run the command:

  `hist(acs$number_children)`

![Alt](https://github.com/nicklyz/R-Studio-Tutorial/raw/master/img/9670379_orig.png)

Similarly for Bar Plots, run the following set of commands:

  `counts <- table(acs$bedrooms)`

  `barplot(counts, main="Bedrooms Distribution",  xlab="Number of Bedrooms")`


![Alt](https://github.com/nicklyz/R-Studio-Tutorial/raw/master/img/6740688_orig.png)

I hope this will give you a basic idea on how to do simple statistics in R.

### Note
For any documentation or usage of the function in R Studio, just type the name of the function and then press cntrl+space to get the auto completion window.
You can use ? before any function name to view the official documentation.

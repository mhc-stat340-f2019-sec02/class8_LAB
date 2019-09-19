# class8_LAB


## Description

Data on driving incidents was collected for all 52 states in the United states.
This lab will explore whether or not state-level factors contribute to Car insurance premiums.
The original goal of this dataset was to determine which state had the worst drivers.

<p align="center">
  <img width="200" height="200" src="https://github.com/mhc-stat340-f2019-sec02/class8_LAB/blob/master/featured.jpeg">
</p>

## Organization
Instead of a private repo per student, we're going to work collaboratively in a single repository.
You can work by yourself or with another student in a team.

On the GitHub repository page for this lab, click "Fork" in the top right corner. This will create a copy of the lab repository in your own account. You will then clone this repository to RStudio. If you're working in a team, only one of you needs to fork the repository. Once you have cloned the repository, create a new .Rmd file with a name like "Lab02_teamname.Rmd", specific to your team. In that R Markdown file, complete the Lab Tasks and Discussion items outlined below. Then commit and push your work to GitHub. Your work will go to your forked version of the repository. Once you're ready, submit a pull request to merge your work back into the main class repository.

## Due date

You must submit your pull request by 2019-09-27 at 23:59:59.

## LAB tasks

* **read in the data set `data/bad-drivers.csv`**
  * Name your dataset, for example, `badDrivers <- read.csv("./data/bad-drivers.csv")`
  * (recommended) rename the columns to shorter nicknames
* **exploratory data analysis**
  * Create a draftsman plot showing all pairwise comparisons between columns in the data.
  * Present a brief description of trends you see in the data, and how they may influence fitting a model.
  * Plot the estimated distribution of _Percentage of Drivers Involved in Fatal Collisions who were speeding_ using a histogram.
	  * If you include the above covariate as an explanatory variable in your regression (part of the X), will the distribution impact your model fit?
* **regression analysis**
  * The target variable for our regression models is `Car Insurance Premiums (CIP)`, measured in dollars.
  * Pick a covariate you feel is most related to Car Insurance Premiums (I'll call this `M` for most related)
  * Fit a simple linear regression `(lm)` model that related **CIP** to **M** and save this model as `reg01`. 
  * Fit a multiple linear regression model `(lm)` that includes **M** and save this as `reg02`.
  * Fit a polynomial regression model `(lm)` relating **CIP** to **M** and save this as `reg03`.
  * Pick a model from REG01, REG02, and REG03. Plot **M** by **CIP**, and overlay the chosen model's fitted values.
  * Describe your model. Do all the variables significantly contribute to predicting **CIP**? Interpret the coefficients, their direction (positive or negative) and how they relate to **CIP**.
  * How does your multiple regression model compare the your simple linear regression, and how would communicate these results to an audience?  
  
* **Hold-out**
  * Randomly select, and remove, 10 states from the training set. Store these 10 states in a dataset called `holdOut` and remaining 41 states in a dataset called `training`.
     * `badDrivers[c(1,2,3),]` selects the first, second, and third observation from your dataset.
     *  Take a look at the `sample` command in **R**
  * Re-train REG01,REG02,REG03 on `training`
  * For REG01, 02, and 03, compute the mean-squared error (MSE) on `holdOut`
  * Which model would you select and why?
  
* **Cross-validation**
  * For REG01, REG02, REG03
    * Split your data into 5 training/testing sets (note, one dataset will have 11 observations)
	* Create an empty data.frame called `crossValResults` that has 3 columns (one for each model) and 5 rows (one for each test MSE)
    * Program a for loop that
	      * *trains* your model on 4 pieces of the data
		  * *tests*, or makes predictions, on the "held-out" dataset. 
		  * *computes* the MSE on the "held-out" dataset
		  * *stores* the test MSE in `crossValResults`. 
    * When completed, you should have computed 15 MSEs, 5 for every regression model stored as columns in a data frame.
    * Compute the CV error for your regression models, the MSE averaged over each test set.
	* How does the CV error compare to the hold-out error?
	* How does the Cross-validation MSE compare between your simple and multiple regression?
  
<!-- ## Brief Report -->

<!-- * Paragraph 1: Describe the dataset -->
<!-- * Paragraph 2: Describe the models you'll use to make predictions. -->
<!-- * Paragraph 3: Summarize the methods you'll use to decide which model is best. Make sure to define and describe the test metric (MSE) -->
<!-- * Paragraph 4:  -->







  

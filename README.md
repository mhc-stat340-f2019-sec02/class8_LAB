# class8_LAB


## Description

Data on driving incidents was collected for all 52 states in the United states.
This lab will explore whether or not state-level factors contribute to Car insurance premiums.
The original goal of this dataset was to determine which state had the worst drivers.

![insurance](https://github.com/mhc-stat340-f2019-sec02/class8_LAB/blob/master/featured.jpeg)

## LAB tasks

* read in the data set `data/bad-drivers.csv`
  * (recommended) rename the columns to shorter nicknames
* exploratory data analysis
  * present some pictures and a brief description of trends you see in the data, and how they may influence fitting a model.
  
* regression analysis
  * The target variable for our regression models is `Car Insurance Premiums ($)`
  * fit a simple linear regression model and save this model as `reg01`. 
  * fit a multiple linear regression model that includes the variable you used in your simple linear regression and save this as `reg02`.
* Cross-validation
  * **For both REG01 and REG02**
    * split your data into 4 training,testing sets
    * program a for loop that trains your model on 3 pieces of the data and tests on the "held-out" dataset. (This for loop should iterate over all 4 training, testing sets.)
    * compute the MSE for each test set
    * compute the MSE averaged over each test set
  
## Discussion

  Please explain your model, making sure to reference the coefficients of the model and their significance.
  
  How does your multiple regression model compare the your simple linear regression, and how would communicate these results to an audience? 
  
  How does the Cross-validation MSE compare between your simple and multiple regression?
  

# stock-analysis

## Overview of Project
Our friend Steve has asked us to help analyze some stocks for his parents. In the class module, we wrote a macro for the analysis of two years: 2017 and 2018. The analysis took raw data for 12 different companies and calculated their yearly total daily volume, and return. This project focused on refactoring that code to run more quickly, but achieve the same results.

## Results
To explain the results from refactoring the code, we must first explain the code from the class module.

### Class Module
After creating a subroutine to write our code, we started out declared some key variables. Since we want to know how long the code takes to run, we created variables to determine how long the program runs for. We also created an input box to prompt the user to enter the year for the analysis to run on (either 2017 or 2018). Our next step was to create headings for the compiled data to be listed under. Since all of the tickers were given in the data set, we also created an array for each ticker to live in. After we created the array, we began to loop through the tickers. After initializing variables like starting price, ending price, and row count, we began to loop through each ticker. This loop was on the outside since the data was sorted by ticker. We then added a nested loop inside the ticker loop. This loop is meant to loop through the rows themselved and calculate the total volume, starting price, and ending price. The data being sorted by ticker allowed us to do this in 3 seperate if statements. The idea of these if statements was rooted in the fact that the beginning price that corresponds with a given ticker would have a different ticker in the row above. Similarly, the ending price that corresponds with a given ticker would have a different ticker than the row below. Then for the rest of the rows in the middle we used those values to calculate total volume. Then we ended the loops and printed the ticker, total volume, and return to the All Stocks Analysis sheet. Lastly, we prompted a message box to show us how long the code ran for.

### Differences in Refactored Code
The code we refactored for the challenge assignment followed many of the same steps, albeit a few differences. The main difference was that instead of using a variable to store the total volume, starting prices, and ending prices, we used an array of size 12 where each index corresponded with the 12 tickers. We then moved the code that printed those values outside of the loop and into its own loop since we had all of the values stored in arrays. The previous code erased those values when moving to the next ticker so we had to print them inside the loop before the next iteration.

Below is a side by side of the base code (left) and the refactored code (right).

![beginning_of_code](https://user-images.githubusercontent.com/91795475/138580996-bfc34506-abc9-49c0-bd0d-8f88bad60234.PNG)

![end_of_code](https://user-images.githubusercontent.com/91795475/138580999-fe49da70-57d6-4c22-af25-e15d7c037e47.PNG)


## Stock Analysis

### 2017

### 2018


## Summary

[//]: # (advantages and disadvantages of refactoring code in general: more efficient, less run time, but takes time to refactor and may not necessarily make it better)

[//]: # (advantages and disadvantages of original and refactored script: able to recall all elements in array for refactored, quicker runtime in refactored. Took about 5 hours to run one second quicker)

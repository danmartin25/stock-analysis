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
Circling back to Steve's original question, what do the stocks look like? Each year returned very different results. In 2017, 11 out of 12 had a positive return. In 2018, only 2 out of 12 had a positive return. Out of all of the stocks, ENPH had the best net return over the 2 year span, and was one of only 2 companies with a positive return both years. Before investing solely off of return, Steve should look at the company more in depth and their outlook, but purely based off of the numbers ENPH is easily the best choice.

### 2017
Below is the data for 2017. We can also view the runtime from running the refactored code.
![VBA_Challenge_2017](https://user-images.githubusercontent.com/91795475/138581030-b2d6b7c0-d9b5-40ef-80f2-b0657e0176a5.PNG)

### 2018
Below is the data for 2018. We can also view the runtime from running the refactored code.
![VBA_Challenge_2018](https://user-images.githubusercontent.com/91795475/138581033-567e3bb5-99e2-44d9-b679-760166de8b30.PNG)



## Summary

[//]: # (advantages and disadvantages of refactoring code in general: more efficient, less run time, but takes time to refactor and may not necessarily make it better)

Refactoring code can be very beneficial to programmers. In addition to cutting down runtime, refactoring can help clean up code and make it easier to understand. Maybe code that was added later on has variables and values that would make the original code run faster. While there are many of these benefits, there are also a few drawbacks. Refactoring code takes time. For a program that already works, that may seem inefficient. One could refactor a program only to find out they cannot get it to run faster, or even worse, they get it to run slower. Refactoring is all about efficiency and there is definitely a scale where one side is a faster running program and the other side is time spent on the program.

In the case of our code, refactoring seemed more on the inefficient side. In the original code, the run times were 1.399 and 1.328 seconds for 2017 and 2018, respectfully. After we refactored the code the run times dropeed to 0.347 and 0.231 seconds for 2017 and 2018, respectfully. Due to the nature of the program being relatively short and simple, this difference is not much. In this scenario, I would argue the time lost spent refactoring was more valuable than the difference in runtime. However, if this code were to be built upon, then the refactoring would be valuable. If there were more years or companies this code could take a long time to run, and the difference in run time between the two methods would be much larger. Another advantage of the refactored code is that because we created an array for ticker volumes, we are now able to recall and use those values elsewhere in the code. In the first program if we were building upon the code and wanted to use a specific ticker's volume, we would not be able to within the script because the for loop kept overwriting the single variable we had for ticker volume. The refactored script had an array for each ticker volume so we could recall any specific volume if necessary.

[//]: # (advantages and disadvantages of original and refactored script: able to recall all elements in array for refactored, quicker runtime in refactored. Took about 5 hours to run one second quicker)

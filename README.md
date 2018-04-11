# zsq96512-PHBS_TQFML-Project
#1. Project description
#Bilateral exchange rate is changing every day, and can be affected by many factors. Instead of using the regression method to predict the specific value of the exchange rate, this project tries to use the daily variable data to predict the direction of the change of the exchange rate next period. However, we still working on how long the forecasting period we are going to choose.
We consider several possible theories such as interest parity theory, and some empirical result on exchange market, such as the momentum or reversal effect, the relationship between commodity price and exchange rate, the relationship between stock price index and exchange rate.
 
#2. output

#We choose three possible exchange rates as our output. JPY,GBP,EUR are the three major currency in the world. We need to try the all the possibility and decide which one we should finally choose.
USD/JPY

EUR/USD

GBP/USD

#Features:

#past (4 weeks;13 weeks;26 weeks;52 weeks;104 weeks) changes in exchange rates : to test whether momentum or reversal effects have influence on the changes in forecasting period exchange rate
#Lagged relative interest rate changes in different countries (1 day; 2 days; 3days; 1 week; 4 weeks): to test whether relative interest rate changes have impacts on forward exchange rate changes and influence next period exchange rate
#Stock price index in each country: eg. DJI, .IXIC, FTSE, N225, CAC40
#Commodity price index: XAU(USD)/ DTD/ WTI
#Actually we are not sure these features will give us the result well, we may try further possibility if we find proper data.


#3. Methods

#Since there are three directions, including going up, staying still or going down, this project will try KNN, SVM, random forest, OvR to choose the best one.

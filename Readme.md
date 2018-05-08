# Forcasting JPY/USD Exchange Rate

## Team Member
* Shiqi Zhang 1701213153
* Haoli Wan 1701213095

## 1.Background Introduction
* Structural models, using Macro factors to predict exchange rate, are easily beat by random walk model. <br>
* Time series models, such as ARMA,ARIMA,ARCH,GARCH were frequently used by predictors.<br>
* In recent years, ANN, SVM and chaos theory are widely used in predicit exchange rate.<br>


## 2.Motivation
Focused on the short-term voltility of the foreign exchange rate, this project apply the SVR method and the deep learning method ANN to predict the exchange rates of next 7 periods.

## 3.Goal
Our main goal is to use daily exchange rate data to forecast exchange rate in next seven days(2018.03.30-2018.04.10).In order to do this we first use grid search and moving windows from 3.13-3.30 (10 periods),to estimate the best parameters. to <br>
Main methods used to determine the length of prediction methods is `chaos theory` and `lyapunov exponents`. Using wolf methods and choosing parameters according to experience, we calculate `the maximum lyapunov exponents is L=0.1407` (data=JPY/USD(2016.01.04-2018.04.10),N=592,m=10,tau=60,P=15). The maximum lyapunov exponents is above zero which can prove that the exchange rate time series has chaotic characteristics. Also, 1/L=7.1073 means that the `maximum time scale that the series system can forecast is 7 days.`<br>
For we didn't find suitable code to calculate lyapunov exponents in python, we use [code](https://github.com/zsq96512/zsq96512-PHBS_TQFML-Project/tree/master/Lyapunov%20index%3B%20wolf%20methods) that can be conducted in MATLAB to calculate lyapunov exponents.


## 4.Datasource
This project collected the daily data of the exchange rate of JPY/USD (592 samples) from January 1st, 2016 to April 10th, 2018 in wind economics database. 

## 5.Work
### 5.1 [Data Preprocessing](https://github.com/zsq96512/zsq96512-PHBS_TQFML-Project/blob/master/Data%20Preprocessing.ipynb)
* Difference the data, draw the graph.<br>
### 5.2 [Support Vector Regression](https://github.com/zsq96512/zsq96512-PHBS_TQFML-Project/blob/master/SVR%20Method.ipynb)
* Belongs to support vector machine methods
* Using five lagged exchange rate as dependent variable.
* Three different kernels considered: linear, polynomial(poly), Radial Basis Function(rbf).<br>
* Five error index measure: Mean squared error(MSE), Mean absolute error(MAE), Root mean absolute error(RMSE), Mean absolute percentage error(MAPE), goodness of fit(U=1-MAPE).
* Grid search to find best parameters.<br>
### 5.3 [Artifial Neural Netork](https://github.com/zsq96512/zsq96512-PHBS_TQFML-Project/blob/master/Neural%20Network%20Method.ipynb)
* 5 lag terms as the input variables(586 samples) and the next 7 periods’ exchange rate as output variables.
* ANN: 2 layers and the numbers of neurons are [5, 4, 7].
* Apply the backpropagation algorithm to the neutal network, with the activation function to be tanh function.
* Grid search was used to find the optimal parameters, including learning rate and the numbers of neurons in the hidden layer, after the empirical formula gave the range of the numbers of neurons in the hidden layer, which is shown below.
![](picture/L.png)
* With the initial weight to be randomized, we tried lots of times and store the seed of best randomized initial weights.
* Evaluation index: MSE, MAE, RMSE, MAPE and U.

## 6.[Result & Analysis](https://github.com/zsq96512/zsq96512-PHBS_TQFML-Project/blob/master/Conclusion%20%26%20Analysis.ipynb)
* Support Vector Machines performs worse than Artifial Neutal Network. There are several explanations for this result.<br>
(1)Using grid search we didn't full check all the possible parameters.<br>
(2)The windows period we use to find parameters is not optimal.

* Future work of ANN:
(1)Increase the number of the hidden layer and their neurons;<br>
(2)Improve the method of iniial weights setting;<br>
(2)Apply a useful empirical formula.

## References

[1] Galeshchuk, S. (2016). Neural networks performance in exchange rate prediction. Neurocomputing, 172(C), 446-452.

[2] Ince, H., & Trafalis, T. B. (2007). A hybrid model for exchange rate prediction. Decision Support Systems, 42(2), 1054-1062.

[3] F. E. H. T., & Cao, L. (2007). Application of support vector machines in ÿnancial time series forecasting. Journal of University of Electronic Science & Technology of China, 48(1–4), 847-861.

[4] PaoloTenti. (1996). Forecasting foreign exchange rates using recurrent neural networks. Applied Artificial Intelligence, 10(6), 567-582.

[5] Nag, A. K., & Mitra, D. A. (2002). Forecasting daily foreign exchange rates using genetically optimized neural networks. Journal of Forecasting,21(7), 501-511.

[6] Zhang, G., & Hu, M. Y. (1998). Neural network forecasting of the british pound/us dollar exchange rate. Omega, 26(4), 495-506.

[7] Ni, H., & Yin, H. (2009). Exchange rate prediction using hybrid neural networks and trading indicators. Neurocomputing, 72(13), 2815-2823.

[8] Sermpinis, G., Dunis, C., Laws, J., & Stasinakis, C. (2012). Forecasting and trading the eur/usd exchange rate with stochastic neural network combination and time-varying leverage. Decision Support Systems,54(1), 316-329.

[9] Sermpinis, Georgios, Theofilatos, Konstantinos, Karathanasopoulos, & Andreas, et al. (2013). Forecasting foreign exchange rates with adaptive neural networks using;radial-basis functions and particle swarm optimization. European Journal of Operational Research, 225(3), 528-540.

[10] Rout, M., Majhi, B., Majhi, R., & Panda, G. (2014). Forecasting of currency exchange rates using an adaptive arma model with differential evolution based training. Journal of King Saud University - Computer and Information Sciences, 26(1), 7-18.

[11] Rehman, M., Khan, G. M., & Mahmud, S. A. (2014). Foreign currency exchange rates prediction using cgp and recurrent neural network ☆. Ieri Procedia, 10, 239-244.

[12] XIONG, Z. (2011). ARIMA ronghe shenjingwangluo de renminbi huilv yuce moxing yanjiu( Research on Renminbi Exchange Rate Forecasting Model Based on Artificial Neural Network). Quantitative Economic And Technical Economic Research, (6), 64-76.

[13] C, S. (2007). huilu yuce:yige xinde feicanshu zhichi xiangliang huigui fangfa( Exchange Rate Prediction: A New Nonparametric Support Vector Regression Method). Quantitative Economic And Technical Economic Research, 24(5), 142-150.

[14] X, C., & O, L. (2008). Huilv yuce de shenjing wangluo fangfa jiqi bijiao( Exchange Rate Prediction Neural Network Method and Comparison). Financial Science, (5), 47-53.

[15] X, C., H, X., & S, B. (2009). jiyu xiaobo fenxi yu zhichi xiangliangji de renminbi huilv yuce( Prediction of RMB Exchange Rate Based on Wavelet Analysis and Support Vector Machine). Journal Of Xiangtan University, 33(5), 82-87.

[16] W, M., & X, Q. (2007). zhichi xiangliangji zai jinrong shijian xulie yuce zhongde yingyong( Application of Support Vector Machine in Financial Time Series Prediction). Journal Of Electronic Science And Technology University(S1), 442-444.

[17] W, J., & M, Y. (2006). jiyu shenjing wangluo de huilv yuce( Neural Network Based Rate Prediction). Computer And Modernization, (2), 105-108.

[18] W, X., & W, H. (2006). yichuan suanfa he shenjing wangluo zai huilv yuce zhongde yingyong( Application of Genetic Algorithm and Neural Network in Exchange Rate Prediction）. In China Control and Decision Academic Conference.

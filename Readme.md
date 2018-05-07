# Forcasting JPY/USD Exchange Rate

## Team Member
* Shiqi Zhang 1701213153
* Haoli Wan 1701213095

## 1.Background Introduction
1.1 Structural models, using Macro factors to predict exchange rate, are usually easily beat by random walk model. <br>
1.2 Time series models, such as ARMA,ARIMA,ARCH,GARCH were frequently used by predictors in the past.


## 2.Motivation

## 3.Goal

## 4.Datasource

## 5.Work
### 5.1 Data Preprocessing
### 5.2 Support Vector Regression
### 5.3 Artifial Neutral Work[`code`](https://github.com/zsq96512/zsq96512-PHBS_TQFML-Project/blob/master/Neural%20Network%20Method.ipynb)
#### 5.3.1 Input and output variables
This project left out the variables of the last 7 periods as the test set, and the rest  was the training set, both the training set and test set were nomalized by the min_max method to fasten the training process.
#### 5.3.2 Construction oF ANN
This ANN model has 2 layers and the numbers of neurons are [5, 4, 7], since we have 5 lag terms as the input variables (586 samples), and we predict the next 7 periods’ exchange rate, which is our output variables (586 samples). And both the input and output variables are the fluctuations of the exchange rate. 

Besides, this project apply the backpropagation algorithm to the neutral network, with the activation function to be tanh function.

As for the parameter adjustment process, grid search was used to find the optimal learning rate and the optimal numbers of neurons in the hidden layer, after the empirical formula gave the range of the numbers of neurons in the hidden layer, which is shown below.
![](picture/L.png)

With the initial weight to be randomized, we tried lots of times and store the seed of best randomized initial weights.

### 5.3.3 Evaluation
To evaluate the performance of ANN method, this project selected several index including MSE, MAE, RMSE, MAPE , and we choose the MAPE as our target, and U is the accurancy. The result is shown below.


## 6.Result & Analysis

## References

Galeshchuk, S. (2016). Neural networks performance in exchange rate prediction. Neurocomputing, 172(C), 446-452.

Ince, H., & Trafalis, T. B. (2007). A hybrid model for exchange rate prediction. Decision Support Systems, 42(2), 1054-1062.

∗, F. E. H. T., & Cao, L. (2007). Application of support vector machines in ÿnancial time series forecasting. Journal of University of Electronic Science & Technology of China, 48(1–4), 847-861.

PaoloTenti. (1996). Forecasting foreign exchange rates using recurrent neural networks. Applied Artificial Intelligence, 10(6), 567-582.

Nag, A. K., & Mitra, D. A. (2002). Forecasting daily foreign exchange rates using genetically optimized neural networks. Journal of Forecasting,21(7), 501-511.

Zhang, G., & Hu, M. Y. (1998). Neural network forecasting of the british pound/us dollar exchange rate. Omega, 26(4), 495-506.

Ni, H., & Yin, H. (2009). Exchange rate prediction using hybrid neural networks and trading indicators. Neurocomputing, 72(13), 2815-2823.

Sermpinis, G., Dunis, C., Laws, J., & Stasinakis, C. (2012). Forecasting and trading the eur/usd exchange rate with stochastic neural network combination and time-varying leverage. Decision Support Systems,54(1), 316-329.

Sermpinis, Georgios, Theofilatos, Konstantinos, Karathanasopoulos, & Andreas, et al. (2013). Forecasting foreign exchange rates with adaptive neural networks using;radial-basis functions and particle swarm optimization. European Journal of Operational Research, 225(3), 528-540.

Rout, M., Majhi, B., Majhi, R., & Panda, G. (2014). Forecasting of currency exchange rates using an adaptive arma model with differential evolution based training. Journal of King Saud University - Computer and Information Sciences, 26(1), 7-18.

Rehman, M., Khan, G. M., & Mahmud, S. A. (2014). Foreign currency exchange rates prediction using cgp and recurrent neural network ☆. Ieri Procedia, 10, 239-244.

XIONG, Z. (2011). ARIMA ronghe shenjingwangluo de renminbi huilv yuce moxing yanjiu( Research on Renminbi Exchange Rate Forecasting Model Based on Artificial Neural Network). Quantitative Economic And Technical Economic Research, (6), 64-76.

C, S. (2007). huilu yuce:yige xinde feicanshu zhichi xiangliang huigui fangfa( Exchange Rate Prediction: A New Nonparametric Support Vector Regression Method). Quantitative Economic And Technical Economic Research, 24(5), 142-150.

X, C., & O, L. (2008). Huilv yuce de shenjing wangluo fangfa jiqi bijiao( Exchange Rate Prediction Neural Network Method and Comparison). Financial Science, (5), 47-53.

X, C., H, X., & S, B. (2009). jiyu xiaobo fenxi yu zhichi xiangliangji de renminbi huilv yuce( Prediction of RMB Exchange Rate Based on Wavelet Analysis and Support Vector Machine). Journal Of Xiangtan University, 33(5), 82-87.

W, M., & X, Q. (2007). zhichi xiangliangji zai jinrong shijian xulie yuce zhongde yingyong( Application of Support Vector Machine in Financial Time Series Prediction). Journal Of Electronic Science And Technology University(S1), 442-444.

W, J., & M, Y. (2006). jiyu shenjing wangluo de huilv yuce( Neural Network Based Rate Prediction). Computer And Modernization, (2), 105-108.

W, X., & W, H. (2006). yichuan suanfa he shenjing wangluo zai huilv yuce zhongde yingyong( Application of Genetic Algorithm and Neural Network in Exchange Rate Prediction）. In China Control and Decision Academic Conference.

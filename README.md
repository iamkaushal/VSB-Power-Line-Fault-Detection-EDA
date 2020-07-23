# VSB-Power-Line-Fault-Detection-EDA
Exploratory Data Analysis on VSB Power Line Fault Dectection Data 

## Overview  
This case study is based on the data set provided by VŠB - Technical University of Ostrava. The data set includes the partial discharge in signals acquired from the power lines with new meters designed at the ENET Centre at VSB.    
  
**Motivation:** Medium voltage overhead power lines run for hundreds of miles to supply power to the cities and these large distances make it quite expensive to manually inspect the lines for damage that doesn’t immediately lead to power outage, like tree branches hitting the lines or a flow in the insulator. These modes of damages lead to a phenomenon known as partial discharge. Partial discharges slowly damage the power line, so left unrepaired they will eventually lead to a power outage or start a fire.
Objective: Objective of this case study is to detect the patterns of partial discharge in signals acquired from these power lines with new meter designed at the ENET Centre at VSB and build Machine Learning Models to effectively classify the signal to continuously monitor the power lines for faults and inform the concerned authorities in case to any fault detected.   
  
**Impact:** The impact of a good Machine Learning classifier model can be really strong. It will reduce the maintenance cost of the power lines and reduce the cost of the power company. It will also make the detection more efficient and timely monitoring can reduce the recovery time very significantly and it will reduce the frequency of power outage which can be a big concern in big Metro cities. Also, it will be helpful in reducing the disasters like fires because of the power lines partial discharges.   
  
  
## First Cut Approach     
  
Clean the data by removing outliers, replacing null values using imputation techniques like replacing with the mean of the datapoint target value. For categorical variables replacing null value with a new category if there are many or just replace them with the most frequent occurring value of the target variable.   
  
Using various EDA techniques on the data set like, finding the correlation between the features. Removing highly correlated features. Plotting various graphs like scatter plots to visualize the outliers in the dataset. Plotting the distribution of the features of the dataset. Knowing the distributions of the dataset like Normal or Power Distribution can be really advantages for further processing of data.  Also using simple descriptive techniques like mean, median, mode, standard deviation of the dataset features to find the outliers. Using t-SNE plots to visualize the data points.    
  
Splitting the dataset into three parts, train, i.e used to train the models, cv that will be used to cross-validate the trained model, and test data to find the performance on the unknown data. Test data will be used only for the performance testing of the model and will be unknown to the model during the training and cross validation process. 
Preparing features for the model using various techniques. For categorical variables using techniques like BOW, W2V, avg-w2v, tfidf, tfidf-w2v, tfidf-avg-w2v, etc. And for numerical features just standardizing the features.    
  
Creating new features using feature engineering hacks like log features if we find the distribution of the dataset to be log-normal and using sinusoidal features or trigonometric features if the signal is found sinusoidal during EDA.   
  
Stacking all the features to prepare for the models. Using hstack or vstack if required.   
  
As the number of features are very large, reduce the features using by selecting the important feature using tree based models or SelectKBest Features implemented in sklearn, where k will be the hyperparameter that can be found by plotting the variance explained vs number of dimensions plot and then using technique like elbow method to find the number of dimensions that can explain about 90 percent of the variance.   
  
Training various models like K-NN, Logistic Regression, Random Forests, XGBoost for binary classification. Then using hyper-parameter tuning techniques like using plots between train and cross validation performance metrics and using RandomSearchCV or GridSearchCV implemented in sklearn to find the best parameters for the models.   
  
Analysing the performance metric, i.e. Matthews-correlation (official performance metric in the contest) and then find the performance of the test data.   
  
Using more Features like Fourier features and High pass and low pass signal filter features to improve the model accuracy further.   
Tabulating all the results using the pretty table library and writing the observations.   
  

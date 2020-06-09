# covid19-MY-analysis-MachineLearning
Full project on Machine Learning using Malaysia Covid-19 dataset<br/>
**Disclaimer:** This project for **learning** purpose only not for **research**

# Data Science Salary Estimator: Project Overview
This my second full personal project on data science that include several process which are data collection , data cleaning, make exploratory data analysis(EDA) and applying machine learning model to estimate case on several parameter

* Created a model that estimates covid-19 cases in Malaysia with result of Mean Absolute Error (MAE) ~14 cases
* Using Linear, Lasso, and Random Forest Regressors model and optimized them using GridsearchCV
* Additional model uses different kind method to find accuracy for train and test data. The result really disappointing because had low accuracy and some of the model are overfitting. The model that use are Logistic Regression, Random Forest, Ridge, Kneighbour and XGBoost

# Data Collection
Getting data from this GitHub repo: https://github.com/ynshung/covid-19-malaysia. The attribute that collected are:<br/>
<br/>
**General**
* Cases
* Discharged
* Death 
* ICU

**Cluster Cases**
* Person-Under-Investigation (PUI)
* Close-Contact
* Tabligh
* Surveillance
* Misi Bantuan Kemanusiaan dan Bencana (HADR)
* Import

**State Cases**
* Perlis
* Kedah
* Pulau Pinang
* Perak
* Selangor
* Negeri Sembilan
* Melaka
* Johor
* Pahang
* Terengganu
* Kelantan
* Sabah
* Sarawak
* WP Kuala Lumpur
* WP Putrajaya
* WP Labuan

## Data Cleaning
After collecting, I needed to clean it up so that it was usable for our model. I made the following changes:
* Merge the 3 separated data corresponding to the date occur and convert the NaN value to -1(no value) and '-' to 0(0 case)
* Since the data set are cumulative cases, I need to tweaked a bit the data set to the cases occur for each day for better analysis (EDA) and model building

# Exploratory Data Analysis (EDA)
Make data visulization to get easier understanding of the data and make descriptive analysis after that<br/>
Here the example of result:<br/>
<br/>
**Bot Plot**<br/>
<br/>
![alt text](https://github.com/Hafizuddin961/covid19-MY-analysis-MachineLearning/blob/master/example-result/bot-plot.png)
![alt text](https://github.com/Hafizuddin961/covid19-MY-analysis-MachineLearning/blob/master/example-result/bot-plot-icu.png)

**Correlation**<br/>
When near 1 means highly correlate while -ve means inversely proportional<br/>
<br/>
![alt text](https://github.com/Hafizuddin961/covid19-MY-analysis-MachineLearning/blob/master/example-result/corr.JPG)<br/>

**Heatmap of Correlation**<br/>
<br/>
![alt text](https://github.com/Hafizuddin961/covid19-MY-analysis-MachineLearning/blob/master/example-result/heatmap.png)

**Pivot Table based on Date**<br/>
<br/>
![alt text](https://github.com/Hafizuddin961/covid19-MY-analysis-MachineLearning/blob/master/example-result/pivot.JPG)


# Model Building & performance
Split the data into train and tests sets with a test size of 20%.
Tried 3 different models and evaluated them using Mean Absolute Error.
Also, tried 3 different models and evaluated them using different approach.

**Result:**

**Use Mean Absolute Error (MAE):**
*	**Random Forest** : MAE = 24.62
*	**Linear Regression**: MAE = 16.07
*	**Lasso Regression (alpha = 0.25)**: MAE = 11.24
* **Linear Regression + Random Forest** : MAE = 17.16

**Use different evaluation:**
* **Logistic Regression** : MAE = 21.58
* **Random Forest** : Train accuracy score = 1.0, Test accuracy score = 0.24
* **Ridge** : Train accuracy score = 0.19, Test accuracy score = 0.24
* **Kneighbour** : Train accuracy score = 0.21, Test accuracy score = 0.24
* **XGBoost** : RMSE = 55.258755

# Resources
Data set: https://github.com/ynshung/covid-19-malaysia


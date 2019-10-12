> Notes to the introduction to the data science world by UpLevel for the I am the Best Coder 2019 by shopee

# Overview of the data science process
Processing
Cleaning
Exploring data analysis
Models & algorithm

# Categories for data science projects
Competition - aiming for accuracies
Company job - business ask for outcomes and the data scientist creates the solution but doesn’t need to over-engineer the solution
Eg netflix didn’t engineer the winning algorithm
Inspirations from internet

# Getting data
Ranked from dirty to clean
1. Scraping
  * Scraping the HTML file
  * From bs4 import beautifulsoup
  * `Soup = beautifulSoup(data.text, “html.parser”)`
  * To capture div using class name
  * `Movie = soup.find_all(‘div’...)`
2. Company data
3. competition/ public sets
  * Kaggle
4. API

Import requests to call api
data.json() to see the data

# Exploring data
Using pandas, some of the functions that can be used
- `.describe()`
- `.value_counts()`
- `.isnull().sum()`
- `.head()`
> returns the first few rows of the data
`.dtypes()`
> to see the different types
`.get_dummies()`
> helps to automatically convert into one hot encoding for a data column

Use `df.columns.values()` or `value_counts()`

To see a range of data, something like `df[df['duration'] > 4000` can be used

## Finding outliers
A histogram can be used to visualise the data range

# Transformation
It is good to have your data in a normal distribution thus, you would need to do transformation. 

There are the different methods
1. log transformation like `np.log` (if there's 0 or `-inf`, try to +1 to test)
2. One Hot encoding from label encoding [(sauce)](https://medium.com/@michaeldelsole/what-is-one-hot-encoding-and-how-to-do-it-f0ae272f1179)
  * Good for logistic regression because you need to turn the data into columns. 
  
# Building models
## Splitting dataset
* To split your test and training set, the most common split is 80/20. 
* K-fold and then take the average of the performance (scikit-learn has a function for it)
* Algorithm cheat sheet by scikit-learn
![Algorithm cheat sheet by scikit-learn](https://scikit-learn.org/stable/_static/ml_map.png)
* there are 2 types of decision tree, one for classifier & one for regression problem
* Classifier != regression
* How each model works on different dataset
![How each model works on different dataset](https://www.dataquest.io/wp-content/uploads/2018/11/sciki-learn2.jpg)

# Accuracy of the model
## Metrics
* Accuracy
- RMSE
* Precision
- F1 Score
- ROC
- Recall
- Specificity

## Handling class imbalance
Scikit has a library to help to balance the dataset
![](https://miro.medium.com/max/4185/1*P93SeDGPGw0MhwvCcvVcXA.png)

# How to get more information and relationships
This is like feature engineering.

## Isolation
1. thresholding
> Eg if `t < 500` where t is time, it is categorised as normal.
2. special event designation
> eg if you know if it's national day, mark it out
3. splitting category into subcategories

## Feature representation
1. transforming time/date
2. numercial to categorical
> use one hot encoding
3. grouping sparse classes
4. creating dummy data

## mathemacial interaction
1. summation
2. difference
3. multiplication
4. division

## external data
1. geolocation
2. information extraction


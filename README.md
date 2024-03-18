# Machine learning introduction

## Task

We will practice with a problem from Kaggle.com. Guiding instructions, you will predict the price of an apartment rental listing based on the listing content like text description, photos, number of bedrooms, price, etc. The data comes from renthop.com, an apartment listing website. 

Follow instructions, answer questions and get your final score!

1. Introduction. Write your answers in the *Intro* part of your Notebook 
   1. To get started, please write 5 examples of ML methods application in life. What is the benefit of using machine learning methods in each of your examples? 
   2. Use classification of tasks in the introduction to decide what class you can assign for the tasks from the table above and for the 5 examples you provided. 
   3. Please think and suppose, what is the difference between multiclass and multilabel.
   4. Is an example case with housing prices from theory a classification of a regression problem? Is it possible to reduce the regression problem to classification?
2. Intro data analysis
   1. Import libraries **pandas**, **numpy**, **sklearn**, **lightgbm**, **scipy**, **statsmodels**, **matplotlib**, **seaborn**. Use **pip install** if it’s necessary
   2. Load data from [kaggle](https://www.kaggle.com/competitions/two-sigma-connect-rental-listing-inquiries/data) with **pandas**. You are need only table data and **train.json**
   3. What is the size of your data? 
   4. Print the list of columns. Which column is a target? 
   5. Make a fast analysis of the data: use methods **info()**, **describe()**, **corr()**. Explain the results of outputs. Are there any empty columns? 
   6. We’ll work only with 3 features: 'bathrooms',  'bedrooms', 'interest_level' and with target column ‘price’. Make a dataframe with these columns only.
3. Statistical data analysis
   1. To start with statistical data analysis we recommend you refresh basic knowledge of statistics, such as Mean / Median / Mode / Variance / Standard Deviation. Also you are welcome to be free with distributions (Discrete uniform Distribution, Bernoulli Distribution, Binomial Distribution, Poisson Distribution, Normal Distribution, Exponential Distribution). Please make sure that you know the definitions of outliers, percentiles, confidential intervals. The article will be later 
   2. Make a quick sense with [this article](https://towardsdatascience.com/how-to-compare-two-or-more-distributions-9b06ee4d30bf). Please take attention to such aspects as distributions and histograms, boxplot, outliers, kernel density function.
   3. Target analysis
      1. Plot a histogram to understand the distribution of the target. Is it all clear? 
      2. The next step is boxplot(). What can you say about target? Are there any outliers? 
      3. Drop rows which are out of the 1 and 99 percentile by the target column. 
      4. Plot a histogram for price again. Explain the result.
   4. Features analysis
      1. What is the type of column 'interest_level'? 
      2. Print the values of this column. How many items each value contains? 
      3. Decode these values. For example, you may replace each value to 0, 1 or 2.
      4. Plot histograms for features 'bathrooms',  'bedrooms'. Are there outliers?
   5. Complex analysis
      1. Plot a correlation matrix to understand correlation between features and target. Plot a heatmap plot for correlation matrix. Is there a correlation? 
      2. Use a scatter plot to visualize correlation between features and target. You should return 3 plots, where X axis it target, and Y axis is a feature.
4. Generate features
   1. This step is very wide. You may create all features you want. For example, you may add 3 new features, which are squared: 'bathrooms_squared’, 'bedrooms_squared’, ‘'interest_level_squared'. Plot a correlation matrix with new features. Are new features more correlated with target then basic features? 
   2. To train model here we will not use your new features. Remember this example and use it in Lecture 2. 
   3. Read this sklearn info about PolynomialFeatures: https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.PolynomialFeatures.html
   4. To use PolynomialFeatures we first need to split data to train and test samples. We already made it for you, please read the train and test data. 
   5. Initialize PolynomialFeatures() with the degree of 10. 
   6. Apply PolynomialFeatures() to fit and transform your train and test data.
5. Now you need to train 3 models: linear regression, decision tree and native model. We will use it as black boxes without deep understanding. 
   1. Result table. 
      1. Create two empty pandas DataFrames with columns ‘model’, ‘train’, ‘test’. Let’s the first be called result_MAE, and the second result_RMSE. We will fill these tables with results of models.
   2. Linear Regression 
      1. Initialize linear regression from **sklearn** without parameters. 
      2. Fit your model and make predict on train and test features. Save it as new columns in data 
      3. Calculate MAE (Mean Absolute Error) on train and test targets 
      4. Calculate RMSE (Root Mean Square Error) on train and test targets 
      5. Insert your metrics into tables *result_MAE* and *result_RMSE* with model name ‘linear_regression’
   3. Decision Tree
      1. Initialize decision tree regressor from sklearn with fixed random_state=42 
      2. Fit it on train features and train targe and make predict on train and test features. Save it as new column in data 
      3. Calculate MAE (Mean Absolute Error) on train and test targets 
      4. Calculate RMSE (Root Mean Square Error) on train and test targets 
      5. Insert your metrics into tables *result_MAE* and *result_RMSE* with model name ‘decision_tree’
   4. Native models
      1. Calculate mean and median of ‘price’ on train and test data and create a columns with these values 
      2. Calculate MAE on train and test targets between your target and calculated mean and median values 
      3. Calculate RMSE on train and test targets between your target and calculated mean and median values 
      4. Insert your metrics into tables result_MAE and result_RMSE with model names ‘native_mean’ and ‘native_median’
   5. Compare results 
      1. Print your final tables result_MAE and result_RMSE. 
      2. What is the best model?
   6. Additional
      1. You may practice with all data in your start dataset. Use and generate all features you want

### Submission

Save your code in python JupyterNotebook.




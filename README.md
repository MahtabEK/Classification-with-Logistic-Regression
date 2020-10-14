# Classification-with-Logistic-Regression
The Dataset: This dataset is originally from the National Institute of Diabetes and Digestive and Kidney Diseases. The objective of the dataset is to diagnostically predict whether or not a patient has diabetes, based on certain diagnostic measurements included in the dataset. Several constraints were placed on the selection of these instances from a larger database. In particular, all patients here are females at least 21 years old of Pima Indian heritage.  You can read more about the data and the variables here.

**Part 1:**

I read in the diabetes.csv dataset.


**Part 2:**

I Split the data into train and test holding out 50% of observations as the test set. Pass random_state=0 to train_test_split to ensure I get the same train and tests sets as the solution.


**Part 3:**

Here are some question for you:

- Does LogisticRegression use a penalty by default? If yes, what penalty? If it does, does this mean that LogisticRegression actually uses ridge regression or the LASSO as the default?

- What is the interpretation of the parmater C? How does it relate to the regularization strength  𝜆 ?

- If you want to use a regularization strengh of 2 (i.e.  𝜆=2 ), what value of C would you pass?

You can fine the answers to these questions in the jupyter notebook I provided: "Classification with Logistic Regression.ipynb"


**Part 4:**

Here, I create a pipeline for logistic regression (that is, the unpenalized version). I need to choose an alternative solver for LogisticRegression since the default solver does not support the no penalty option. So I used solver="newton-cg",

If you get a warning about convergence of coef_, try increasing the max_iter parameter. I used max_iter=10000 and it works fine.


**Part 5:**

I used my model to construct a confusion matrix by fitting and predicting on the training data. 
Here I specify my model's training accuracy, precision, and recall.


**Part 6:**

I estimate logistic regressions out of sample recall by using 5 fold cross validation.

Then, I create a new pipeline for either an l2 penalty in logistic regression or an l1 penalty. It should be noted that penalized models perform best when we scale the inputs. So I add StandardScaler() to my pipeline.

I used sklearn's GridSearchCV to search over the regulatization strength ranging from 0.01 to 10 in 25 evenly spaced increments for my model. I used recall as the metric for scoring.


**Part 7:**

Here, I print the cross validated recall for mt regularized model by accessing the best model's score by performing lasso_gscv.best_score_.


**Part 8:**

I prrint out the C parameter for the regualized model. 

Here are some questions for you:

- From this value what is the regularization strength  𝜆 ?

- Would you prefer a regularized model for this dataset? When might a regularized model make more sense?


**Part 9:**

LASSO and other penalized estimators make the assumption that the model is what we call sparse (that means, not every variable is actually related to the outcome). We can see which variables are more important than others by examining what is known as the coefficient paths.

Here are the steps to create the coefficient path:

1) Initialize an array of regularization strengths (typically going from something very small, maybe 0.1, to something very large, maybe 100.

2) For each regularization strength, fit your model. Keep track of the coefficients.

3) Plot the coefficient values against the log of the regularization strength.

Here, I construct the coefficient path for logistic regression with an l1 penalty.

You should note that you can determine which coefficient is most strongly related to the outcome be examining which coefficent reaches 0 last.

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



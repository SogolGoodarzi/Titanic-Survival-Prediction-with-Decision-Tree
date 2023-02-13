# Titanic-Survival-Prediction-with-Decision-Tree
By implementing the decision tree algorithm for the titanic dataset we can predict the number of surviving passengers.

### About the dataset
There are two .csv files. "titanic-train" contains the train data and "titanic-test" contains test data. When you look at the information in these files, you can come to the conclusion that there is no need to use all of the given info or features to do the predictions. For example, the name of the passenger can't be effective on the chance of his or her survival. So, we just need to use some of the given features in the training file. 

### Preprocessing
* First of all we have to eliminate the unimportant and ineffective features. You have to make a decision and choose which features to use to reach a better result. 

* The second point that we have to consider is changing the continuous values to discrete values. For example, for the values reported for age, I categorize the values into four classes: child, teenager, adult, and old and label the values from 0 to 3. Also, I do the same process for the feature "Fare". 

You can use the following link for the preprocessing of this dataset. 

https://deepnote.com/@alivasples/Titanic-Survival-Prediction-Decision-Tree-85456baf-8725-4718-b954-0876c3c6ba57

### Implementation:
First of all, we need a function to calculate Entropy (because we are using the ID3 algorithm). Another function is MaxIG which is for finding the maximum value among the calculated information gains. Then, a class is generated for creating the nodes or branches of the decision tree. In the function called DesicionTree, we do the predictions after finding the maximum information gain and label or classify each data into two categories: 'died' and 'survived'. Finally, we consider a recursive function to expand the tree and generate its leaves.

After categorizing all data, we can compare the predicted labels with the actual ones and report the accuracy of the model. 

### Problems of Decision Tree

**1. Unstable nature:** One of the limitations of decision trees is that they are largely unstable compared to other decision predictors. A small change in the data can result in a major change in the structure of the decision tree, which can convey a different result from what users will get in a normal event. 

**2. Less effective in predicting the outcome of a continuous variable:** Decision trees are less effective in making predictions when the main goal is to predict the outcome of a continuous variable. This is because decision trees tend to lose information when categorizing variables into multiple categories.

**3. Sensitivity to Noise:** Decision trees can be extremely sensitive to small perturbations in the data: a slight change can result in a drastically different tree. 

**4. Not useful for large datasets:** Decision tree algorithms are not ideal to use for large datasets. In this case, for numerous classes and not enough training data, the probability of error for this algorithm increases. 

**5. Complexity:** Sometimes in decision trees, it may take so long to do the operations and also we have to mention the complexity of operations. (For example, for entropy calculation it's needed to calculate the logarithm of numbers). Another reason for this complexity is that because the decisions made in tree nodes are limited to the binary outputs, this algorithm can't handle complicated operations. 

**6. Not useful for continuous data:** This method is not good enough for continuous values and we can see a lower performance if the dataset contains these kinds of value. So, for this reason, when data is being classified into different classes, some information may be lost in this process. 

### Suggesting Solutions
#### **1) Bagging**
Bagging (Bootstrap Aggregation) is used when our goal is to reduce the variance of a decision tree. By the use of variance we mean the noise that desicion tree is sensitive to. Here idea is to create several subsets of data from training sample chosen randomly with replacement. Now, each collection of subset data is used to train their decision trees. As a result, we end up with an ensemble of different models. Average of all the predictions from different trees are used which is more robust than a single decision tree. By considering B sets of train data we have:

![image](https://user-images.githubusercontent.com/125180530/218404213-4de5d956-4ddc-423e-a4e3-a4f402a0b98f.png)

#### **2) Random Forest**
Random Forest is an extension over bagging. It takes one extra step where in addition to taking the random subset of data, it also takes the random selection of features rather than using all features to grow trees. When you have many random trees. It’s called Random Forest. The steps that we have to take to implement Random forest are:

1. Suppose there are N observations and M features in training data set. First, a sample from training data set is taken randomly with replacement.

2. A subset of M features are selected randomly and whichever feature gives the best split is used to split the node iteratively.

3. The tree is grown to the largest.

4. Above steps are repeated and prediction is given based on the aggregation of predictions from n number of trees.

Advantages of using Random Forest technique include:

* Handling higher dimensionality data very well.

* Handling missing values and maintains accuracy for missing data.

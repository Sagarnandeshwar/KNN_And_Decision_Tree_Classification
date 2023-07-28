# KNN and Decision Tree Classification
In this project, we have implemented K-Nearest Neighbours and Decision Trees - on two Health related datasets: Hepatitis Data Set and Diabetic Retinopathy Debrecen Data Set Data Set.  
## KNN 
K-NN is a non-parametric method. The quality of the results depends on the distances measured between datapoints, how distinct the classes are, and the value of the hyper-parameter K which represent the number of the nearest neighbors. K-NN is a lazy learner which keeps the data in reserve until the input data’s class or the label is predicted, and does not train any internal parameters.We have used Euclidean and Manhattan method to calculate distance. 

## Decision Tree 
Decision trees are widely used in machine learning as they give interpretable results. The Decision Tree model builds a decision tree where the root and internal nodes represents the features of the data set. The leaf nodes represent the class labels. We used the greedy heuristic at each step to select the optimal split of each node based on the Misclassification, Entropy, and Gini Index cost functions. 

## Datasets 

### hepatitis.csv (Hepatitis) 
The Hepatitis dataset consists of 155 data points out of which, 23(20:6) DIE cases and 123(79:3) LIVE cases. There are a total of 20 attributes out of which, 19 can used for prediction and the Class feature is the labeled target. The hepatitis dataset has a mix of categorical and numerical features. There are six numerical features and thirteen categorical features. To render the dataset usable and without inventing data, we have removed the rows with missing values. Which resulted in a much smaller dataset with just 80 instances for model prediction. The features do not exhibit a high class correlation. 

### messidor features.arff (Retinopathy) 
The retinopathy dataset consists of 1151 data points with 20 attributes each, and no missing values. As with the hepatitis set, we have 19 features for prediction and 1 Class label as target, but many of the features here are unusable. The first, the binary result of quality assessment, is always 1 as only sufficient quality data points were added into the set. The models cannot be built on a constant feature. Additionally, the features 8-15 represent the same information as 2-7, but scaled differently, so there is a high correlation between the two. Equally, each group such as 8-15 are the number of MAs found at different levels of confidence, and tend to be correlated. 

## Result 
The primary objective of this exercise was to explore the application of two widely used classification methods K-Nearest Neighbors and Decision Tree to real world problems. The results show that the algorithms are able to achieve a high accuracy on both the datasets. We observed that the KNN dataset is sensitive to the scale of the features as the method depends on a distance measure to identify nearest neighbours. The features should be standardised pre-processing the data on KNN. As we increase the value of K, the model starts to generalize better, and we see an increase in test accuracy. Furthermore, we observed that both Euclidean and Manhattan distance measures give almost same results on both the datasets, which is likely due to the low dimensionality of the input. We have tried to increase the number of features used for classification but noticed no significant changes in performance while also breaking all secondary methods such as plotting. 

We can observe a similar pattern for Decision tree models. The decision tree model overfits the training data if we overincrease the depth of the tree. In certain instances, the test accuracy decreases with an increase in maximum depth. A comparison of the the application of different cost functions clearly show that the entropy and Gini Index cost functions achieve a hundred percent training accuracy faster than the misclassification cost. All three methods give comparable accuracy. 

For the Hepatitis dataset, we tried replacing the missing values with the mode of the columns for binary features and the means for continuous ones. However, that led to a lower accuracy compared to removing the missing values. This is possibly due to the skewing of data and is particularly noticeable due to the dataset’s small size. 

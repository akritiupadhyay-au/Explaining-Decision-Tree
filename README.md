# Explaining Decision Tree

Decision Tree is a CART model, means Classification and Regression tree. CART model works by recursive partitioning of data in resulting in a local region of defined model. Local region is depicted as a leaf of the decision tree where we have reached to the conclusion of partitioning of the data.
* To explain the CART approach, a function is used to define the region and the weights which specifies the response value in each region. That function is adaptive basis function. Like in a classification model, a threshold is set for each node to decide the next level in the set of (yes,no). 
* In Regression model, a regression cost is defined, linear regression model is fitted to each node using the inputs as features chosen from the root node and the residual error is then measured. The goal of the tree is here to minimize the residual error. 
* In Classification model, a classification model is defined and in order to maximize the accuracy of the model, there are several common errors caused during the evaluation of the proposed partition. 
1. Entropy or deviance -  It is the measure of the impurity or disorder in the node. It tells that how much a predicted value is deviated from the observed value of a feature. The optimality is reached by minimizing the entropy. The minimizaton of the entropy is equal to the maximization of the information gain. Information gain is the criteria which decides whether a feature is used for splitting the node. The feature which have the highest value of the information gain is used as a feature for splitting the node.
2. Gini Index - It measures the probability for a random instance being misclassified when chosen randomly. Alternatively, it measures the probability of misclassification rate for every feature. It chooses that feature to split the node whose probability of misclassification rate is minimum.
* Difference between gini index and entropy - Gini index and entropy, both are used for splitting the node. But, here are some major differences:
1. Gini index is calculated in the range [0,0.5], while entropy is calculated in the range [0,1].
2. Entropy is calculated on the basis of logarithms of base 2, while gini index is calculated by subtracting the sum of the squares of the probability of misclassification rate from 1.
3. Gini index has more clarity in understanding the tree and always predict more accurate than entropy.

## Overfitting
* The major limitation of using Decision Tree is overfitting which led due to data fragmentation, which means that after allowing multi-way splits, too little data fall in each subtree.
* To prevent overfitting, we can stop growing the tree by pruning. Pruning is done by growing the full tree and then pruning the branches which gives the least increase in error. To determine the pruning level, evaluation is done by cross validating error on each subtree and pick the tree whose CV error is within 1 standard error of the minimum. This way a simple tree is made by the point with minimum CV error.

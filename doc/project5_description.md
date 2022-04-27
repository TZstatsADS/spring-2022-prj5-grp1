# Project 5: Tree Classifiers (Decision Tree, Random Forest, HistGradient Boosting, XGBoosting)

Term: Spring 2022

+ Group 1
+ Rishav Agarwal (ra3141)

Goal: The goal is to predict wins based on in-match performace of multiple players and to understand which features may act as the deciding factors in determining the wins. The dataset used can be found [here.](data)

Decision Tree: (Reference: https://www.analyticsvidhya.com/blog/2021/08/decision-tree-algorithm/)

They are Supervised Machine Learning algorithms which can be used for classifications and Regression Problems. The name itself suggests that it uses a flowchart like a tree structure to show the predictions that result from a series of feature-based splits. It starts with a root node and ends with a decision made by leaves. It is basically a set of if-else statement created on the basis of the training data. When a new data points enters the tree, the tree checks and then parses it through either the left subtree or the right subtree.

[Decision_Tree](example_figures/Decision_Tree.jpeg)

Decision Tree is prone to Overfitting and one of the techniques to reduce that is the Minimal Cost-Complexity Pruning. 

This algorithm is parameterized by α(≥0) known as the complexity parameter.

The complexity parameter is used to define the cost-complexity measure, Rα(T) of a given tree T: 
Rα(T)=R(T)+α|T|

Basically, we get the alpha values for each subtree and then pass those as a hyper-parameter when initalizing a Decision Tree object. Based on this, we can calaculate the accuracy for each pruning and then decided on the one which acts as the best. 

Random Forest: (Reference: https://towardsdatascience.com/understanding-random-forest-58381e0602d2#:~:text=The%20random%20forest%20is%20a,that%20of%20any%20individual%20tree.)

Random Forest is an algorithm that acts as an ensemble of Decision Tree (a collection of Decision Trees). Each of the trees in this Random Forest provides a class, then the algorithm predicts the final class based on majority voting (that is the class that is predicted the most number of times).

[Random_Forest](example_figures/Random_Forest.png)

The best part about this algorithm is that it is protected from a lot of errors as each trees in the algorithm works as its own. The two parameters that is important to this are:
1) n_estimators: This signifies the number of trees that we want to build before we calculate the prediction. Greater the number of trees, better is the performance of the Random Forest.
2) max_depth: This represents the depth of each of the tree in the decision tree. The greater the depth, the greater is the number of split which means the information captured by the tree is more, making the accuracy even better.

Boosting: (Reference: https://machinelearningmastery.com/gentle-introduction-gradient-boosting-algorithm-machine-learning/)


Boosting is part of ensemble technique that uses the tree models to perform classifications and regressions. Unlike Random Forest, here the output of one tree feeds into another tree. If a sample is misclassified by one of the trees then the next tree focuses on that, that is, it tries to minimize the loss function at every instance. 
Gradient Boosting is one of the most common and famous algorithm for this type of computation, and it is the generalization of the AdaBoost Technique. But in practice, it is a very slow model, as trees are created and then added sequentially. 

[Boosting](example_figures/GB.png)


So, we bring about two techniques stemming from Gradient Boosting.

1) Histogram Gradient Boosting (HistGradient Boosting): 
As Boosting is highly dependant on the construction of the Decision Trees and those taking time, this method aims to make that process faster. It creates binning of values into fixed number of buckets (Histogram), thus, reducing the number of unique values significantly. 

2) eXtreme Gradient Boosting (XGBoosting): Another implementation of the Gradient Boosting which aims to speed up the entire process. It is just a more optimized version of HistGradient Boosting and thus is an industry-favourite. 

Project Description:
In this project, using the above mentioned dataset and the 4 different classifiers, we predict the chances of a player winning the game. The conclusion also gives reasoning as to which features are important when it comes to deciding the reason for a player's win. 

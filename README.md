# FRUIT_CLASSIFICATION
At the moment of this work (8/12/2021) this dataset contains 103 class of different fruits and 53177 total images. My idea is to perform different classification algorithms, in particular SVM, K-NN, Decision Tree, firstly for a binary classification task, then for a multi-class one. I'll also apply Principal Component Analysis in order to reduce the dimensionality of the dataset, see the variance of each class and then I'll try to apply classification algorithm having only two dimension. At the end I'll make a comparison between all methods in order to find which of them perform better on this dataset.

In the future I'd like to implement a CNN, out of the purpose of this work, that almost surely will be a solution better than others in terms of accuracy, but for the moment I limit myself to the mentioned algorithms.

# Fruits-360: A dataset of images containing fruits
A high-quality, dataset of images containing fruits.The following fruits 
Apples (different varieties: Crimson Snow, Golden, Golden-Red, Granny Smith, Pink Lady, Red, Red Delicious), Apricot, Avocado, Avocado ripe, Banana (Yellow, Red, Lady Finger), Beetroot Red, Blueberry, Cactus fruit, Cantaloupe (2 varieties), Carambula, Cherry (different varieties, Rainier), Cherry Wax (Yellow, Red, Black), Chestnut, Clementine, Cocos, Dates, Ginger Root, Granadilla, Grape (Blue, Pink, White (different varieties)), Grapefruit (Pink, White), Guava, Hazelnut, Huckleberry, Kiwi, Kaki, Kohlrabi, Kumsquats, Lemon (normal, Meyer), Lime, Lychee, Mandarine, Mango (Green, Red), Mangostan, Maracuja, Melon Piel de Sapo, Mulberry, Nectarine (Regular, Flat), Nut (Forest, Pecan), Onion (Red, White), Orange, Papaya, Passion fruit, Peach (different varieties), Pepino, Pear (different varieties, Abate, Forelle, Kaiser, Monster, Red, Williams), Pepper (Red, Green, Yellow), Physalis (normal, with Husk), Pineapple (normal, Mini), Pitahaya Red, Plum (different varieties), Pomegranate, Pomelo Sweetie, Potato (Red, Sweet, White), Quince, Rambutan, Raspberry, Redcurrant, Salak, Strawberry (normal, Wedge), Tamarillo, Tangelo, Tomato (different varieties, Maroon, Cherry Red, Yellow), Walnut.

# Dataset properties
Total number of images: 80653.

Training set size: 60318 images (one fruit or vegetable per image).

Test set size: 20232 images (one fruit or vegetable per image).

Multi-fruits set size: 103 images (more than one fruit (or fruit class) per image)

Image size: 100x100 pixels.
Filename format: imageindex100.jpg (e.g. 32100.jpg) or rimageindex100.jpg (e.g. r32100.jpg) or r2imageindex100.jpg or r3imageindex100.jpg. "r" stands for rotated fruit. "r2" means that the fruit was rotated around the 3rd axis. "100" comes from image size (100x100 pixels).

Different varieties of the same fruit (apple for instance) are stored as belonging to different classes.

# Repository structure
Folders Training and Test contain all images used for training and testing.

Folder test-multiple_fruits contains images with multiple fruits. Some of them are partially covered by other fruits. Also, they were captured in different lighting conditions compared to the fruits from Training and Test folder. This is an excelent test for real-world detection.


# K-NEAREST NEIGHBOR
K-NN is a supervised learning method that considers the K closest training examples to the point of interest for predicting its class. The point is assigned to the class that is closest.
Could be applied different distance metrics such as: Euclidian, Weighted, Gaussian, etc. Steps are pretty easy:

 Receive an unclassified data

Measure the distance with choosen metrics from the new data to all others data that are already classified.

 Gets the K smaller distances

 Check the list of classes that had the shortest distance and count the amount of each class that appears

Takes as correct class the class that appeared the most times

Classifies the new data with the class that you took in previous step

# DECISION TREE
In a decision tree each intermediate node of the tree contains splitting attributes used to build different paths, while leaves contains class labels.

There are differt algorithms to build a decision tree, all are made with a greedy approach, optimal locally.
The most famous is Hunt's algoritm.
<img src="https://cdn-images-1.medium.com/max/880/0*QctkHiOX2G2pvfD_.jpg">
Strarting from an empty tree, we need to find iteratively best attribute on which split the data locally at each step. If a subset contains records that belongs to the same class then the leaf containing such class label is created, otherwise if a subset is empty is assigned to default to mayor class.

Critical points of decision trees are test condition, the selection of the best attribute and the splitting condition. For the selection of the best attribute is generally choosen the attribute that generate homogeneus nodes. There are different metrics in order to find the best splitting homogenity, the most common are:

GINI IMPURITY INDEX: Given $n$ classes and $p_i$ the fraction of items of class $i$ in a subset p, for $i$∈{1,2,...,n}. Then the GINI index is defined as: $$ GINI = 1 − \sum_{i=1}^n p_i^2 $$

INFORMATION GAIN RATIO: The information gain is based on the decrease of entropy after a data-set is split on an attribute. Constructing a decision tree is all about finding attribute that returns the highest information gain (i.e., the most homogeneous branches).
Entropy is defined as $H(i) = -\sum_{i=1}^n p_i\log_2 p_i $.
Entropy is defined as $H(i) = -\sum_{i=1}^n p_i\log_2 p_i $.
So then Information gain is defined as:

$$ IG = H(p) - H(p,i) = H(p) - \sum_{i=1}^n \frac{n_i}{n} H(i) $$
where p is the parent node. Advantages of Decision Trees are velocity, easy to interpretate and good accuracy, but they could be affected by missing values.
# MODEL EVALUATION
In order to find the most suitable algorithm to this dataset, different evaluation methods will be presented: Accuracy, Confusion Matrix, ROC Curve.
Given:

TP = #samples for which the prediction is Fruit1 and the true label is Fruit1
FP = #samples for which the prediction is Fruit2 but the true label is Fruit1
TN = #samples for which the prediction is Fruit2 and the true label is Fruit2
FN = #samples for which the prediction is Fruit1 but the true label is Fruit2
We can define:

ACCURACY: $\frac{TP+TN}{TP+FP+TN+FN}$ that is the percentage of samples classified correctly.

CONFUSION MATRIX: A simple table with previous values used to show performance of a classifier

ROC CURVE: Area Under the Receiver Operating Characteristic curve (AUC)
To introduce this concept, we define the following two metrics:

  1.True positive rate (TPR): TPR = recall = $\frac{TP}{FN+TP}$


  2.False positive rate (FPR): FPR = $\frac{FP}{TN+FP}$

In order to plot the Receiver Operating Characteristic (ROC) curve we need to compute TPR and FPR and choose a number of thresholds for the classification (AUG). Area under the ROC curve, performed plotting TPR and FPR is used as evaluation matrics for the different classifiers

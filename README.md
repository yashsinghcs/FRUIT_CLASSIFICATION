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



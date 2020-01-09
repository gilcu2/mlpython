# Tunning hiper parameters

## Hold-out

1. Shuffle data
1. separate train in training and validation
1. check loss and accurate with different shuffles, if are different data is to small, pass to cross validation
1. optimize loss and accuracy against the hiper-parameters

## Cross validation

1. Divide training in k parts
1. Iterate using k-1 parts for training and the other for validation
1. Optimize using the average of the results

## Iterated cross validation

1. Multiple fold validations with shuffling before each one
1. Optimize using the average of the cross validation

# Data preparation for tunning hiper parameters
* Assure representativity (shuffling help) and no repetitions
* Carefull with temporal data and shuffling, dont loss time order
* Training and validation sets disjoint

# Data preprocessing

* One hot encoding for categories
* Feature normalization, each feature media 0 and standard deviation 1 (x -= x.mean(axis=0);x /= x.std(axis=0))

# Avoid overfitting
* More training data
* Reduce capacity: Less and smaller layers
* Weight regularization: Add a cost to loss depending of the value of the network weights
  * L1: Absolute value
  * L2: Square
  
# Quality measures

* Balanced-classes: Accuracy
* Imbalanced: Precision and recall
* Ranking problems or multilabel classification: Average precision

# Last layer and loss function

|Problem type                           |Last-layer activation  |Loss function              |
|---------------------------------------|-----------------------|---------------------------|
|Binary classification                  |sigmoid                |binary_crossentropy        |
|Multiclass, single-label               |classification softmax |categorical_crossentropy   |
|Multiclass, multilabel classification  |sigmoid                |binary_crossentropy        |
|Regression to arbitrary values         |None                   |mse                        |
|Regression to values between 0 and 1   |sigmoid                |mse or binary_crossentropy |




# Random Forest

<img src="https://i.stack.imgur.com/iY55n.jpg" style="zoom:80%; background-color:white">

Train a group of Decision Tree classifiers (generally via the bagging method (or sometimes pasting)), each on a different random subset of the training set


To make predictions, just obtain the preditions of all individual trees, then predict the class that gets the **most** votes.

## Why is Random Forest good?

The Random Forest algorithm **introduces extra randomness** when growing trees; instead of searching for the very best feature when splitting a node, it searches for the best feature among a random subset of features. **This results in a greater tree diversity, which (once again) trades a higher bias for a lower variance, generally yielding an overall better model.** 👏
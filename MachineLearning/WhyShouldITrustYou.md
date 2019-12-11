## Why Should I Trust You - Explaining the Predictions of Any Classifier

U. of Washington, by Marco Tulio Ribeiro, Sameer Singh, and Carlos Guestrin

This paper generalizes explanations of a variety, perhaps any, classifier.  The
essential idea is the model (to be explained) is sampled to provide predictions
and weights how close the instance that is being explained to what samples
were used.  This means that this is always a local explanation.

#### Algorithms

The paper presents two algorithms:

LIME - an algorithm that can be explain the predictions of any classifier, via
approximations with a interpretable model.

SP-LIME - a method that selects a set of representative instances with explanations
to address the "tursting the model" problem.

#### Explanations

Text Classification via SVM.  This was a simple classifier to differentiate whether
a message could be classified as "Christian" or "Atheist"  They discovered problems
with the dataset...  Some of the issues with the dataset were discovered by
poor explanations.

Deep Networks for Images.  Sparse linear explanations, used to explain the prediction
of Google's pre-trained Inception.  Here the explanations helped the user "trust"
the predictions.

#### Of Note

This is a classic paper showing how explanations can be used in the negative.  One
example cited is a classifier to determine whether a wolf is present in a picture
or not.  The human subjects were able to reject the classifier by explanations
of whether or not the image had snow in it.  In other words, secondary image
characteristics, that aren't relevant, were part of the decision making process
and once "explained" as a hueristic, the consumer was able to disregard the
prediction.


#### Code

The github code can be located here:
https://github.com/marcotcr/lime-experiments
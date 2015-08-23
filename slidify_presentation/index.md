---
title       : Application to explore Iris dataset
subtitle    : 
author      : 
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## 1: What is Iris dataset

The Iris Dataset is a canonical dataset for exploring machine learning in.
This data sets consists of 3 different types of irises' (Setosa, Versicolour, and Virginica) and the features that can be used to classify the instances of iris. Four features are available: Sepal Length, Sepal Width, Petal Length and Petal Width.

The shiny application https://pnbddp.shinyapps.io/project allows user to play to explore this dataset and try 4 different classifiers. 

Next slides are going to explain each part of the applicaiton in detail 
--- .class #id 

## 2: The UI

The UI of the app has left and right panel
* Lefft panel provides menu selection. This section is itself split into two - one that allows to play with features, and another that allows to select different machine learning models
* Right panel shows the plots and the result of evaluating different machine learning models.

--- .class #id 

## 3: Feature selection
User can choose to explore the connection between the features available and classes (labels) of flowers. To do so, user can choose features to be plotted on x and y axis, and the color of the points is going to represent the type of the Species. By choosing different features, user can explore which features help to clearly separate different Species (and thus might be useful for the classifiers), and overall get the feel of the data available


--- .class #id 

## 4: Trying different classifiers
4 classifiers are available to the user
* Naive bayes
* Multinomial logistic regression (maxent)
* Svm with linear kernel
* Random forest
When user chooses the classifier, we perform 5 fold cross validation for on the iris dataset and report back the confusion matrix for the selected classifier. This way users can compare generalization performance of different classifiers and choose the best classifier.

--- .class #id

## 5: Example of the classifier output
As you can see, user is presented with confusion matrix for Naive Bayes classifier, that shows that the model confused 3 instances of virginica and versicolor

```
##             Reference
## Prediction   setosa versicolor virginica
##   setosa         50          0         0
##   versicolor      0         47         3
##   virginica       0          3        47
```
Additionally user will be able to see overall generalization accuracy (96%) of the classifier and additional model info

```
##       Accuracy          Kappa  AccuracyLower  AccuracyUpper   AccuracyNull 
##   9.600000e-01   9.400000e-01   9.149722e-01   9.851815e-01   3.333333e-01 
## AccuracyPValue  McnemarPValue 
##   2.525127e-60            NaN
```



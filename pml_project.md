Practical Machine Learning: Prediction Assignment Writeup
========================================================

**Data analysis involved following:-**  
- Read paper: <a href="http://groupware.les.inf.puc-rio.br/public/papers/2013.Velloso.QAR-WLE.pdf">Qualitative Activity Recognition of Weight Lifting Exercises</a>
- Original authors used 17 features. They were analyzed using rpart and rf
- It was concluded that the train and test data was created by splitting original data
- Based on above it was easy to limit the predictors to following 3:-
    - raw_timestamp_part_1
    - new_window
    - num_window
- Because of this simplification, the **accuracy** was: **99.95%**

**Algorithm used**  
- Read data
- Clean data
- Partition data in training and validation set
- Use **random forest** to train the model
- Analyze the accuracy on training data
- Analyze the accuracy on validation data
- Read test data
- Clean test data
- Predict on test data


<h4>Run algorithm</h4>

```r
test_pred <- run_algorithm()
```

```
## Loading required package: randomForest
## randomForest 4.6-7
## Type rfNews() to see new features/changes/bug fixes.
```

```
## note: only 2 unique complexity parameters in default grid. Truncating the grid to 2 .
```

<h4>Prediction on validation data</h4>

```
##           Reference
## Prediction    A    B    C    D    E
##          A 1116    0    0    0    0
##          B    0  759    2    0    0
##          C    0    0  682    0    0
##          D    0    0    0  643    0
##          E    0    0    0    0  721
```

<h4>Accuracy of algorithm: 99.95 %</h4>

<h4>Error rates: Overall</h4>

```
##       Accuracy          Kappa  AccuracyLower  AccuracyUpper   AccuracyNull 
##         0.9995         0.9994         0.9982         0.9999         0.2845 
## AccuracyPValue  McnemarPValue 
##         0.0000            NaN
```

<h4>Error rates: By each class</h4>

```
##          Sensitivity Specificity Pos Pred Value Neg Pred Value Prevalence
## Class: A      1.0000      1.0000         1.0000         1.0000     0.2845
## Class: B      1.0000      0.9994         0.9974         1.0000     0.1935
## Class: C      0.9971      1.0000         1.0000         0.9994     0.1744
## Class: D      1.0000      1.0000         1.0000         1.0000     0.1639
## Class: E      1.0000      1.0000         1.0000         1.0000     0.1838
##          Detection Rate Detection Prevalence Balanced Accuracy
## Class: A         0.2845               0.2845            1.0000
## Class: B         0.1935               0.1940            0.9997
## Class: C         0.1738               0.1738            0.9985
## Class: D         0.1639               0.1639            1.0000
## Class: E         0.1838               0.1838            1.0000
```

<h4>Final prediction on test data</h4>

```
## test_pred
## A B C D E 
## 7 8 1 1 3
```

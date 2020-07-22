Response for July 21

A. 1. We split the labels from the data by using .pop. The names of the labels datasets are train_y and test_y.

A. 

2.1 
```
classifier=tf.estimator.DNNClassifier(
    hidden_units, feature_columns, model_dir=None, n_classes=2, weight_column=None,
    label_vocabulary=None, optimizer='Adagrad', activation_fn=tf.nn.relu,
    dropout=None, config=None, warm_start_from=None,
    loss_reduction=losses_utils.ReductionV2.SUM_OVER_BATCH_SIZE, batch_norm=False
)
```
   2.2 
```
regressor=tf.estimator.LinearRegressor(
    feature_columns, model_dir=None, label_dimension=1, weight_column=None,
    optimizer='Ftrl', config=None, warm_start_from=None,
    loss_reduction=losses_utils.ReductionV2.SUM_OVER_BATCH_SIZE,
    sparse_combiner='sum'
)
```
   2.3 
```  
classifier=tf.estimator.DNNLinearCombinedClassifier(
    model_dir=None, linear_feature_columns=None, linear_optimizer='Ftrl',
    dnn_feature_columns=None, dnn_optimizer='Adagrad', dnn_hidden_units=None,
    dnn_activation_fn=tf.nn.relu, dnn_dropout=None, n_classes=2, weight_column=None,
    label_vocabulary=None, config=None, warm_start_from=None,
    loss_reduction=losses_utils.ReductionV2.SUM_OVER_BATCH_SIZE, batch_norm=False,
    linear_sparse_combiner='sum'
)
```
   2.4 
```
regressor=tf.estimator.DNNLinearCombinedRegressor(
    model_dir=None, linear_feature_columns=None, linear_optimizer='Ftrl',
    dnn_feature_columns=None, dnn_optimizer='Adagrad', dnn_hidden_units=None,
    dnn_activation_fn=tf.nn.relu, dnn_dropout=None, label_dimension=1,
    weight_column=None, config=None, warm_start_from=None,
    loss_reduction=losses_utils.ReductionV2.SUM_OVER_BATCH_SIZE, batch_norm=False,
    linear_sparse_combiner='sum'
)
```
   2.5 
```
classifier=tf.estimator.LinearClassifier(
    feature_columns, model_dir=None, n_classes=2, weight_column=None,
    label_vocabulary=None, optimizer='Ftrl', config=None, warm_start_from=None,
    loss_reduction=losses_utils.ReductionV2.SUM_OVER_BATCH_SIZE,
    sparse_combiner='sum'
)
``` 
A. 3. The input function determines how data is converted to a Tensorflow dataset. The feature columns describe how the model should use the input data.

A. 4. The classifier.train() command trains the classifier model. It takes the input function we made earlier and the steps argument (which basically specifies the number of training steps) to do so. The classifier is our DNNClassifier that uses the feature columns we defined.

A. 5. The DNNClassifier got an accuracy of .9 for the test set. The DNNLinearCombinedClassifier (when I specified dnn_feature_columns and dnn_hidden_units) got .867 test accuracy. Finally, the LinearClassifier got .967, making it the most accurate, which I found to be surprising.

B


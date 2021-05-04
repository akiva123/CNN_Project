# CNN Project

This project classifies whether pneumonia is present in lungs. While doctors are successful at reading lung x-rays for pneumonia, an algorithm can be just as useful for determining the illness. This project uses convolutional neural networks to determine whether images of lungs have pneumonia in them.
The Anova p-value of 0 confirmed that the images do come from different distributions, and therefore, that the images are distinguishable from eachother.  
A convolutional neural network (CNN) has an input, output, and multiple hidden layers. The hidden layers have a series of convolutional layers that produce the dot product of filter weights and pixel matrices. A filter is used to dimentionally reduce an image to find high frequency parts of the image. Kernel size specifies the dimensions of the filter. An activation function determines neuron weight from one layer to the next. The convolutional layer is followed by a pooling layer, which uses a filter to reduce the dimensions of the convoluted result into fewer parameters.  
This model begins with convolutional layers of 64 filters with a kernel size of 3, 128 filters with a kernel size of 3, and then 256 filters with a kernel size of 3. The activation function used for this model is ReLU followed by Sigmoid for binary output. The model has pooling layers with a filter size of 2.
The Loss value implies how poorly the model is after each iteration of optimization. Loss increases as the predicted probability diverges from the actual label. The optimizer alters the model weights and learning rate to reduce the loss. SGD calculates which way the weights should be altered so that the function can reach a minima. Accuracy is the ratio of true occurences to true and false occurences. Precision is the ratio of true positives to all positives. Recall is the ratio of true positives to all actual true values. F1 is the harmonic mean of precision and recall.  Reciever operatic charachteristic (roc) is the true positive to false positive rate.  Cross validation (cv) is a resampling method that evaluates a model by splitting the data into k folds and both trainig and testing on each fold.
The model loss is 0.0678, accuracy is 0.9511, precision is 0.9640, recall is 0.9712, f1 is 0.9665, val loss is 0.4735, val accuracy is 0.7500, val precision is 0.6667, val recall is 1.0000, and val f1 is 0.8000.  The model correctly classified 1201 instances as false and 3799 instances as true.  The model incorrectly classified 76 instances as false and 140 instances as true.  The model roc score is 0.9380 and cv score is 0.9600.  
Regularization modifies the learning algorithm so that the model generalizes better. L2 and L1 regularization add a penalty term that adjusts the loss function by decreasing the weight matices, reducing model overfitting. The regularization term differs in L1 and L2. In L1 lamda is the absolute value and decreases the weights toward and possibly to zero. In L2 the penalty term, lambda, is squared and decreases the weights toward zero but not exactly zero. This model uses L2 regularization.  The L2 regularized model loss is 0.0691, accuracy is 0.9549, precision is 0.9678, recall is 0.9705, f1 is 0.9683, val loss is 0.4101, val accuracy is 0.8125, val precision is 0.7273, val recall is 1.0000, and val f1 is 0.8421.  The L2 regularized model correctly classified 1212 instances as false and 3802 instances as true.  The L2 regularized model incorrectly classified 73 instances as false and 129 instances as true.  The L2 regularized model roc score is 0.9425 and cv score is 0.9513.  
Dropout is a regularization technique that randomly turns off some neurons during each iteration of training. The dropout model probability is .5.  The dropout model loss is 0.1115, accuracy is 0.9099, precision is 0.9322, recall is 0.9475, f1 is 0.9383, val loss is 0.6932, val accuracy is 0.7500, val precision is 0.6667, val recall is 1.0000, and val f1 is 0.8000.  The regularized model correctly classifies 1122 instances as false and 3792 instances as true.  The regularized model incorrectly classifies 83 as false and 219 as true.  The reglularized model roc score is 0.9076 and cv score is 0.9609.  
Early stopping is a cross validation method that ends trainig once the performance on the validation set begins to decrease.  The early stopping model stopped after 3 epochs.  The early stopping model loss is 0.1490,  accuracy is 0.8762, precision is 0.9064, recall is 0.9368, f1 is 0.9146, val loss is 0.5595, val accuracy is 0.7500, val precision is 0.7000, val recall is 0.8750, val f1 is 0.7778.  The early stopping model correctly classified 1144 instances as false and 3622 instances as true.  The early stopping model incorrectly classified 213 instances as false and 197 instances as true.  The early stopping model roc score is 0.8991. 
The model with the best roc score is the L2 regularized model of 0.9425.  
The test model classified 53 true negatives, 390 true positives, 181 false positives, and 0 false negatives.  If a doctor read the x-ray as negative but the patient had pneumonia symptoms, the doctor would treat the patient for pneumonia.  The test model does not classify any patients who have pneumonia as healthy, but it does classify healthy patients as having pneumonia, similar to a doctor.  


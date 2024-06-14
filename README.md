## Fungus Image Classification with Deep Neural Networks

In the project, the classification problem is solved. The data set DeFungi: Microscopic Fungi Image Classification is located at [DeFungi: Microscopic Fungi Image Classification (kaggle.com)](https://www.kaggle.com/datasets/joebeachcapital/defungi/data). At data preprocessing, images with low variance are supposed as outliers that are blurred or do not contain fungus. Such Images were excluded. Two models are being investigated: ResNet and ConvMixer.

ResNet-34 has a CNN architecture that is a classical one for image classification. ResNet-34 model development includes the following steps:
-	Data augmentation to make the data set balanced;
-	Learning curve investigation on 20% of data points;
-	First grid search of hyperparameters (batch size and learning rate) on 20% of data points;
-	Second grid search of hyperparameters (batch size and learning rate) on the full training set; 
-	Learning curve investigation on the full data set using the 3-fold cross-validation and validation set approach;
-	Improvement of the model using data augmentation
-	Fitting the model with early stopping.

The performance of ResNet-34: Model Test Accuracy = 77%, Precision = 78%, Recall = 79%, F1 score = 79%.

ConvMixer model includes a patch embedding layer and a sequence of repeating fully convolutional blocks. ConvMixer model development includes the following steps.
-	ConvMixer base model development;
-	Learning curve investigation on 90% of data points;
-	Optimal training/test split;
-	Grid search of hyperparameters (batch size and learning rate) on the full training set;
-	Performance evaluation of the tuned model;
-	Improvement of the model by adding mixers to the model;
-	Fitting the model and performance evaluation.

The performance of ConvMixer with 8 mixers: Model Test Accuracy = 78%, Precision = 81%, Recall = 79%, F1 score = 80%.

The performance of ConvMixer with 16 mixers shows worse performance. Adding mixing layers without hyperparameters’ optimization does not improve the model performance.

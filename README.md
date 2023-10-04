# Image-classification---CNN

## Required Libraries
    => tensorflow
    => keras
    => matplotlib
    => numpy
    => seaborn

## Dataset
    Data is loaded from keras datasets
    => cifar10

## Data processing
    => train, test split
    => reshape the dataframes of y_train and y_test

## model building - ANN
    ANN = models.Sequential([
      layers.Flatten(input_shape = (32,32,3)),
      layers.Dense(300, activation = 'relu'),
      layers.Dense(100, activation = 'relu'),
      layers.Dense(10, activation = 'relu'),
      ])

    ANN.compile( optimizer = "adam",
            loss = "sparse_categorical_crossentropy",
            metrics = ["accuracy"]
    )

## Evaluation - ANN
    loss: 14.5063 
    accuracy: 0.1000

## model building - CNN
    CNN = models.Sequential([
    
        layers.Conv2D(filters = 32, activation = 'relu', kernel_size = (3,3), input_shape=(32,32,3)),
        layers.MaxPooling2D(2,2),

        layers.Conv2D(filters = 64, activation = 'relu', kernel_size = (3,3)),
        layers.MaxPooling2D(2,2),
      
        layers.Flatten(),
        layers.Dense(64, activation = 'relu'),
        layers.Dense(10, activation = 'softmax'), # this normalises the values
        ])

## Evaluation
     loss: 1.2716 
     accuracy: 0.5499

## classification_report

    precision    recall  f1-score   support
    
               0       0.61      0.52      0.56      1000
               1       0.59      0.78      0.67      1000
               2       0.50      0.31      0.38      1000
               3       0.40      0.38      0.39      1000
               4       0.54      0.36      0.43      1000
               5       0.57      0.35      0.44      1000
               6       0.50      0.81      0.62      1000
               7       0.67      0.63      0.65      1000
               8       0.54      0.81      0.65      1000
               9       0.59      0.55      0.57      1000
    
        accuracy                           0.55     10000
       macro avg       0.55      0.55      0.54     10000
    weighted avg       0.55      0.55      0.54     10000

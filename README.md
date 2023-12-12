**Dataset**

The model uses the CIFAR-10 dataset. If you don't have it, it will be downloaded automatically during training.
ou can apply the same model to both CIFAR-10 and CIFAR-100 datasets. CIFAR-10 and CIFAR-100 have similar image sizes (32x32 pixels) and channel dimensions (3 channels for RGB), so the architecture of the model should remain the same.
However, keep in mind that CIFAR-100 has 100 classes, whereas CIFAR-10 has only 10 classes. Therefore, you need to modify the last dense layer in your model to have 100 units instead of 10 to match the number of classes in CIFAR-100.

--> ADD THIS: model.add(keras.layers.Dense(100, activation=fuzzy_softmax))

**Model Architecture**
The model architecture includes custom fuzzy activation functions in convolutional layers, max-pooling, dropout, and fully connected layers.

** Custom Components **

**Fuzzy Activation Functions**

-MinOneMinusAActivation: Custom layer implementing min(1-a, b).

-MaxOneMinusAActivation: Custom layer implementing max(1-a, b).

-fuzzy_threshold: Custom activation function implementing fuzzy thresholding.

-fuzzy_softmax: Custom activation function implementing fuzzy softmax.

**Training**

implemented to monitor validation loss.

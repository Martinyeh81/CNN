# Predict Sign Language

## Data

The data is from Kaggle(https://www.kaggle.com/datamunge/sign-language-mnist?select=amer_sign3.png)

### Grayscale image 28x28 pixels with (0-255) pixel values:

||label|pixel1|pixel2|pixel3|pixel4|pixel5|pixel6|...|pixel784|
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|0|3|107|118|127|134|139|143|...|202|
|1|6|155|157|156|156|156|157|...|149|
|2|2|187|188|188|187|187|186|...|195|
|3|2|211|211|212|212|211|210|...|163|
|4|2|164|167|170|172|176|179|...|179|

### Image:

![sign1](https://github.com/Martinyeh81/CNN/blob/main/images/amer_sign3.png)

![sign2](https://github.com/Martinyeh81/CNN/blob/main/images/american_sign_language.png)

### Number of calsses

![sign3](https://github.com/Martinyeh81/CNN/blob/main/images/number_classes.png)

## Model

trainset's shape is (24709, 784)

Valset's shape is (2746, 784)

testset's shape is (27455, 784)

Compute the cross-entropy cost function J:

$$ J = - \frac{1}{m}  \sum_{i = 1}^m  \large ( \small y^{(i)} \log a^{(i)} + (1-y^{(i)})\log (1-a^{ (i)} )\large )\small$$

1. Simulated the DNN model(epoch = 1500, batch_size = 32, optimizer= adam): LINEAR -> RELU -> LINEAR -> RELU -> LINEAR -> SOFTMAX

![sign4](https://github.com/Martinyeh81/CNN/blob/main/images/DNN_layer.png)

2. CNN model(epoch = 200, batch_size = 64, optimizer= adam): CONV2D -> RELU -> MAXPOOL -> CONV2D -> RELU -> MAXPOOL -> FLATTEN -> FULLYCONNECTED

3. ResNet model (epoch = 10, batch_size = 32, optimizer= adam):

The identity block is for the case where the input diimension is the same as the output dimension. Also, it skips over 3 hidden laters

![sign6](https://github.com/Martinyeh81/CNN/blob/main/images/idblock3_kiank.png)

The convolutional block is for the case where the input diimension is different from the output dimension. For example, To reduce the dimensions' H and W by a factor of 2, we use a 1x1 convolution with stride 2. Also, it skips over 3 hidden laters

![sign7](https://github.com/Martinyeh81/CNN/blob/main/images/convblock_kiank.png)

![sign8](https://github.com/Martinyeh81/CNN/blob/main/images/Resnet.png)

## Conclusion

||DNN|CNN|ResNet|
| --- | --- | --- | --- |
|Train Accuracy|1.000|0.921|0.999|
|Val Accuracy|1.000|0.915|1.000|
|Train loss|0.000113|0.235623|0.0011|

DNN Loss function

![sign9](https://github.com/Martinyeh81/CNN/blob/main/images/DNN_loss.png)

CNN Loss function

![sign10](https://github.com/Martinyeh81/CNN/blob/main/images/CNN_loss.png)

ResNet Loss function

![sign11](https://github.com/Martinyeh81/CNN/blob/main/images/ResNet_loss.png)


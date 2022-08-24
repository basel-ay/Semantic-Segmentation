# Semantic-Segmentation

## Segmentation

Segmentation can be viewed as pixel classification, whereas for each pixel of image we must predict its class (background being one of the classes). There are two main segmentation algorithms:

* `emantic segmentation` only tells the pixel class, and does not make a distinction between different objects of the same class.

* `Instance segmentation` divides classes into different instances.

For instance segmentation, these sheep are different objects, but for semantic segmentation all sheep are represented by one class.

![image](https://user-images.githubusercontent.com/64821137/186511335-6120d2e6-06f1-4bb1-b44f-b1800cb90227.png)

There are different neural architectures for segmentation, but they all have the same structure. In a way, it is similar to the autoencoder you learned about previously, but instead of deconstructing the original image, our goal is to deconstruct a mask. Thus, a segmentation network has the following parts:

* `Encoder` extracts features from input image

* `Decoder` transforms those features into the mask image, with the same size and number of channels corresponding to the number of classes.

![image](https://user-images.githubusercontent.com/64821137/186511482-343e1dfb-cfbf-4862-adc6-0968ac1d7450.png)

## SegNet

Simple encoder - decoder architecture with convolutions, poolings in encoder and convolutions, upsamplings in decoder.

![image](https://user-images.githubusercontent.com/64821137/186511774-e5ef3662-b1e2-479e-8f8f-acf0e28234ca.png)

## U-Net

Very simple architecture that uses skip connections. Skip connections at each convolution level helps network doesn't lost information about features from original input at this level.

U-Net usually has a default encoder for feature extraction, for example resnet50.

![image](https://user-images.githubusercontent.com/64821137/186511870-20fda43c-4a42-4b11-bbd3-14a4619e80b5.png)

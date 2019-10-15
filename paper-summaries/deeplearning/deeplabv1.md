## DeepLab: Semantic Image Segmentation with Deep Convolutional Nets, Atrous Convolution, and Fully Connected CRFs

Full blown summary on Atrous convolution and CRF [here](https://towardsdatascience.com/review-deeplabv1-deeplabv2-atrous-convolution-semantic-segmentation-b51c5fbde92d)

1. What's the new addition with regards to previous papers on segmentation? They apply atrous convolution to get a bigger field of view in the convolution layers and also having lesser parameters. A 5x5 atrous convolution has the same number of operations as a 3x3 normal convolution but with a bigger field of view.

2. How exactly does the atrous convolution help with regards to segmentation? By having an Atrous Spatial Pyriamid Pooling (ASPP), helps in brining down the upsampling from an aggressive 32x upsampling to 8x upsampling.

3. The output after the ASPP is fed into a CRF for fine tuning the segmentation. This step is not incorporated in training and hence deeplabv1 is not an end-to-end training network.



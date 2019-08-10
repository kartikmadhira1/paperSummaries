### SqueezeSegV2: Improved Model Structure and Unsupervised Domain Adaptation for Road-Object Segmentation from a LiDAR Point Cloud

Introduction : An deep learning based point cloud segmentation model to output point wise labels with input from point cloud.

1. V1 was not robust to dropout noise in lidar point clouds and was performance was bad when put on real world data.
1. This paper also uses the GTA - V simulator as data to feed into the model for training. However, the simulation data failed to be applicable on real world data.
1. The major improvement from V1 is thus a domain adaptation pipeline that makes it possible for the the training on simulator be used on real world (KITTI dataset) composed of 3 major chunks, namely - Learned Intensity Rendering, Geodesic Correlation Alignment and Progressive Domain Calibration.

    1. Learned Intensity Rendering (Pre-training): GTA - V simulator lacks in having an intensity slice in it's point cloud data. This intensity is the magnitude of the received signal, an important perception element and an element lacking in V1 network. In order to make this data slice available on the GTA - V simulator, the authors make through a self supervision network where they take a labeled dataset like the KITTI dataset and create a supervised model to render intensities and add it to GTA - V data.
    The loss is not L2 or L1 though. The authors specify that the same x, y, z values can have two different intensities and hence regression is not the best solution. Instead the authors choose a hybrid loss function that is a mixture of classification and regression. The intensities are grouped in n = 10 groups and the network first predicts the group. Once, the network outputs the group, the regressor then outputs an offset from the group base reference intensity. 

    2. Geodesic correlation alignment (Training): After intensity rendering, the GTA-V dataset is used to train on Focal loss Focal loss ([explanation!](https://medium.com/adventures-with-deep-learning/focal-loss-demystified-c529277052de)). However this is supervision only based on the GTA-V data. This is expected to have a bias towards simulated data. Hence at every training iteration, the authors propose a parallel model(shared weights) that takes in KITTI dataset(real world) data, propagates through the same network, an in the end trains on a geodesic loss from the output of GTA-V data output and the KITTI output. Therefore the final loss is a addition of the geodesic loss and the focal loss.
    ![geodesic_correlation](PaperSummaries/images/trainloss.png)
    ![geodesic_correlation](PaperSummaries/images/geodesic correlation.png)

    3. Progressive Domain Calibration(Post-training): The authors then propose a post training calibration process wherein the idea is to normalize the output distributions of each layer with mean 0 and standard deviation 1 and then update the batch normalization mean and variance accordingly.

1. Apart from the domain adaptation pipeline, the authors also propose CAM, focal loss, lidar mask and batch normalization in order to improve upon the dropout noise.
    1. Context Aggregation module (CAM) - The idea of CAM is to have a larger receptive field in the input layer since the dropouts are scattered and squeeze a large field into one. The authors propose a large max pooling layer(stride - 7) in the input layer, followed by two conv layers and finally element wise multiplication with input. This improves the dropout noise.
    2. Focal loss improves the accuracy significantly.
    3. Lidar mask is one more layer apart from x, y, z and intensity which depicts if a pixel is missing or existing and improves the network along with batch normalization every layer.
# Paper Summaries:


### _Learning and traditional approaches_
#### __Architectures__

1.[ResNets](paper-summaries/deeplearning/resnet.md), ResNext and DenseNet.

### _Detection and Segmentation_

#### Detection
1. Histogram of Oriented Gradients for Human Detection [Summary](paper-summaries/traditional/HOG_human_detect.md) | [paper](https://lear.inrialpes.fr/people/triggs/pubs/Dalal-cvpr05.pdf)

2. Object Detection with Discriminatively Trained Part Based Models [Summary](paper-summaries/traditional/dpm.md) | [paper](http://cs.brown.edu/people/pfelzens/papers/lsvm-pami.pdf)

1. OverFeat: Integrated Recognition, Localization and Detection using Convolutional Networks [Summary](paper-summaries/traditional/overfeat.md) | [paper](https://arxiv.org/pdf/1312.6229.pdf)

2. SSD: Single Shot MultiBox Detector [Summary](paper-summaries/deeplearning/ssd.md) | [paper]https://arxiv.org/pdf/1512.02325.pdf)

3. YOLOv3: An Incremental Improvement [Summary](paper-summaries/deeplearning/yolo.md) | [paper](https://pjreddie.com/media/files/papers/YOLOv3.pdf) **TODO**

4. EfficientDet: Scalable and Efficient Object Detection [Summary](paper-summaries/deeplearning/ed.md) | [paper](https://arxiv.org/abs/1911.09070)

#### Segmentation

1. Fully Convolutional Networks for Semantic Segmentation [Summary](paper-summaries/deeplearning/fcn_seg.md) | [paper](https://arxiv.org/abs/1411.4038) **TODO**
2. DeepLab: Semantic Image Segmentation with Deep Convolutional Nets, Atrous Convolution, and Fully Connected CRFs [Summary](paper-summaries/deeplearning/deeplabv1.md) | [paper](https://arxiv.org/pdf/1606.00915.pdf) **TODO**

3. Hypercolumns for Object Segmentation and Fine-grained Localization (Instance Segmentation) [Summary](paper-summaries/deeplearning/hypercolumns.md) | [paper](https://arxiv.org/pdf/1411.5752.pdf) **TODO**

#### Point Clouds

1. SqueezeSegV2: Improved Model Structure and Unsupervised Domain Adaptation  for  Road-Object  Segmentation  from  a  LiDAR  Point Cloud [Summary](paper-summaries/deeplearning/squeezesegv2.md) | [paper](https://arxiv.org/pdf/1809.08495.pdf)


#### Evaluation

1. Understanding Precision and Recall curve [see this awesome blog post](https://github.com/rafaelpadilla/Object-Detection-Metrics#precision-x-recall-curve)

### _Tracking and Sensor Fusion_
1. Multiple Object Tracking Performance Metrics and Evaluation in a Smart Room Environment - [Summary](https://github.com/kartikmadhira1/paper-summaries/blob/master/paper-summaries/mota.md) | [paper](https://cvhci.anthropomatik.kit.edu/~stiefel/papers/ECCV2006WorkshopCameraReady.pdf)



##### High Notes questions:

1. Why are pointers needed, in fact what do they bring in more than normal variables created by allocation memory stably by compiler on the stack.

2. How does the interpreter know if a block of register values is float or int. Why does your program need specific variable types is it ease of use meaning it makes sense to handle floats and int differently or there are instruction specific issues with floats and int that they are segregated so.

- thought - > raw memory is all register with 8 bits, depends on compiler/interpreter to compile/interpret them using binary - [DECIMAL/INT/FLOATING POINT] converter.

- thought -> Hardware explanation of pointers w.r.t dynamic and static/runtime and compile type needs of the program(remember struct Node* creation!)  We are using pointers because this performed actions returns memory address. Technique for usage of memory addresses in C++ is usage of pointers!!!

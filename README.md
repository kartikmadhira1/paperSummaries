# Paper Summaries:


### _Learning and traditional approaches_
#### __Architectures__

1.[ResNets](PaperSummaries/deeplearning/resnet.md), ResNext and DenseNet.

### _Detection and Segmentation_

#### Traditional vision based
1. Histogram of Oriented Gradients for Human Detection [Summary](PaperSummaries/traditional/HOG_human_detect.md) | [Paper](https://lear.inrialpes.fr/people/triggs/pubs/Dalal-cvpr05.pdf)

2. Object Detection with Discriminatively Trained Part Based Models [Summary](PaperSummaries/traditional/dpm.md) | [Paper](http://cs.brown.edu/people/pfelzens/papers/lsvm-pami.pdf)

#### Deep learning based

1. OverFeat: Integrated Recognition, Localization and Detection using Convolutional Networks [Summary](PaperSummaries/traditional/overfeat.md) | [Paper](https://arxiv.org/pdf/1312.6229.pdf)

#### Point Clouds

1. SqueezeSegV2: Improved Model Structure and Unsupervised Domain Adaptation  for  Road-Object  Segmentation  from  a  LiDAR  Point Cloud [Summary](PaperSummaries/deeplearning/squeezesegv2.md) | [Paper](https://arxiv.org/pdf/1809.08495.pdf)


#### Evaluation

1. Understanding Precision and Recall curve [see this awesome blog post](https://github.com/rafaelpadilla/Object-Detection-Metrics#precision-x-recall-curve)

### _Tracking and Sensor Fusion_

1. Multiple Object Tracking Performance Metrics and Evaluation in a Smart Room Environment - [Summary](https://github.com/kartikmadhira1/paperSummaries/blob/master/PaperSummaries/mota.md) | [Paper](https://cvhci.anthropomatik.kit.edu/~stiefel/papers/ECCV2006WorkshopCameraReady.pdf)



##### High Notes questions:

1. Why are pointers needed, in fact what do they bring in more than normal variables created by allocation memory stably by compiler on the stack.

2. How does the interpreter know if a block of register values is float or int. Why does your program need specific variable types is it ease of use meaning it makes sense to handle floats and int differently or there are instruction specific issues with floats and int that they are segregated so.

- thought - > raw memory is all register with 8 bits, depends on compiler/interpreter to compile/interpret them using binary - [DECIMAL/INT/FLOATING POINT] converter.

- thought -> Hardware explanation of pointers w.r.t dynamic and static/runtime and compile type needs of the program(remember struct Node* creation!)  We are using pointers because this performed actions returns memory address. Technique for usage of memory addresses in C++ is usage of pointers!!!

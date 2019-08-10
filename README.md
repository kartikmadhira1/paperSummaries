# Paper Summaries:


### _Deep Learning_
#### __Architectures__

1.[ResNets](PaperSummaries/deeplearning/resnet.md), ResNext and DenseNet.

#### __Point Clouds__

1. SqueezeSegV2: Improved Model Structure and Unsupervised Domain Adaptation  for  Road-Object  Segmentation  from  a  LiDAR  Point Cloud [Summary](PaperSummaries/deeplearning/squeezesegv2.md) | [Paper](https://arxiv.org/pdf/1809.08495.pdf)


### _Tracking and Sensor Fusion_

1. Multiple Object Tracking Performance Metrics and Evaluation in a Smart Room Environment - [Summary](https://github.com/kartikmadhira1/paperSummaries/blob/master/PaperSummaries/mota.md) | [Paper](https://cvhci.anthropomatik.kit.edu/~stiefel/papers/ECCV2006WorkshopCameraReady.pdf)


##### High Notes questions:

1. Why are pointers needed, in fact what do they bring in more than normal variables created by allocation memory stably by compiler on the stack.

2. How does the interpreter know if a block of register values is float or int. Why does your program need specific variable types is it ease of use meaning it makes sense to handle floats and int differently or there are instruction specific issues with floats and int that they are segregated so.

- thought - > raw memory is all register with 8 bits, depends on compile/interpreter to compile/interpret them using binary - [DECIMAL/INT/FLOATING POINT] converter.

- thought -> Hardware explanation of pointers w.r.t dynamic and static/runtime and compile type needs of the program(remember struct Node* creation!)  We are using pointers because this performed actions returns memory address. Technique for usage of memory addresses in C++ is usage of pointers!!!

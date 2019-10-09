## SSD: Single Shot MultiBox Detector


This is a single shot detector (same as OverFeat) and for a expanded explanation see this [blog](https://medium.com/@jonathan_hui/ssd-object-detection-single-shot-multibox-detector-for-real-time-processing-9bd8deac0e06) post.

1. All of the detectors mostly use two underlying techniques to detections: First, to build a feature map and then apply convolution filters to detect objects at different scales. Same is used by SSD.

![](../images/ssd.png)


2. The SSD network is based of VGG16 architecture. Upto the Conv4_3 layer it is essentially a feature extractor.
3. The detections start from the Conv4_3 layer where a 38x38x512 mapped layer is present. Every cell in this 38x38 spatial layer is used to output 4 predictions. Each of these 4 predictions contains 21 class scores (20 objects and 1 background score) and 4 of the bounding box predictions.
4. Similar to this stage at a particular scale, similar predictions are made for different scales in the consecutive layers with sometimes to 6 predictions per box for smaller resolutions. This way the later reduced resolution layers are responsible to detect bigger objects. **Higher resolution feature maps are responsible for detecting small objects. The first layer for object detection conv4_3 has a spatial dimension of 38 × 38, a pretty large reduction from the input image. Hence, SSD usually performs badly for small objects comparing with other detection methods. **
5. 


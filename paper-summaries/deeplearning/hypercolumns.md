LOL

1. Spatial info loss as we go deeper. Hence, to capture this info for classifier, this method was introduced.
2. First, it is assumed we got a set of detections from an object detection system, after non-maximum suppression (NMS).
3. Then, the bounding box of the detection is expanded slightly and predict a heatmap on this expanded box (50 x 50).
4. For segmentation, the heatmap encodes the probability that a particular location is inside the object. Since it is 
segmented after detection, thus, I declare it as an instance segmentation approach at the title.
5. And it also works for part labeling/keypoint prediction, a separate heatmap is predicted for each part/keypoint, 
where each heatmap is the probability a location belongs to that part/keypoint.
6. In each case, a 50×50 heatmap is predicted and then resized to the size of the expanded 
bounding box and splat onto the image.
7. Location is important, e.g.: for a detected person, head should be at the top of box. Thus, the simplest way is to 
train separate classifiers for each of 50×50 locations,i.e. using 1×1 convolution or fully connected (FC) layer on 
each hypercolumn can be used at each location.
8. But there are three problems: -. The amount of data going through one point is few, which might lead to overfitting.
-. Training such many classifiers are computational expensive. 3. Adjacent pixels should be similar to each other.

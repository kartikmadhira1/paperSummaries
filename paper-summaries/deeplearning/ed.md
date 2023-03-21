Before we begin, the key design in some of the current object detector architectures is:
1. Backbone - Feature extractor. Common examples include -> ResNets, VGGs and in this case the EfficientNet. Contains Low-level(edges, lines, corners.  High spatial resolution features), Mid-level and High-level features(More refined features - e.g face, hands but low spatial resolution).
2. Feature Pyramid Network (FPN) - Fuses features from multiple scales (via the backbone). Usually equal weightage is given to each scale.
3. BBox regression and classification


In the case of EfficientDet, key improvements to this structure proposed were:

1. Efficient Multi-scale fusion -> Aims to weigh features levels to contribute to better overall loss. 
2. BiFPN -> Bi-directional and cross-connection flow of features. So it is not just top-down but bottom-up addition too when compared against FPN. (P3-P7 fusion)
3. Efficient scaling of network -> Jointly scale up the resolution, depth (number of sequential Bi-FPN layers) and width (number of channels) of the baseline efficientdet baseline model. Intuition is that rather than blindly increasing resolution of backbone or increasing the FPN depth, the authors emperically developed method to efficiently jointly scale up (resolution, depth, width)







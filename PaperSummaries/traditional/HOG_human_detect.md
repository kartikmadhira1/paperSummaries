# Histogram of Oriented Gradients for Human Detection

A better down summary is available [here](http://mccormickml.com/2013/05/09/hog-person-detector-tutorial/).

1. The overall idea of the paper is to get robust features in a 'global context'.
2. Features are the normalized histogram from each of the 8x8 pixel non-overlapping cells. 
3. The normalization occurs with every non-edge cell getting normalized by 2x2 blocks(not pixels or cells) in each direction. 
4. The denominator for normalization is the magnitude of the gradient in one block. Therefore every cell is normalized by 4 other blocks and thus each cell has 9x4 = 36 size feature vector.
5. Why block normalization? - First, every normalization because it makes the gradient vectors invariant to illumination. Secondly, block because it should take care of occlusion from shadows.
6. In total the detector is trained on 64x128 a window size and therefore there are 7 cells horizontally possible and 15 cells vertically, which in total is 7x15x9x4 = 3780 feature points from a single window.
7. This feature set is then sent to be trained on a linear SVM.

![HOG pipeline, taken from Prof.Abhinav Shrivastava's slides](images/hog.png)


Additional topics covered in the paper:

1. Hard mining
2. Sliding window approach
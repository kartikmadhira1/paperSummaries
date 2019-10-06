## Multiple Object Tracking Performance Metricsand Evaluation in a Smart Room Environment

1. Establishes a common metric to establish accuracy and precision - MOTA and MOTP, when multiple objects are present and the goal is to evaluate the hypothesis by a certain tracker every frame. 
2. This is important since metrics previous to this were complex and evaluation parameter was not unified.
3. General Algorithm is:
    1. Get a correspondance mapping M between the ground truth(Oi) and hypothesis(Hj) for frame t, if valid id mapping is already present. Here valid mapping means, that the ID for a particular object is same in ground truth and hypothesis from tracker. Initialize Mismatch error(mme), False positives (fp) and misses(m).
    2. If there is no valid mapping available, use cost parameter(Euclidean distance, IoU) for assigning the mapping M in Munkre's algorithm.
    3. For next frame t+1, get the mapping for each id and check for corresponding hypothesis id from M.
    4. If there is a mismatch, increase MME by 1 and update munkres with a new mapping (Oi,Hk). Calculate false positives and misses and increase them accordingly.
    5. Calculate MOTA and MOTP.

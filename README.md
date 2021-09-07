# Artificial Intelligence in Medical Imaging
This project was done as part of a 4th year capstone project at the University of Toronto to reduce time and space demands of MRI scans.
We designed a system using U-Nets and kMeans to optimally select a subset of k-space points from a MRI scan that yields a high quality image.
Our system utilizes a custom masking technique and a modified version of Facebook’s fastMRI U-Net to quickly reconstruct a MRI image from a subset of k-space points.
The system overall is able to achieve Structural Similarity Index Metric scores exceeding 75% between the ground truth and the reconstructed MRI image.

## Context
Current Medical Resonance Imaging (MRI) reconstruction procedure is
inefficient; k-space data acquisition and transformation is time
consuming

## Goal
Determine if machine learning algorithms can be applied to identify a
subset of k-space points from an MR scan, that when reconstructed
produces an MR image of a comparable level of detail to that of the
ground truth image.

## Design Flow
1. A raw k-space dataset is first fed into the k-space reduction model to
obtain a sub-sampled k-space dataset via unsupervised learning
models like K-Means clustering.
2. A U-Net model is pre-trained on 300 k-space subsets (i.e. 9000
images) to accurately enhance the input subsampled k-space dataset
3. During the prediction phase, we send the subsampled k-space dataset
from part 1 through the U-Net to obtain an enhanced MR image
4. SSIM is then computed for ground truth and reconstructed image for
quantifying similarity
5. For our experiment, we calculated the mean SSIM of the 1050 images
that were obtained from the U-Net. Our final SSIM score was 0.80285.

## Results & Conclusion
Results and Conclusion
- Achieved final SSIM of 80.285%, beating our target of 75%
- Confirmed hypothesis of patterns in k-space, obtainable via
AI algorithms
- Fulfilled all project requirements, while maintaining flexibility
through tunable parameters 

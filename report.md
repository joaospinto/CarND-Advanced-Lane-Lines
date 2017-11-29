# Advanced Lane Lines (Term 1)

## Objective
The goal of this project is to expand on the first project of this term and apply more advanced computer vision techniques to the problem of finding lane markings.

## Approach
We first use the provided calibration images (containing images of a `9x6` chess-board) to compute the distortion coefficients of the camera. These can then be used to undistort all the images that were taken with this camera. After this, we extract the HLS decomposition of each image, and apply histogram equalization on the L channel. We use thresholding on the S channel, as well as on the Sobel gradients of the equalized L channel, to extract coarse lane markings from the image.
Afterwards, we do a perspective transform on the image to obtain a birds-eye view of the lanes, and use RANSAC to interpolate both lines. At this point, we color the region between the interpolated lines, and revert back to the original image frame (undoing the perspective transform). Finally, this is overlayed on top of the original image.

## Conclusion



examples
![left](report_images/left_2017_10_05_11_20_13_397.jpg) [here](https://youtu.be/pi8hGzjxwAE)

# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.


---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

I implemented my pipeline per the following design:

1. Use Canny edge detector to identify the edges on the given image
2. Assuming the field of view to be from a camera installed on the front of a vehicle, define a triangular region of interest on the front to identify lanes
3. Use Hough transform to identify straight lines (lanes)
4. For lanes which are not solid lines, use line-fitting techniques to identify lanes as solid lines

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


1. If lanes are not lines and instead reflective markers, this approach will fail
2. If camera is not installed on the front, this approach will fail
3. Related to the point above, if the lanes are not in the bottom triangular region, this approach will fail
4. Hough transform parameters are tuned per the given example image set. This is a tunable set of parameters and not universal
5. If the lanes are curved, this approach might not work.



### 3. Suggest possible improvements to your pipeline

1. This approach can be enhanced to identify curved roads, elevated highways etc.
2. The jitter from frame to frame can be reduced by averaging with the line fit from the previous frame

# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I applied Gaussian smoothing,  then Canny Edge detection, then I created a masked edges image, only with a region, where lane lines likely are, then I used  Hough transformation to get a list of lines.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by taking bunch of lines and extrapolating them. To do that I took all sorted points by slope and use `np.polyfit` to fit a line to these points. The `np.polyfit` returns  coeficients for my single line `y = mx + b`, then I used `np.poly1d` function to calculate single line 
equation with coeficients from `np.polyfit` .




### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when car is not in the center of the road. It is possible, that lane lines will be out of region of interest, but in the same time visiable. In such case any lane lines will be detected. 

Another shortcoming could be when we will take image from crossroads with pedestrian crossings, and all this road signs will be in region of interest.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to use slopes from previous frames to calculating slope for the last frame.

Another potential improvement could be to use dynamically detection of region of interest using some machine learning techniques (Deep learning, SVM, etc.) 

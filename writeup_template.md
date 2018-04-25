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

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by 




### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when car is not in the center of the road. It is possible, that lane lines will be out of region of interest, but in the same time visiable. In such case any lane lines will be detected. 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to use slopes from previous frames to calculating slope for the last frame.

Another potential improvement could be to use 

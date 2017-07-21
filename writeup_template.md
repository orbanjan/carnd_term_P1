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

My pipeline consisted of 5 steps. 
           1. I converted the images to grayscale
           2. Applied Gaussian blurring/smoothing
           3. Used Canny edge detection
           4. Mask the useful area
           5. Run Hough transformation on egge detectel image to get lines

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by
           a. Separate the lines based on their slopes (positive and nevative)
           b. Also use separation on x cordinates whether the point fallan on the left or on righ half of the image
           c. collect x and y arrays separately and applied a linear fit on that
           d. knowing the b, m slope and intercept parameters of each lane lines we can calculate the 2 lines (knowing their starting and end y coordinates already)

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when lanes have a high curviture. 

Another shortcoming could be high contast on the image (shadows)


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to apply curved masking area based on identification on the road curves

Another potential improvement could be to filter further based on slopes (ie slopes with very high or very low would be eliminated).


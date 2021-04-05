# **Finding Lane Lines on the Road** 

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

My pipeline consisted of following steps. 
* I convert the rgb image to gray image
* Then I use guassian blur with kernal size = 3 to denose image
* Canny detector is use to get the edge of the image
* I applied the point of interest to remove the edge outside of POI
* HoughlineP is used to detect the lines
* In order to draw a single line on the left and right lanes, I modified the draw_lines() function by split left and right detected by whether the slope is positive or negative. Then average of these two clusters to get the slope and center x,y. Afterwards, I derive the equation and use the min/max y value to get the cooresponding min/max x value.

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the camera moved. Currently, I fixed the POI to certain area.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to use color selection as another potential filter to detected the lanes.

# **Finding Lane Lines on the Road** 
---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images_output/grayscale_output.jpg "Grayscale"
[image2]: ./test_images_output/gaussian_blur_output.jpg "Gaussian Blur"
[image3]: ./test_images_output/canny_output.jpg "Canny"
[image4]: ./test_images_output/region_of_interest_output.jpg "Region Of Interest"
[image5]: ./test_images_output/hough_lines_output.jpg "Hough Lines"
[image6]: ./test_images_output/final_output.jpg "Final Output"

---

### Reflection

### 1. Description of pipeline:

My pipeline consisted of 5 steps as:

1. Conversion of the images to grayscale.
2. Applied Gaussian Blur with kernel size of 5 to smoothen the images.
3. Used Canny Edge Detector to get edges information from the images.
4. Cropped images to consider only lower half of the images.
5. Used Hough Transform to detect lines

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by following logic:

1. Separated left lane lines and right lane lines using slope of lines.
2. Got bottom most point of line and top most point of line for both left and right lane lines.
3. Using these points, drawn lane lines

Example images for various statges of pipeline: 

![Grayscale][image1]
![Gaussian Blur][image2]
![Canny][image3]
![Region Of Interest][image4]
![Hough Transform][image5]
![Final Output][image6]

### 2. Shortcomings with my current pipeline


One potential shortcoming would be what would happen when road would have more curves, as a result lane lines will look like curves, so plotting straight lane lines will not be a good idea.

Another shortcoming could be If there are more straight lines which are not lane lines, it will be difficult to find the actual lane lines.


### 3. Possible improvements to my pipeline

A possible improvement would be to not plot straight line using top most and bottom most points, instead plot by connecting end points of various straight lines of a single lane together.

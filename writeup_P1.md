# **Finding Lane Lines on the Road** 

## Project Overview
---

**Finding Lane Lines on the Road**

The goal of this project is to find road lane lines on the road. 

[//]: # (Image References)
[image1]: ./test_images/solidWhiteRight.jpg "Solid White Right"
[image2]: ./test_images/solidWhiteCurve.jpg "Solid White Curve"
[image3]: ./test_images/solidYellowCurve2.jpg "Solid Yellow Curve 2"
[image4]: ./test_images/solidYellowLeft.jpg "Solid Yellow Left"
[image5]: ./test_images/whiteCarLaneSwitch.jpg "White Car Lane Switch"
[image6]: ./test_images/solidYellowCurve.jpg "Solid Yellow Curve"
[image10]: ./examples/gray_solidWhiteRight.jpg "Solid White Right in Gray Scale"
[image20]: ./examples/gray_solidWhiteCurve.jpg "Solid White Curve in Gray Scale"
[image30]: ./examples/gray_solidYellowCurve2.jpg "Solid Yellow Curve 2 in Gray Scale"
[image40]: ./examples/gray_solidYellowLeft.jpg "Solid Yellow Leftin Gray Scale"
[image50]: ./examples/gray_whiteCarLaneSwitch.jpg "White Car Lane Switch in Gray Scale"
[image60]: ./examples/gray_solidYellowCurve.jpg "Solid Yellow Curve in Gray Scale"
[image100]: ./examples/blur_solidWhiteRight.jpg "Blurred Solid Right Curve"
[image200]: ./examples/blur_solidWhiteCurve.jpg "Blurred Solid White Curve"
[image300]: ./examples/blur_solidYellowCurve2.jpg "Blurred Solid Yellow Curve 2"
[image400]: ./examples/blur_solidYellowLeft.jpg "Blurred Solid Yellow Left"
[image500]: ./examples/blur_whiteCarLaneSwitch.jpg "Blurred White Car Lane Switch"
[image600]: ./examples/blur_solidYellowCurve.jpg "Blurred Solid Yellow Curve"
[image1000]: ./examples/canny_solidWhiteRight.jpg "Edges Detected - Solid White Right"
[image2000]: ./examples/canny_solidWhiteCurve.jpg "Edges Detected - Solid White Curve"
[image3000]: ./examples/canny_solidYellowCurve2.jpg "Edges Detected - Solid Yellow Curve 2"
[image4000]: ./examples/canny_solidYellowLeft.jpg "Edges Detected - Solid White Curve"
[image5000]: ./examples/canny_whiteCarLaneSwitch.jpg "Edges Detected - White Car Lane Switch"
[image6000]: ./examples/canny_solidYellowCurve.jpg "Edges Detected - Solid Yellow Curve"
[image10000]: ./examples/hough_solidWhiteRight.jpg "Solid White Right Hough Lines"
[image20000]: ./examples/hough_solidWhiteCurve.jpg "Solid White Curve Hough Lines"
[image30000]: ./examples/hough_solidYellowCurve2.jpg "Solid Yellow Curve 2 Hough Lines"
[image40000]: ./examples/hough_solidYellowLeft.jpg "Solid Yellow Left Hough Lines"
[image50000]: ./examples/hough_whiteCarLaneSwitch.jpg "White Car Lane Switch Hough Lines"
[image60000]: ./examples/hough_solidYellowCurve.jpg "Solid Yellow Curve Hough Lines"
[image100000]: ./test_images_output/image_solidWhiteRight.jpg "Solid White Right with Solid Lane Lines"
[image200000]: ./test_images_output/image_solidWhiteCurve.jpg "Solid White Curve with Solid Lane Lines"
[image300000]: ./test_images_output/image_solidYellowCurve2.jpg "Solid Yellow Curve 2 with Solid Lane Lines"
[image400000]: ./test_images_output/image_solidYellowLeft.jpg "Solid Yellow Left with Solid Lane Lines"
[image500000]: ./test_images_output/image_whiteCarLaneSwitch.jpg "White Car Lane Switch with Solid Lane Lines"
[image600000]: ./test_images_output/image_solidYellowCurve.jpg "Solid Yellow Curve with Solid Lane Lines"
---

### Reflection

### 1. Pipeline

My pipeline steps are implemented like, first I generated a folder that contains the output images. I generated it by using ‘try, catch’ commands to avoid the error when there was already generated. Then, I converted images in test_images folder to gray scale like below. 

![alt text][image1] 
![alt text][image10] 
![alt text][image2] 
![alt text][image20] 
![alt text][image3] 
![alt text][image30] 
![alt text][image4] 
![alt text][image40] 
![alt text][image5] 
![alt text][image50] 
![alt text][image6] 
![alt text][image60] 

After that, I used to gray images to convert blurred images by using Gaussian blur method as they can be seen in below.

![alt text][image100]
![alt text][image200]
![alt text][image300]
![alt text][image400]
![alt text][image500]
![alt text][image600]

By using blurred images, I used Canny Edge detector to detect edges like below images. 

![alt text][image1000]
![alt text][image2000]
![alt text][image3000]
![alt text][image4000]
![alt text][image5000]
![alt text][image6000]

After edge detection process I selected the section that defines region of interest which avoids to handle unnecessary lines. Then, By using hough transform I found the hough lines and draw them on the images as they can be seen below. 

![alt text][image10000]
![alt text][image20000]
![alt text][image30000]
![alt text][image40000]
![alt text][image50000]
![alt text][image60000]


In the second part, it is asked to be more advanced the improvement of draw lines() is needed. Therefore, lane lines would look like a whole line. To make this improvement; first I seperated right and left lanes according to line slopes. Then, I saturated all slopes and intercepts values for each lane and collected them in arrays. By using arrays, I found the average slope and intercept for right and left lane. According to average slope and intercept lane lines were fitted via line mathematical formula. 

As a result, the outcomes of images looks like below.

![alt text][image100000]
![alt text][image200000]
![alt text][image300000]
![alt text][image400000]
![alt text][image500000]
![alt text][image600000]


### 2.  Potential Shortcomings with your current pipeline

One potential shortcoming could be the line presentation, since lanes are found most of times in the video stream. Sometimes they could be lost or look wrong. 

### 3. Possible Improvements

A possible improvement would be when region of interest is to be parametrized according to camera position on the vehicle.

Another potential improvement could be to add threshold when there is no lane found may be the last found lanes could continue to be presented. Since lanes are found most of times in the video stream. 

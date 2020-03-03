# **Finding Lane Lines on the Road** 
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

<img src="examples/laneLines_thirdPass.jpg" width="480" alt="Combined Image" />

Overview
---

The goal of this project is to find road lane lines on the road. To do that, steps are implemented like, first I generated a folder that contains the output images. I generated it by using ‘try, catch’ commands to avoid the error when there was already generated. Then, I converted the image to gray scale. After that, I used to gray image to conver blurred image by using Gaussian blur method. By using blurred image, I used Canny Edge detector to detect edges. After edge detection process I selected to section that defines region of interest. Then, By using hough transform I found the hough lines and draw them on the image. 
In the second part, it is asked to apply the code to video stream. After it was applied to be more advanced the improvement of draw lines function is needed. Therefore, lane lines would look like a whole line. 



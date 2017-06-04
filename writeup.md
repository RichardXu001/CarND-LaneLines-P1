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
  My pipeline consisted of 5 steps.
  1. Converted the images to grayscale.
  2. use Gaussianblur to make it more smooth.
  3. Use Canny to output Edge, before that,need to
  4. Only keep the region that we interest
  5. Use hough transform to draw line.
  In order to draw a single line on the left and right lanes, I modified the draw_lines() function by make cv2.HoughLinesP.
  threshold=32
  minLineLength=5
  maxLineGap=200
  ### 2. Identify potential shortcomings with your current pipeline
  One potential shortcoming would be what would happen when I use my pipeline to test "challenge.mp4", when coming through the tree shadow. It would mistaken the shadow to be lane.
  Another shortcoming could be the road edge will refect the sunlight and would also be mistaken as lane.
  ### 3. Suggest possible improvements to your pipeline
  A possible improvement would be to use a different parameter for different road condition. 
  Another potential improvement could be to lower the dependability of camera and more rely on other sensors like Radars and Lidar temporarily untill the this condtion fade away.
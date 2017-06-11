
## Writeup and Submission


### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. 

1. Turn images to Grayscale
2. Apply gaussian blur to the grayscale images.
3. Convert gaussian blurred grayscaled images to canny edge images after reducing it to only Regions of Interest.
4. Canny edge images to hough transforms to get the lines
5. Overlap the hough transformed lines with the original lines

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by finding all the lines and separating them as left lines and right lines. Then taking the mean slope of the left lines and mean slope of the right lines. I then found out the intersection point. I then drew the lines.




### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the lane expands sideways or when the road goes up hill the region of interest won't be capturing the interesting regions anymore.

Another shortcoming could be if the there is any car in front of the camera, the mean of the left and right lines will be distorted significantly.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to dynamically identify the region of interest by extrapolating or adding weights to the previous lane lines identified, because a lane lines should not change drastically and should ideally follow a smooth change.

Another potential improvement could be to fitting of learning of rho, thetha etc. that is being sent to hough transform. A pipeline that produces lane lines from different combinations of rho thetha can then learn how a rho and thetha changes according to the changes in lane patterns or spacings.



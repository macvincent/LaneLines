# **Finding Lane Lines on the Road** 
In this project, I assembled a pipeline and tuned function parameters to take an image of a road and identify the lane lines. It also works for videos, which are nothing more than a series of images.

### Pipeline
The lane identification pipeline consisted of these seven stages in order:
1.  `grayscale()`: Converts our image to grayscale
2.  `gaussianblur()`: Reduces noise by smoothening image
3.  `canny()`: Identifies the edges in the smoothened grayscale image
4.  `region_of_interest()`: Here we specify the section of our image where we want to identify our lane lines
5.  `hough_lines()`: We use this function to extract our lane lines
6.  `draw_lines()`: After extracting our lane lines, we impose it on an empty image
7.  `weighted_img()`: Here we combine our lane image with the original image

### Potential shortcomings with current pipeline

1.  The pipeline is not accurate. For some video frames, we get outliers that produce crisscrossed lanes which can have a serious impact in real-world applications.
2.  The lane lines are also not as accurate as they should be. While they are quite close to the actual lane lines the majority of the time, it will be better if it can be made more accurate.

### Suggest possible improvements to your pipeline
1. While coding up the `draw_lines()` function was intellectually interesting, the lines are not as accurate as they should be and this can be improved.
2. While it works for the videos in this repository, the current pipeline does not adjust to pictures of different types and dimensions. This can be worked on.
3. More work also needs to be done to prevent and reduce the possibility of identifying wrong lane lines.

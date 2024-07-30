
# Lane Detection System for Advanced Driver-Assistance Systems (ADAS)

## Introduction

Automation is the future, and humans are striving to achieve it in every aspect of their lives to build a fast and secure environment that is less prone to errors and anomalies. Advanced Driver-Assistance System (ADAS) for autonomous vehicles is one of the major technologies embedded in autonomous vehicles to provide safe and effective road navigation. Lane Line Detection using Computer Vision is an essential part of ADAS to provide accurate and reliable lane detection technology.

Lane detection is the ability of a system to identify the lane boundaries on a road. The lane detection system is crucial for maintaining lane position and stability. It also helps to predict the vehicle's trajectory and control the vehicle's speed, steering angle, and braking system. In this project, we use the OpenCV library in Python to implement a lane detection system.

## Methodology

1. **White Color Selection**:
   - Detect white lane lines by loading an image into a numpy array and obtaining its height and width from the shape attribute.
   - Create a copy of the original image for processing.
   - White color is RGB(255,255,255), but we use a minimum threshold of (200,200,200) to detect white lanes as they can be slightly faded.
   - Mask out pixels below the threshold, resulting in an output image with white lines highlighted and the rest of the image black.

2. **Region Masking**:
   - Detect the region for white lines by defining a triangular region using two base points and an apex.
   - Use `np.polyfit` to fit a linear function (Y=AX+B) to each side of the triangle using data points, returning [A,B] of the fit.
   - Mask out pixels below the threshold, resulting in the entire picture except the white lanes being black.
   - Display the original image with our region of interest outlined in red.

3. **Edge Detection**:
   - Apply Canny edge detection by reading the image in grayscale and applying Gaussian smoothing to reduce noise.
   - Apply the Canny edge detection algorithm to the smoothed image to get the edges.
   - Define a region of interest using the same triangle as before and apply a mask to the edges image to get the edges inside the region of interest.

4. **Hough Transform**:
   - Use the Hough transform algorithm to detect lines in the masked edges image.
   - Draw the detected lines on the original image.

## Conclusion

Lane detection is an essential part of the Advanced Driver-Assistance System (ADAS) for autonomous vehicles. In this project, we have used the OpenCV library in Python to implement a lane detection system. We have used the Canny edge detection algorithm to detect the edges of the lane lines and the Hough transform algorithm to detect the lines. Finally, we have drawn the detected lines on the original image.

## Project Files

- **Lane Guard.ipynb**: A Python notebook that can be run on Jupyter.
- **Data Set**: Contains the test and training images. These images need to be downloaded, and their paths in the code must be updated accordingly.

Contributing
We welcome contributions! Please read our contributing guidelines for more details.

Feel free to modify this description to better fit your project's specifics.

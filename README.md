# EX09 Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
## Step1:
Apply the dilation operation on the image using cv2.dilate() with the same structuring element. Dilation will increase the size of the white regions (text) in the image, effectively reversing the effect of erosion

## Step2:
Initialize a blank image (100 pixels high and 400 pixels wide) using NumPy. The image should be a single-channel (grayscale) array filled with zeros (black).

## Step3:
Use OpenCV's cv2.putText() function to overlay the text "HYCINTH" on the blank image. Define the font style, position, font scale, color, and thickness for rendering the text.

## Step4:
Specify the size of the structuring element (e.g., 5x5 pixels) and create a rectangular structuring element using cv2.getStructuringElement(). This element will be used for the morphological operations.

## Step5:
Apply the erosion operation on the image using cv2.erode() with the defined structuring element. Erosion will reduce the size of the white regions (text) in the image.
 
## Program:
```
Developed By: Bharathganesh S
Register No: 212222230022
```
### Import the necessary packages
``` 
import numpy as np
import cv2
import matplotlib.pyplot as plt
```
### Create the Text using cv2.putText
```
image = np.zeros((300, 600, 3), dtype="uint8")
text = "ASHWIN KUMAR S"
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, text, (50, 150), font, 2, (255, 255, 255), 3)
```
### Create the structuring element
``` 
kernel = cv2.getStructuringElement(cv2.MORPH_RECT, (5, 5))
plt.subplot(1, 3, 1)
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis("off")
```
### Erode the image
``` 
eroded_image = cv2.erode(image, kernel, iterations=1)
plt.subplot(1, 3, 2)
plt.imshow(eroded_image_rgb)
plt.title("Eroded Image")
plt.axis("off")


```
### Dilate the image
``` 
dilated_image = cv2.dilate(image, kernel, iterations=1)
plt.subplot(1, 3, 3)
plt.imshow(dilated_image_rgb)
plt.title("Dilated Image")
plt.axis("off")

```
## Output:

### Display the input Image

![image](https://github.com/user-attachments/assets/6615ff64-7060-4898-91ae-05351528655f)


### Display the Eroded Image

![image](https://github.com/user-attachments/assets/db145d30-1261-43b6-ad98-9b954ef3d43e)


### Display the Dilated Image

![image](https://github.com/user-attachments/assets/7365e815-b83f-4bd5-a67a-c1c2af5f3a12)

## Result
Thus the generated text image is eroded and dilated using python and OpenCV.

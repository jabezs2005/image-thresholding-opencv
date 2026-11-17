# Image Segmentation Using Thresholding Techniques in OpenCV

## Aim

To segment an image using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques using Python and OpenCV.

The program performs the following operations:

- Global Thresholding
- Adaptive Thresholding
- Otsu's Thresholding

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## Algorithm

### Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:

Load the input image using OpenCV.

### Step 3:

Convert the input image into grayscale format.

### Step 4: Global Thresholding

- Select a fixed threshold value.
- Apply thresholding to separate foreground and background pixels.
- Display the thresholded image.

### Step 5: Adaptive Thresholding

- Compute threshold values for small regions of the image.
- Apply Adaptive Mean Thresholding.
- Apply Adaptive Gaussian Thresholding.
- Display the segmented images.

### Step 6: Otsu's Thresholding

- Automatically determine the optimal threshold value.
- Apply Otsu's thresholding technique.
- Display the segmented image.

### Step 7:

Compare the results obtained from Global, Adaptive, and Otsu's thresholding methods.

## Program
```
Developed By:

NAME : JABEZ S 
REF NO : 212223040070


# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale

#READ THE IMAGE USING IMREAD
#CONVERT THE COLOR FROM BGR TO RGB
image_gray=cv2.imread("Duck.jpg",0)

# Use Global thresholding to segment the image
ret,thresh_dipt1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_dipt2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_dipt3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_dipt4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_dipt5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image

ret,thresh_dipt6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Use Otsu's method to segment the image 

thresh_dipt7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_dipt8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Display the results

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_dipt1,...................,thresh_dipt8]#LIST OUT ALL TILL thresh_dipt8 i.e from thresh_dipt_1 till thresh_dipt_8a
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```



## Output
<img width="267" height="634" alt="Screenshot 2026-11-17 at 8 51 52 AM" src="https://github.com/user-attachments/assets/5d640106-701c-468d-ade3-f73a80fcda6b" />

<img width="892" height="784" alt="Screenshot 2026-11-17 at 8 51 59 AM" src="https://github.com/user-attachments/assets/3a3b4463-aae3-400c-a3bf-ec9b115edd58" />


### Original Grayscale Image

- The grayscale version of the input image is displayed.
- Serves as the input for thresholding operations.

### Global Thresholding

- Original image is displayed.
- Thresholded image is displayed.
- A fixed threshold value is used for segmentation.
- Pixels are classified as foreground or background.

### Adaptive Thresholding

- Original image is displayed.
- Adaptive Mean Thresholded image is displayed.
- Adaptive Gaussian Thresholded image is displayed.
- Threshold values vary across different regions of the image.
- Suitable for images with uneven illumination.

### Otsu's Thresholding

- Original image is displayed.
- Otsu segmented image is displayed.
- Optimal threshold value is calculated automatically.
- Produces improved segmentation for bimodal histograms.


## Result

Thus, image segmentation is successfully performed using **Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding** techniques in OpenCV. 

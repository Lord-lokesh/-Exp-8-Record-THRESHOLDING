# Exp-8-Record-THRESHOLDING
# THRESHOLDING
# Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

Software Required

Anaconda - Python 3.7

OpenCV

# Algorithm

Step1:

Load the necessary packages.

Step2:

Read the Image and convert to grayscale.

Step3:

Use Global thresholding to segment the image.

Step4:

Use Adaptive thresholding to segment the image.

Step5:

Use Otsu's method to segment the image and display the results.

# Program
Developed by

# NAME : LOKESH M
# REG NO : 212224230142

```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 2: Read the image and convert to grayscale
image = cv2.imread('breaking.jpg')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale

# Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')

# Step 3: Use Global Thresholding to segment the image
# Apply global thresholding with a threshold value of 127
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Step 4: Use Adaptive Thresholding to segment the image
# Apply adaptive thresholding using Gaussian method
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)


# Step 5: Use Otsu's method to segment the image
# Apply Otsu's method for optimal thresholding
_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)




# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show the plot
plt.tight_layout()
plt.show()

```

<img width="556" height="247" alt="image" src="https://github.com/user-attachments/assets/7363b51f-0070-4863-aa3c-74c135762113" />

<img width="1082" height="613" alt="image" src="https://github.com/user-attachments/assets/28f5741b-117e-4265-8a2a-013c3b1aab95" />

# Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.



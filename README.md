# Exp-5--Record-Implementation-of-Filters
# Santhosh V(212224230251)

## Aim

To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, and Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement.

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (`cv2`)
- NumPy
- Matplotlib

## Algorithm

### Step 1: Import Libraries
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2: Load the Image
Read the input image using `cv2.imread()`.

### Step 3: Convert Image
Convert the image from BGR to RGB format for proper display using Matplotlib.

### Step 4: Averaging Filter
- Apply the averaging filter using `cv2.blur()`.
- Reduce image noise by averaging neighboring pixel values.
- Display the filtered image.

### Step 5: Weighted Averaging Filter
- Create a custom weighted averaging kernel.
- Apply the filter using `cv2.filter2D()`.
- Display the filtered image.

### Step 6: Gaussian Filter
- Apply Gaussian smoothing using `cv2.GaussianBlur()`.
- Reduce noise using Gaussian-weighted pixel values.
- Display the filtered image.

### Step 7: Median Filter
- Apply median filtering using `cv2.medianBlur()`.
- Replace each pixel with the median value of its neighborhood.
- Display the filtered image.

### Step 8: Laplacian Sharpening Using Kernel
- Define a Laplacian sharpening kernel.
- Apply the kernel using `cv2.filter2D()`.
- Enhance image edges and fine details.
- Display the sharpened image.

### Step 9: Laplacian Operator
- Convert the original image into grayscale.
- Apply the Laplacian operator using `cv2.Laplacian()`.
- Detect edges and image details.
- Display the resulting image.

### Step 10: Display Results
Display the original image and all filtered images using Matplotlib in a grid layout for comparison.

## Program

**Developed By:** Santhose Arockiraj J

**Register Number:** 212224230248

**Program File:** `EXP5.ipynb`

### Step 1: Import Libraries and Apply Average Filter

```python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("my.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```

### Step 2: Weighted Average Filter

```python
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
image3=cv2.filter2D(image2,-1,kernel1)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```

### Step 3: Gaussian Blur

```python
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```

### Step 4: Median Blur

```python
median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```

### Step 5: Laplacian Kernel

```python
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```

### Step 6: Laplacian Operator

```python
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

## Output

### 1. Averaging Filter

- Averaging filter produces a blurred image by averaging neighboring pixels.

<img width="717" height="406" alt="download" src="https://github.com/user-attachments/assets/3e25bd88-9d71-4d08-9f21-56876c545301" />



### 2. Weighted Averaging Filter

- Weighted averaging provides a smoother result using a custom kernel.

<img width="533" height="300" alt="download" src="https://github.com/user-attachments/assets/dca2f0be-1cd2-4a29-9562-151251f2dd97" />



### 3. Gaussian Filter

- Gaussian filter reduces noise while preserving important image features.

<img width="516" height="300" alt="download" src="https://github.com/user-attachments/assets/7dc48aee-b0a1-489d-9679-547b903007f4" />



### 4. Median Filter

- Median filter removes salt-and-pepper noise effectively.
<img width="717" height="406" alt="download" src="https://github.com/user-attachments/assets/62e6cfea-fd97-40a5-b3b1-9826e50fcfd1" />



### 5. Laplacian Sharpening Using Kernel

- Laplacian kernel enhances edges and fine details.

<img width="516" height="300" alt="download" src="https://github.com/user-attachments/assets/2cd0e2b8-0cbb-4f09-9d65-bd234b6357c2" />


### 6. Laplacian Operator

- Laplacian operator detects edges clearly in grayscale.

<img width="516" height="300" alt="download" src="https://github.com/user-attachments/assets/f621f18a-cc84-4999-a3f7-f72f4e2daae9" />



## Result

Thus, various smoothing and sharpening filters were successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and fine details for better image enhancement and feature extraction.

# Image Smoothing and Sharpening Using OpenCV

## Aim

To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

---

## The program performs the following operations:

- Read and display an input image  
- Apply Averaging filter  
- Apply Weighted Averaging filter  
- Apply Gaussian filter  
- Apply Median filter  
- Apply Laplacian sharpening using kernel  
- Apply Laplacian operator  
- Display all outputs for comparison  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image (e.g., `image.jpg`).

### Step 3:
Convert the image from BGR to RGB format for display.

### Step 4:
Apply Averaging Filter using `cv2.blur()`.

### Step 5:
Apply Weighted Averaging Filter using a custom kernel with `cv2.filter2D()`.

### Step 6:
Apply Gaussian Filter using `cv2.GaussianBlur()`.

### Step 7:
Apply Median Filter using `cv2.medianBlur()`.

### Step 8:
Apply Laplacian Sharpening using Kernel with `cv2.filter2D()`.

### Step 9:
Convert image to grayscale and apply Laplacian Operator using `cv2.Laplacian()`.

### Step 10:
Display all filtered images using a grid layout for comparison.
--- 

## Program

---

##  Developed By

- **Name:** DHASHVANTH B
- **Register No:** 212224230064

---
### 1. Averaging Filter

```

import cv2
import matplotlib.pyplot as plt

img = cv2.imread('image2.jpg')
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Apply Averaging Filter
averaging = cv2.blur(img, (5, 5))

plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(img)
plt.title("Original Image")
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(averaging)
plt.title("Averaging Filter")
plt.axis('off')

plt.show()

```

### 2. Weighted Averaging Filter

```

import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('image2.jpg')
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Define Weighted Kernel
kernel = np.array([[1, 2, 1],
                   [2, 4, 2],
                   [1, 2, 1]], dtype=np.float32) / 16

# Apply Weighted Averaging
weighted = cv2.filter2D(img, -1, kernel)

plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(img)
plt.title("Original Image")
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(weighted)
plt.title("Weighted Averaging Filter")
plt.axis('off')

plt.show()

```

### 3. Gaussian Filter

```

import cv2
import matplotlib.pyplot as plt

img = cv2.imread('image2.jpg')
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Apply Gaussian Filter
gaussian = cv2.GaussianBlur(img, (5, 5), 0)

plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(img)
plt.title("Original Image")
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(gaussian)
plt.title("Gaussian Filter")
plt.axis('off')

plt.show()

```

### 4. Median Filter
```

import cv2
import matplotlib.pyplot as plt

img = cv2.imread('image2.jpg')
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Apply Median Filter
median = cv2.medianBlur(img, 5)

plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(img)
plt.title("Original Image")
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(median)
plt.title("Median Filter")
plt.axis('off')

plt.show()

```

### 5. Laplacian Sharpening Using Kernel

```

import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('image2.jpg')
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Define Laplacian Kernel
kernel = np.array([[0, -1, 0],
                   [-1, 5, -1],
                   [0, -1, 0]])

# Apply Laplacian Sharpening
sharpened = cv2.filter2D(img, -1, kernel)

plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(img)
plt.title("Original Image")
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(sharpened)
plt.title("Laplacian Sharpening")
plt.axis('off')

plt.show()

```

### 6. Laplacian Operator

```

import cv2
import matplotlib.pyplot as plt

img = cv2.imread('image2.jpg', cv2.IMREAD_GRAYSCALE)

# Apply Laplacian Operator
laplacian = cv2.Laplacian(img, cv2.CV_64F)

# Convert to absolute values
laplacian = cv2.convertScaleAbs(laplacian)

plt.figure(figsize=(10, 5))

plt.subplot(1, 2, 1)
plt.imshow(img, cmap='gray')
plt.title("Original Grayscale Image")
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(laplacian, cmap='gray')
plt.title("Laplacian Operator")
plt.axis('off')

plt.show()

```



##  Output

### Smoothing Filters

- Averaging filter produces blurred image
<img width="717" height="513" alt="download" src="https://github.com/user-attachments/assets/e292292c-b915-4cfc-8c8e-c3e1dabc9ebf" />



- Weighted averaging provides smoother result with less distortion
<img width="533" height="377" alt="download" src="https://github.com/user-attachments/assets/d9c67e32-87bd-473b-bb87-ec3830832074" />



- Gaussian filter preserves edges better while reducing noise  
<img width="516" height="377" alt="download" src="https://github.com/user-attachments/assets/554714a8-eb2f-4084-b07e-72316ab428cb" />



- Median filter removes salt-and-pepper noise effectively  
<img width="717" height="513" alt="download" src="https://github.com/user-attachments/assets/581e68ab-04cc-43fb-ae51-11fdff973375" />




###  Sharpening Filters

- Laplacian kernel enhances edges and fine details  
<img width="516" height="377" alt="download" src="https://github.com/user-attachments/assets/3cc8c0c5-d888-4f60-9e2c-f822a4ef57b9" />



- Laplacian operator detects edges clearly in grayscale  
<img width="516" height="377" alt="download" src="https://github.com/user-attachments/assets/142ab04d-e90f-4691-bcbc-7e6dd4954e8c" />


---

##  Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.

# Edge-Detection Using OpenCV
## NAME: SANTHOSH KUMAR A
## REG NO: 212224230250
## Aim

To perform edge detection using Sobel, Roberts, Prewitt, Laplacian, and Canny edge detectors.

---

## Software Required

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

## ⚙️ Algorithm

### Step 1:
Import all the necessary modules for the program.

### Step 2:
Load an image using `cv2.imread()`.

### Step 3:
Convert the image to grayscale.

### Step 4:
Apply **Sobel operator** using OpenCV to detect edges.

### Step 5:
Apply **Prewitt operator** using custom kernels.

### Step 6:
Apply **Roberts operator** using custom kernels.

### Step 7:
Apply **Laplacian operator** using OpenCV.

### Step 8:
Apply **Canny edge detector** using OpenCV.

### Step 9:
Display all edge-detected images for comparison.

# Program :
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
```
# Load image
image = cv2.imread("E:\Digital Image\Exp-6.jpg")  # replace with your path
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```
```
sobel_x = cv2.Sobel(gray, cv2.CV_64F, 1, 0, ksize=5)
sobel_y = cv2.Sobel(gray, cv2.CV_64F, 0, 1, ksize=5)
sobel = cv2.magnitude(sobel_x, sobel_y)
```
```
prewitt_x = np.array([[1, 0, -1],
                      [1, 0, -1],
                      [1, 0, -1]])
```
```
prewitt_y = np.array([[1, 1, 1],
                      [0, 0, 0],
                      [-1, -1, -1]])
```
```
prewitt_x_edge = cv2.filter2D(gray, -1, prewitt_x)
prewitt_y_edge = cv2.filter2D(gray, -1, prewitt_y)
prewitt = cv2.magnitude(prewitt_x_edge.astype(np.float32),
                        prewitt_y_edge.astype(np.float32))
```
```
roberts_x = np.array([[1, 0],
                      [0, -1]])

roberts_y = np.array([[0, 1],
                      [-1, 0]])
```
```
roberts_x_edge = cv2.filter2D(gray, -1, roberts_x)
roberts_y_edge = cv2.filter2D(gray, -1, roberts_y)
roberts = cv2.magnitude(roberts_x_edge.astype(np.float32),
                        roberts_y_edge.astype(np.float32))
```
```

laplacian = cv2.Laplacian(gray, cv2.CV_64F)
```
```

canny = cv2.Canny(gray, 50, 150)
```
```

plt.figure(figsize=(12, 10))

plt.subplot(2, 3, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
print("SANTHOSH KUMAR A")
print("212224230250")
plt.title("Original")
plt.axis("off")
```
```
plt.subplot(2, 3, 2)
plt.imshow(sobel, cmap='gray')
print("SANTHOSH KUMAR A")
print("212224230250")
plt.title("Sobel")
plt.axis("off")
```
```
plt.subplot(2, 3, 3)
plt.imshow(prewitt, cmap='gray')
print("SANTHOSH KUMAR A")
print("212224230250")
plt.title("Prewitt")
plt.axis("off")
```
```
plt.subplot(2, 3, 4)
plt.imshow(roberts, cmap='gray')
print("SANTHOSH KUMAR A")
print("212224230250")
plt.title("Roberts")
plt.axis("off")
```
```
plt.subplot(2, 3, 5)
plt.imshow(laplacian, cmap='gray')
print("SANTHOSH KUMAR A")
print("212224230250")
plt.title("Laplacian")
plt.axis("off")
```
```
plt.subplot(2, 3, 6)
plt.imshow(canny, cmap='gray')
print("SANTHOSH KUMAR A")
print("212224230250")
plt.title("Canny")
plt.axis("off")
```
```
plt.tight_layout()
plt.show()
```



## Output 
### Original Image 
<img width="567" height="407" alt="image" src="https://github.com/user-attachments/assets/083269a9-0761-4a05-9e05-75102e04aa87" />


###  Sobel Edge Detector
- Detects edges in horizontal and vertical directions  
- Produces gradient-based edge map

  <img width="503" height="298" alt="image" src="https://github.com/user-attachments/assets/1c785c48-a3e4-46f4-b6d3-ab6c994c12e4" />


###  Prewitt Edge Detector
- Similar to Sobel but simpler kernel  
- Detects directional edges
  
<img width="491" height="303" alt="image" src="https://github.com/user-attachments/assets/5667f323-2cdb-4ab6-b2b9-2e88f53d27ee" />

###  Roberts Edge Detector
- Detects edges using diagonal gradients  
- Sensitive to noise  

<img width="472" height="323" alt="image" src="https://github.com/user-attachments/assets/f0900b74-4e3c-4076-b4af-d5bc09e5a464" />


###  Laplacian Edge Detector
- Detects edges using second-order derivatives  
- Highlights rapid intensity changes  

<img width="521" height="329" alt="image" src="https://github.com/user-attachments/assets/0dcf4f68-812e-45a1-be0f-acab6486ee3a" />

###  Canny Edge Detector
- Multi-stage edge detection  
- Produces clean and thin edges  

<img width="526" height="313" alt="image" src="https://github.com/user-attachments/assets/e21175ed-0685-4a52-a06a-2de7cc9b83df" />

### Figure Size
<img width="486" height="111" alt="image" src="https://github.com/user-attachments/assets/883f1151-441b-4a3f-b751-675881384f6f" />


## Result

Thus, edges are successfully detected using Sobel, Prewitt, Roberts, Laplacian, and Canny edge detection techniques. Each method highlights edges differently based on gradient and intensity variations, improving feature extraction and analysis.

# Image Capture and Video Processing Using OpenCV

## Name       :  MURALIDHARAN M
## Register No:  212223040120


---

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file  
2. Display the video  
3. Display the video by resizing the window  
4. Rotate and display the video  

---

## 🛠️ Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  

---

## ⚙️ Algorithm

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture frames continuously from the webcam.

### Step 3:
Save a frame as a JPG image using `cv2.imwrite()`.

### Step 4:
Display the live video stream using `cv2.imshow()`.

### Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

---

## 💻 Program

### Developed By:
**Name       :  MURALIDHARAN M
**Register No:  212223040120

import cv2
import matplotlib.pyplot as plt
import numpy as np

img = cv2.imread('captured_frame.jpg')

if img is None:
    print("Error: Image 'captured_frame.jpg' not found! Creating fallback image.")
    img = np.zeros((300, 300, 3), dtype=np.uint8)
    cv2.putText(img, 'Exp 2 Test', (50, 150), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 2)

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
gray_img = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
blurred_img = cv2.GaussianBlur(gray_img, (5, 5), 0)
edges = cv2.Canny(blurred_img, threshold1=100, threshold2=200)

cv2.imwrite('edges_detected.jpg', edges)
print("Processed edge image saved as 'edges_detected.jpg'.")

fig, axes = plt.subplots(1, 3, figsize=(15, 5))

axes[0].imshow(img_rgb)
axes[0].set_title('Original Image (RGB)')
axes[0].axis('off')

axes[1].imshow(gray_img, cmap='gray')
axes[1].set_title('Grayscale Image')
axes[1].axis('off')

axes[2].imshow(edges, cmap='gray')
axes[2].set_title('Canny Edges')
axes[2].axis('off')

plt.tight_layout()
plt.show()


---

## Output

### i) Write the frame as JPG image
<img width="488" height="392" alt="WhatsApp Image 2026-11-06 at 12 57 46 AM" src="https://github.com/user-attachments/assets/c64b48ca-8156-44eb-8af3-361f08026354" />


### ii) Display the video
<img width="497" height="370" alt="WhatsApp Image 2026-11-06 at 12 58 04 AM" src="https://github.com/user-attachments/assets/76825564-7730-4ee6-86ee-1ee872514daf" />



### iii) Display the video by resizing the window
<img width="257" height="372" alt="WhatsApp Image 2026-11-06 at 12 58 16 AM" src="https://github.com/user-attachments/assets/7490ec8b-792c-44df-a159-0515036c4fd3" />



### iv) Rotate and display the video
<img width="287" height="371" alt="WhatsApp Image 2026-11-06 at 12 58 29 AM" src="https://github.com/user-attachments/assets/3b0f4273-ff07-4421-bd04-22fa40427612" />


---


## Result:
Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.


         


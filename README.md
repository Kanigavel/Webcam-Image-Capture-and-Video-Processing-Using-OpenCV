# Image Capture and Video Processing Using OpenCV

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
## Name: Kanigavel M
### Register No: 212224240070

~~~
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret: cv2.imwrite("captured_frame.jpg", frame)
cap.release()
captured_image = cv2.imread("captured_frame.jpg")
plt.imshow(captured_image[:, :, ::-1]) 
plt.title("Captured Frame")
plt.axis("off") 
plt.show()
cap = cv2.VideoCapture(0)
for i in range(50): 
    ret, frame = cap.read()
    if not ret:
        break
frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
clear_output(wait=True)
plt.imshow(frame_rgb)
plt.axis("off")
plt.show()
time.sleep(0.05)

~~~
~~~~
for i in range(50): 
    ret, frame = cap.read()
    if not ret:
        break
resized_frame = cv2.resize(frame, (100, 150))
frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
clear_output(wait=True)
plt.imshow(frame_rgb)
plt.axis("off")
plt.show()
time.sleep(0.05)
~~~~
~~~
for i in range(50): 
    ret, frame = cap.read()
    if not ret:
        break
rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
clear_output(wait=True)
plt.imshow(frame_rgb)
plt.axis("off")
plt.show()
time.sleep(0.05)
~~~
## Output

### i) Write the frame as JPG image and  Display the video
<img width="640" height="415" alt="image" src="https://github.com/user-attachments/assets/4333e2c2-c215-4ac2-93eb-3a21a43c133b" />


### ii) Display the video by resizing the window
<img width="448" height="413" alt="image" src="https://github.com/user-attachments/assets/32ba97ee-c4b1-4b73-a1c0-2ca09fb67ae4" />


### iii) Rotate and display the video
<img width="552" height="410" alt="image" src="https://github.com/user-attachments/assets/ae153b89-5b44-4bcb-835e-61165db50869" />


---

## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.

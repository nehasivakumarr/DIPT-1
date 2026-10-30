# Image-Handling-and-Pixel-Transformations-Using-OpenCV
## AIM:
Write a Python program using OpenCV that performs the following tasks:
- Read and Display an Image.
- Adjust the brightness of an image.
- Modify the image contrast.
- Generate a third image using bitwise operations.
## Software Required:
Anaconda - Python 3.7
Jupyter Notebook (for interactive development and execution)
## Algorithm:
### Step 1:
Load an image from your local directory and display it.

### Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

### Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.
Display the original, brighter, and darker images.

### Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).
Display the original, lower contrast, and higher contrast images.

### Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels

## Program Developed By:
- Name: NEHA S

- Register Number: 21222510030
  
## Program:
### Step1:
#### Load an image from your local directory and display it.
```
import cv2
import matplotlib.pyplot as plt
# Read the image using OpenCV
img = cv2.imread('NEHA IMAGE.jpeg', cv2.IMREAD_COLOR)
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
```
<img width="442" height="508" alt="image" src="https://github.com/user-attachments/assets/4b5fe656-698c-42a6-8edf-3d827c5166aa" />

### Step2:

o Draw a line from the top-left to the bottom-right of the image.

o Draw a circle at the center of the image. 

o Draw a rectangle around a specific region of interest in the image. 

o Add the text "OpenCV Drawing" at the top-left corner of the image.

### Draw a line from the top-left to the bottom-right of the image

```
# Load the image
image = cv2.imread('NEHA IMAGE.jpeg')
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
```
(1000, 750, 3)
```
# Draw a line from top-left to bottom-right
line_img = cv2.line(img_rgb, (0, 0), (767, 999), (0, 0, 0), 5) # cv2.line(image, start_point, end_point, color, thickness)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('on')  
plt.show()
```
<img width="433" height="531" alt="image" src="https://github.com/user-attachments/assets/9b713066-4d7a-433d-995e-b7eaa1811c3b" />

#### Draw a circle at the center of the image.
```
# Load the image
image = cv2.imread('NEHA IMAGE.jpeg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
```
(1000, 750, 3)
```
circle_img = cv2.circle(img_rgb,(400,300),250,(0,0,0),10) # cv2.circle(image, center, radius, color, thickness)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
```
<img width="363" height="507" alt="image" src="https://github.com/user-attachments/assets/2817e3a4-5349-4f41-82b8-fd5f2f9e0298" />

### Draw a rectangle around  the whole image
```
# Load the image
image = cv2.imread('NEHA IMAGE.jpeg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape
```
(1000, 750, 3)
```
# Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (740, 999), (0, 0, 0), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```
<img width="436" height="518" alt="image" src="https://github.com/user-attachments/assets/f343c135-648e-4b9f-b43f-f14d5367e322" />

### Add the text "212225100030" at the center of the image.

```
# Load the image
image = cv2.imread('NEHA IMAGE.jpeg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Add text to the image
text_img = cv2.putText(img_rgb, "212225100030", (300, 50), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 0, 0), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```
<img width="398" height="515" alt="image" src="https://github.com/user-attachments/assets/436f86f9-fcc9-4dad-9f69-b3acd52d71e9" />

### Step3:
o Convert the image from RGB to HSV and display it.
    
o Convert the image from RGB to GRAY and display it. 

o Convert the image from RGB to YCrCb and display it. 
    
o Convert the HSV image back to RGB and display it.

```
# Load the image
image = cv2.imread('NEHA IMAGE.jpeg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
```
(np.float64(-0.5), np.float64(749.5), np.float64(999.5), np.float64(-0.5))


<img width="346" height="507" alt="image" src="https://github.com/user-attachments/assets/604dfcaf-0530-4486-ad05-980f51aa1056" />

```
# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
# HSV Image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
```
(np.float64(-0.5), np.float64(749.5), np.float64(999.5), np.float64(-0.5))

<img width="360" height="517" alt="image" src="https://github.com/user-attachments/assets/be7c1232-3a94-40b1-801a-27ffc7470106" />

```
# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
# Grayscale Image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
```
(np.float64(-0.5), np.float64(749.5), np.float64(999.5), np.float64(-0.5))

<img width="327" height="490" alt="image" src="https://github.com/user-attachments/assets/6d793444-5da4-49db-8738-f19f46a53cd9" />

```
# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
# YCrCb Image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
```
(np.float64(-0.5), np.float64(749.5), np.float64(999.5), np.float64(-0.5))

<img width="383" height="512" alt="image" src="https://github.com/user-attachments/assets/1c9a1486-1664-4b9b-b54e-d66fcf3583d5" />

```
# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
```
(np.float64(-0.5), np.float64(749.5), np.float64(999.5), np.float64(-0.5))

<img width="335" height="500" alt="image" src="https://github.com/user-attachments/assets/78e2e892-0723-4169-aee9-3d51f2f1ba42" />

### Step4:
o Access and print the value of the pixel at coordinates (100, 100). 

o Modify the color of the pixel at (200, 200) to white.

```
# Modify a block of pixels (300x300) to white, starting from (200, 200)
image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499
# Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```
<img width="385" height="506" alt="image" src="https://github.com/user-attachments/assets/84623e19-ee50-49b8-bcfb-23b1848dad51" />

### Step5:
o Resize the original image to half its size and display it.

```
# Load the image
image = cv2.imread('NEHA IMAGE.jpeg')
image.shape
```
(1000, 750, 3)
```
# Resize the image to half its size
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)
# Convert BGR to RGB for displaying with Matplotlib
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape
```
(300, 384, 3)
```
# Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```
<img width="616" height="512" alt="image" src="https://github.com/user-attachments/assets/d4cf8051-8f5c-4d3b-8a60-d2ce281310ee" />

### Step6:
o Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.

```
# Load the image
image = cv2.imread('NEHA IMAGE.jpeg')
image.shape
```
(1000, 750, 3)

```
# Crop a 300x300 region starting from (50, 50)
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
# Convert BGR to RGB for displaying with Matplotlib
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
# Display the cropped region (ROI)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```
<img width="485" height="515" alt="image" src="https://github.com/user-attachments/assets/4c6c8e47-35fd-4302-91d1-dfbfe73f4eb5" />

### Step7:
o Flip the original image horizontally and display it. 

o Flip the original image vertically and display it.

```
# Load the image
image = cv2.imread('NEHA IMAGE.jpeg')
# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)
# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
```
(np.float64(-0.5), np.float64(749.5), np.float64(999.5), np.float64(-0.5))

<img width="361" height="510" alt="image" src="https://github.com/user-attachments/assets/378569f1-1bfe-45aa-b54d-34f156018f87" />

```
# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)
# Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
# Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```
(np.float64(-0.5), np.float64(749.5), np.float64(999.5), np.float64(-0.5))

<img width="368" height="483" alt="image" src="https://github.com/user-attachments/assets/815287ad-496c-45ce-bb04-90d96c6cd96d" />

### Step8:
o Save the final modified image to your local directory.










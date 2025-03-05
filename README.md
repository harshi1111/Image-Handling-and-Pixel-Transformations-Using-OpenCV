# Image-Handling-and-Pixel-Transformations-Using-OpenCV 

## AIM:
Write a Python program using OpenCV that performs the following tasks:

1) Read and Display an Image.  
2) Adjust the brightness of an image.  
3) Modify the image contrast.  
4) Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

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
- **Name:** HARSHITHA V 
- **Register Number:** 212223230074

  ### Ex. No. 01

#### 1. Read the image ('Eagle_in_Flight.jpg') using OpenCV imread() as a grayscale image.
```python
import cv2
image_gray = cv2.imread('Eagle_in_Flight.jpg', cv2.IMREAD_GRAYSCALE)
```

#### 2. Print the image width, height & Channel.
```python
height, width = image_gray.shape  
channels = 1  
print(f"Width: {width}, Height: {height}, Channels: {channels}")
```

#### 3. Display the image using matplotlib imshow().
```python
import matplotlib.pyplot as plt
plt.imshow(image_gray, cmap='gray')
plt.axis('off')
plt.show()
```

#### 4. Save the image as a PNG file using OpenCV imwrite().
```python
cv2.imwrite(r"C:\Users\admin\Downloads\Eagle_in_Flight.png", image_gray)
```

#### 5. Read the saved image above as a color image using cv2.cvtColor().
```python
image_color = cv2.cvtColor(cv2.imread(r"C:\Users\admin\Downloads\Eagle_in_Flight.png"), cv2.COLOR_BGR2RGB)
```

#### 6. Display the Colour image using matplotlib imshow() & Print the image width, height & channel.
```python
import cv2
import matplotlib.pyplot as plt

# Read the original color image, not the grayscale one
image_color = cv2.imread(r"C:\Users\admin\Downloads\Eagle_in_Flight.jpg", cv2.IMREAD_COLOR)
image_rgb = cv2.cvtColor(image_color, cv2.COLOR_BGR2RGB)  # Convert BGR to RGB for correct display

# Display the image
plt.imshow(image_rgb)
plt.axis('off')
plt.show()

# Print width, height & channels
height, width, channels = image_color.shape
print(f"Width: {width}, Height: {height}, Channels: {channels}")

```

#### 7. Crop the image to extract any specific (Eagle alone) object from the image.
```python
cropped_image = image_rgb[100:500, 200:600]  
plt.imshow(cropped_image)
plt.axis('off')
plt.show()

```

#### 8. Resize the image up by a factor of 2x.
```python
# Resize the image by a factor of 2x
height, width = image_rgb.shape[:2]
resized_image = cv2.resize(image_rgb, (width * 2, height * 2))

# Display the resized image
plt.imshow(resized_image)
plt.axis('off')
plt.show()
```

#### 9. Flip the cropped/resized image horizontally.
```python
# Flip the image horizontally
flipped_image = cv2.flip(resized_image, 1)

# Display the flipped image
plt.imshow(flipped_image)
plt.axis('off')
plt.show()
```

#### 10. Read in the image ('Apollo-11-launch.jpg').
```python
image = cv2.imread('Apollo-11-launch.jpg', cv2.IMREAD_COLOR)
```

#### 11. Add the following text to the dark area at the bottom of the image (centered on the image):
```python
text = "Apollo 11 Saturn V Launch, July 16, 1969"
font_face = cv2.FONT_HERSHEY_PLAIN
font_scale = 2
thickness = 2
color = (255, 255, 255)

text_size = cv2.getTextSize(text, font_face, font_scale, thickness)[0]
text_x = (image.shape[1] - text_size[0]) // 2
text_y = image.shape[0] - 50

cv2.putText(image, text, (text_x, text_y), font_face, font_scale, color, thickness)
```

#### 12. Draw a magenta rectangle that encompasses the launch tower and the rocket.
```python
rect_color = (255, 0, 255)  # Magenta in BGR
cv2.rectangle(image, (x1, y1), (x2, y2), rect_color, 2)
```

#### 13. Display the final annotated image.
```python
rect_color = (255, 0, 255)  # Magenta in BGR
top_left = (250, 100)   # Adjust as needed
bottom_right = (550, 700)  # Adjust as needed

cv2.rectangle(image, top_left, bottom_right, rect_color, 3)
```

#### 14. Read the image ('Boy.jpg').
```python
# YOUR CODE HERE
```

#### 15. Adjust the brightness of the image.
```python
# Create a matrix of ones (with data type float64)
# matrix_ones = 
# YOUR CODE HERE
```

#### 16. Create brighter and darker images.
```python
img_brighter = cv2.add(img, matrix)
img_darker = cv2.subtract(img, matrix)
# YOUR CODE HERE
```

#### 17. Display the images (Original Image, Darker Image, Brighter Image).
```python
# YOUR CODE HERE
```

#### 18. Modify the image contrast.
```python
# Create two higher contrast images using the 'scale' option with factors of 1.1 and 1.2 (without overflow fix)
matrix1 = 
matrix2 = 
# img_higher1 = 
# img_higher2 = 
# YOUR CODE HERE
```

#### 19. Display the images (Original, Lower Contrast, Higher Contrast).
```python
# YOUR CODE HERE
```

#### 20. Split the image (boy.jpg) into the B,G,R components & Display the channels.
```python
# YOUR CODE HERE
```

#### 21. Merged the R, G, B , displays along with the original image
```python
# YOUR CODE HERE
```

#### 22. Split the image into the H, S, V components & Display the channels.
```python
# YOUR CODE HERE
```
#### 23. Merged the H, S, V, displays along with original image.
```python
# YOUR CODE HERE
```

## Output:
- **i)** Read and Display an Image.  
- **ii)** Adjust Image Brightness.  
- **iii)** Modify Image Contrast.  
- **iv)** Generate Third Image Using Bitwise Operations.

## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.

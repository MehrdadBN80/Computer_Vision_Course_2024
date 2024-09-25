# Computer Vision Assignment - First Assignment  
**Winter 2023**  
**Shahid Beheshti University**  

Welcome to the first assignment for the Computer Vision course at Shahid Beheshti University. This assignment is crafted to enhance your understanding of image processing and computer vision concepts through practical exercises involving color spaces, image transformations, and the application of theoretical knowledge from the course.

## Assignment Overview  

### Exercise 1: Luminance vs. Brightness (5 points)  
- Conduct research on the concepts of **Luminance** and **Brightness**.  
- Explain how these two concepts differ and provide your interpretation of the provided image.  
- Discuss the relationship between luminance and brightness in the context of the image.  

### Exercise 2: Color Conversion (10 points)  
Given the RGB color \( \text{COLOR} = (251, 151, 51) \):  
1. Convert this color to **CMYK** representation (2 points).  
2. Convert it to **YIQ** color space (2 points).  
3. Use the transformation matrix to convert it to **YCbCr** (2 points).  
4. Research and briefly explain the use cases of each color space (CMYK, YIQ, YCbCr). Compare their advantages and discuss when one is more effective than another (4 points).  

### Exercise 3: Probability Transformation (5 points)  
- Given an image with intensity values \( r \) in the range [0,1] with the probability distribution \( p_r(r) \) shown in the provided plot, transform the intensity levels such that the resulting distribution follows \( p_z(z) \) (assuming continuous values).  
- Derive the transformation that performs this mapping using \( r \) and \( z \).  

### Exercise 4: Image Histogram Operations (10 points)  
1. Apply **Histogram Equalization** on the provided grayscale image with intensity levels in the range [0,7]. Display the final image and explain the steps taken (5 points).  
2. Perform **Bit Plane Slicing** and display the result (3 points).  
3. Enhance the contrast of the image and show the result (2 points).  

## Computer-Based Questions (80 points)  
The goal of this section is to familiarize students with image manipulation using Python libraries like OpenCV, covering the topics discussed up to the third slide of the course.

### Basic Image Manipulations (20 points)  
- a) Read and display **Image 1**.  
- b) Display the RGB channels of the input image.  
- c) Convert the image to **grayscale** and **binary** without using built-in functions.  
- d) Convert the image's RGB space to **HSV** without using built-in functions.  
- e) Compare your HSV conversion with OpenCV's `cvtColor` function.  
- f) Investigate and implement red color extraction from the image using HSV.  

### Histogram Matching (5 points)  
- Implement histogram matching for **Image 2.1** to match the histogram of **Image 2.2**.  

### Filtering Comparison (15 points)  
- a) Apply a **3x3 average filter** twice, a **9x9 average filter**, and a **5x5 Gaussian filter** to an image. Compare the histograms of the resulting images and explain if any of the filters are equivalent.  
- b) If none of the filters are equivalent, find an alternative filter that achieves the same effect as two consecutive **3x3 average filters**.  
- c) Compare the filtered images using **PSNR** and discuss the implications of the results.  

### Manual Histogram Equalization (7 points)  
- Implement histogram equalization without using OpenCV or Pillow libraries for **Image 4**. Compare the result with that obtained from built-in libraries.  

### Noise Removal (3 points)  
- Remove noise from **Image 5** as effectively as possible. Explain your approach.  

### Unsharp Masking (10 points)  
- Implement **Unsharp Masking** on a chosen image. Generate a blurred version of the image, subtract it from the original, and add back the result with an appropriate coefficient to sharpen the image.  

### Star Detection (15 + 5 points)  
- Detect stars in the provided 8 images of the night sky. Your program should:  
  - Count the number of stars visible to the human eye.  
  - Print the coordinates of at least one detected star.  
  - Visualize the contours of the detected stars in the original image.  

# Computer Vision Assignment - Second Assignment  
**Instructor: Dr. Ahmad Mahmoudi Aznaveh**  

This assignment builds on the foundations of image processing and computer vision, covering edge detection, corner detection, feature extraction, and object detection. You will explore classical techniques, such as filtering and feature matching, and implement a CNN-based model for object detection.

## Assignment Overview  

### Theoretical Questions (20 points)  

#### Problem 1: Kernel Analysis (5 points)  
**Objective**: Analyze the effects of different kernels (filters) on an image (e.g., the Lena image).  
- Identify the purpose and effect of four different kernels.  
- Explain the differences between these kernels and their applications in image processing.  
- Match each kernel to its corresponding output image.  

#### Problem 2: Laplacian vs. Sobel and Canny (5 points)  
**Objective**: Compare edge detection filters.  
- Provide three reasons why the **Laplacian filter** is less effective than **Sobel** and **Canny** for edge detection.  

#### Problem 3: Harris Corner Detection (10 points)  
**Objective**: Understand the Harris Corner Detection algorithm.  
- Explain the **Harris Corner Detection** process.  
- Analyze the relationship between matrix \( M \), and image gradients \( I_x \) and \( I_y \).  
- Calculate the **Corner Response Measure** and determine whether a region in the image is an edge, corner, or smooth area.  

#### Problem 4: Canny Edge Detection (10 points)  
**Objective**: Implement the **Canny Edge Detector**.  
- Apply Canny edge detection with custom parameters (not using Gaussian and Sobel filters).  
- Provide the final output image and explain each step of the process.  

---

### Practical Coding Questions (80 points)  

#### Problem 1: Image Enhancement and Edge Detection (12 points)  
**Objective**: Improve image resolution and apply edge detection.  
- Increase the resolution of an image using an appropriate method.  
- Extract edges from two provided images using the **Sobel** edge detector.  
- Enhance details in the images.  
- Implement automatic thresholding in the Canny edge detection algorithm based on the input image.  

#### Problem 2: Road Lane Detection (15 points)  
**Objective**: Detect road lane lines from driver's POV images.  
- Use classical image processing techniques (e.g., **Hough Transform**) to detect road lane lines in the provided images.  

#### Problem 3: Feature Matching Using HOG and SIFT (23 points)  
**Objective**: Match features using **HOG** and **SIFT** algorithms.  
- Use **HOG (Histogram of Oriented Gradients)** and **SIFT (Scale-Invariant Feature Transform)** to detect matching features between a reference image and cropped images.  
- For each cropped image, determine if it is part of the original image and highlight the matched section.  
- Discuss the advantages of **SIFT** over **HOG**, and the types of transformations each algorithm can handle.  

---

### Implementation Part

#### Q1: Image Processing Techniques Using OpenCV, NumPy, and Matplotlib  
This question involves applying various image processing techniques, including filtering, sharpening, and edge detection, using Python libraries like OpenCV.  

Key Sections:  

1. **Image Filtering and Sharpening**  
   - Load and display the original image.  
   - Apply sharpening filters (basic, simple, strong) to enhance details.  
   - Use **Sobel** and **Laplacian** filters for edge detection.  
   - Implement **unsharp masking** for added sharpness.  
   - Display all processed images for comparison.  

2. **Edge Detection**  
   - Apply **Sobel** filters to detect horizontal and vertical edges in grayscale images.  
   - Use **Laplacian filtering** with thresholding to enhance edge visibility.  
   - Implement **Canny edge detection** with automatic thresholding.  
   - Display original and filtered images side-by-side.  

3. **Image Enhancement**  
   - Apply **Gaussian blur** to reduce noise in two color images.  
   - Use sharpening filters and enhance contrast through scaling.  
   - Perform **histogram equalization** in the YUV color space to improve brightness and contrast.  
   - Display the original, blurred, sharpened, and equalized images for comparison.  

#### Q2: Line Detection Using Hough Transform  
This question focuses on detecting and drawing lines in images using OpenCV.  

Key Steps:  

1. **Image Loading and Visualization**  
   - Load and display images using `matplotlib.image`.  

2. **Region of Interest (ROI)**  
   - Define a polygonal region of interest to focus on specific areas of the image.  
   - Use masking techniques to isolate this region.  

3. **Edge Detection**  
   - Convert images to grayscale.  
   - Apply **Canny edge detection** to identify edges within the cropped region.  

4. **Line Detection**  
   - Use **Hough Transform** to detect lines in the processed edge image.  
   - Adjust parameters like `rho`, `theta`, `threshold`, `minLineLength`, and `maxLineGap` to optimize line detection.  

5. **Line Drawing**  
   - Draw the detected lines on the original image using a specified color and thickness.  

6. **Batch Processing**  
   - Process multiple images in a loop and display the results.  

#### Q3: Feature Matching Using SIFT and HOG  
Key Steps:  

1. **Template Matching Using SIFT and HOG**  
   - Load the original image and several cropped templates.  
   - Convert images to grayscale for feature detection.  

2. **SIFT Detection and Matching**  
   - Detect keypoints and compute descriptors for both the original and cropped images using **SIFT**.  
   - Match descriptors using **BFMatcher** and **FLANN-based matcher**.  
   - Use Lowe's ratio test to filter good matches.  
   - Find homography to draw bounding boxes around detected features.  
   - Display the cropped image, feature matches, and the original image with bounding boxes.  

3. **HOG Template Matching**  
   - Compute **HOG features** for both target and template images.  
   - Slide a window across the target image to compute dot products with the HOG features of the template to find the best match.  
   - Display the original image with the matched template.  

4. **Advantages of SIFT**  
   - **Robustness**: Invariant to scale, rotation, and translation.  
   - **High Accuracy**: Detects distinctive features that are repeatable across images.  

5. **Advantages of HOG**  
   - **Efficiency**: HOG is simpler and faster for feature extraction.  
   - **Shape Detection**: It captures the shape and structure of objects by analyzing gradient orientations.  

6. **Resilience to Transformations**  
   - **SIFT**: Handles changes in scale, rotation, lighting, and perspective distortions.  
   - **HOG**: Effective for shape detection but less robust to significant transformations like rotation or scale changes.  

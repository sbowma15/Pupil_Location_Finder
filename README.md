Pupil Location Finder

This Python program is designed to find the location of a pupil in an eye image using pixel values and specific filters/kernels to provide the necessary output for locating the circular pupil. The process involves reading in an image, converting it to grayscale for better pixel value analysis, and applying a Gaussian Blur function to smooth the image. The smoothed image is crucial for isolating the pupil, which usually has a high-contrast area.

Smoothing
The program reads the image from a hardcoded path and converts it to grayscale (im). A Gaussian blur with a 91x91 block is applied (dst) to achieve a smoother image.

Edge Detection using Sobel Filter
Sobel filters are used for horizontal and vertical convolutions to detect edges. The gradient is calculated, and pixel values are normalized for accurate edge detection. The result is displayed as the maximum gradient image.

Spatial Filter
A spatial filter is applied to the gradient image (grad). Methods iterate through pixel locations, comparing them within a given block size to find the most intense pixels. The resulting image (eye_rim) holds information for locating the pupil's center.

Brightest Pixel Finding
The program identifies the brightest pixel in eye_rim to determine the pupil's center.

Overlapping Mask with Original Image
A circular cut-out of the pupil is created by iterating through image dimensions and using a radius of 80 pixels. Pixels outside this range are set to 0, effectively removing them from the original image.

Display Final Image
The modified image, showing only the circular pupil, is displayed.

Usage
Ensure you have Python installed.
Copy the code into a file (e.g., pupil_location_finder.py).
Provide the image path in the cv2.imread function.
Run the script.
Note: Adjustments to parameters such as block size, radii, and pixel values can be made based on specific use cases.

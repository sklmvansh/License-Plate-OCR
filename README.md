## **License Plate Detection using OpenCV and Tesseract OCR**

This notebook explores how to detect license plates in vehicle images and extract their alphanumeric text using **image processing** and **Optical Character Recognition (OCR) techniques**.

We are going to take the following approach:
1. Problem Definition
2. Data
3. Approach
4. Modelling
5. Experimentation

#### 1. **Problem Definition**
In the statement:
> Given an image of a vehicle, can we automatically detect and extract the license plate number from the image using computer vision and OCR techniques?

#### 2. **Data**
Images of vehicles with visible license plates are used as input for the OCR pipeline. The dataset includes a mixture of plate styles, fonts, and environments to test the robustness of the detection algorithm.

#### 3. **Approach**
We are using the following pipeline:
1. Image preprocessing
2. License plate detection
3. Plate region extraction
4. OCR using Tesseract

##### Tools & Libraries:
- OpenCV: Image manipulation and contour detection
- EasyOCR/Tesseract: Optical character recognition
- Numpy, Matplotlib: Visualization and processing

#### 4. **Modelling**
The steps in the model are as follows:

###### A. Image Preprocessing
- Resize image for uniformity
- Convert to grayscale
- Apply Gaussian blur
- Use edge detection (Canny)

##### B. License Plate Detection
- Find contours and filter by aspect ratio and size
- Approximate polygon and check for rectangular shapes
- Extract bounding box coordinates of likely license plate

##### C. Plate Region Extraction
- Use bounding box to crop license plate region
- Apply perspective transform if required

##### D. OCR with Tesseract
- Preprocess (thresholding or denoising)
- Pass cropped image to `pytesseract.image_to_string`
- Post-process to clean up the result (remove noise/non-alphanumerics)

#### 5. **Experimentation**

We tested the pipeline on multiple images with varying plate sizes, angles, and lighting conditions.

##### Results:
- Works well for clean and well-lit plates.
- Struggles with extreme angles and blurred plates.

##### Future Improvements:
- Integrate deep learning-based plate detectors (e.g., YOLO, SSD)
- Use CRNN-based OCR for improved recognition
- Fine-tune pre-processing steps for different plate types

##### Visual Examples:
- [x] "MH20DV2363" , "KL42Q7011"


#### **Conclusion**:
This project demonstrated how OpenCV and Tesseract OCR can be combined for end-to-end license plate detection and recognition. With better pre-processing and robust detection models, this pipeline could be deployed in real-world traffic monitoring systems.

---

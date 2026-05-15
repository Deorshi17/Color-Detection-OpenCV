# Color-Detection-OpenCV
**An OpenCV-based Python application that detects colors from images by analyzing RGB values and matching them with predefined color names.**
## Overview
Color-Detection-OpenCV is a real-time color recognition project developed using Python and OpenCV. The system allows users to detect colors directly from an image by double-clicking on any pixel area.

The application extracts the pixel color values, compares them with predefined RGB color data from a CSV dataset, and displays the closest matching color name along with RGB values on the screen.

This project demonstrates practical implementation of:

- Computer Vision
- Image Processing
- RGB/BGR Color Analysis
- OpenCV Mouse Events
- Real-Time Color Identification

## Problem Statement
Humans can visually identify colors easily, but computers require mathematical processing to recognize and classify colors accurately.

The objective of this project is to:

- Detect colors from images dynamically
- Extract RGB values from selected pixels
- Match the extracted color with the nearest predefined color
- Display the detected color name in real time

This project solves the problem using OpenCV image processing and RGB distance calculation techniques.

## Project Structure
```
Color-Detection-OpenCV
│
├── Data/
│   └── colors.csv
│
├── Image/
│   ├── pic1.jpg
│   ├── pic2.jpg
│   ├── pic3.jpg
│   ├── pic4.jpg
│   └── pic5.jpg
│
├── color_detection.py
├── requirements.txt
├── README.md
├── LICENSE
└── .gitignore
```

## Dataset

The project uses a CSV dataset containing predefined color information.

### Dataset File
```Data/colors.csv```

### Dataset Columns
| Column      | Description              |
|-------------|--------------------------|
| color       | Color ID                 |
| color_name  | Name of the color        |
| hex         | Hexadecimal color code   |
| R           | Red value                |
| G           | Green value              |
| B           | Blue value               |

The dataset is used to compare extracted image colors with stored RGB values.

## Tools and Technologies
| Technology | Purpose                               |
|------------|---------------------------------------|
| Python     | Core programming language             |
| OpenCV     | Image processing and computer vision  |
| Pandas     | CSV dataset handling                  |
| NumPy      | Numerical operations                  |
| VS Code    | Development environment               |

## Methods Used
**1. Image Loading**

The selected image is loaded using OpenCV:
```python
img = cv2.imread(img_path)
```
**2. Image Resizing**

The image is resized for better display consistency:
```python
img = cv2.resize(img, (800,600))
```
**3. Mouse Event Detection**

The system detects mouse double-click events using OpenCV callbacks.
```python
cv2.EVENT_LBUTTONDBLCLK
```
**4. RGB/BGR Value Extraction**

When the user double-clicks on an image:

Pixel coordinates are captured
OpenCV extracts BGR values internally
Values are stored dynamically
```python
b,g,r = img[y,x]
```

Note: OpenCV internally uses BGR format instead of RGB.

**5. Minimum Distance Color Matching**

The system compares extracted RGB values with every color in the dataset using minimum distance calculation.
```python
d = abs(R - int(df.loc[i,'R'])) + abs(G - int(df.loc[i,'G'])) + abs(B - int(df.loc[i,'B']))
```

The nearest matching color is selected and displayed.

## Workflow
```
Input Image
      ↓
OpenCV Image Processing
      ↓
Mouse Double Click Event
      ↓
Extract RGB/BGR Values
      ↓
Compare with CSV Dataset
      ↓
Find Closest Matching Color
      ↓
Display Color Name + RGB Values
```

## Expected Outcome

The application should:

- Open the selected image successfully
- Detect colors dynamically on double-click
- Extract RGB values accurately
- Match colors with predefined dataset
- Display:
 - Color Name
 - RGB Values
- Work smoothly for all provided sample images

## Key Insights
- OpenCV stores colors internally in BGR format
- Mouse callbacks allow interactive image analysis
- RGB distance calculation is an effective basic color matching technique
- Real-time color detection is widely used in:
  - Computer Vision
  - Robotics
  - Object Tracking
  - Image Segmentation
  - AI-based Vision Systems

## How to Run this Project?

**Step 1: Clone the Repository**
```bash
git clone https://github.com/Deorshi17/Color-Detection-OpenCV.git
```
**Step 2: Open Project Folder**
```bash
cd Color-Detection-OpenCV
```
**Step 3: Install Required Libraries**
```bash
pip install -r requirements.txt
```
**Step 4: Verify Project Structure**
Ensure:

- ```colors.csv``` is inside ```Data/```
- Images are inside ```Image/```
**Step 5: Update Image Path (Optional)**

Inside ```color_detection.py```, select any image:
```python
img_path = 'Image/pic1.jpg'
csv_path = 'Data/colors.csv'
```

You can replace:

- ```pic1.jpg```
- ```pic2.jpg```
- ```pic3.jpg```
- ```pic4.jpg```
- ```pic5.jpg```
**Step 6: Run the Program**
```bash
python color_detection.py
```
**Step 7: Detect Colors**
- An image window will open
- Double-click anywhere on the image
- The application will display:
  - Color Name
  - RGB Values

## Common Errors and Fixes

**Error 1: No module named 'cv2'**
***Cause***
OpenCV is not installed.

***Fix***
```bash
pip install opencv-python
```

**Error 2: No module named 'pandas'**
***Cause***
Pandas library is missing.

***Fix***
```bash
pip install pandas
```

***Error 3: OpenCV Resize Error**
***Error Message***
```
cv2.error: (-215:Assertion failed) !ssize.empty() in function 'cv::resize'
```
***Cause***

OpenCV could not load the image because:

- image name is incorrect
- image path is incorrect
- image does not exist inside ```Image/```

***Fix***

Verify:
```python
img_path = 'Image/pic1.jpg'
```
and ensure the image exists.

## Results & Conclusion

The project successfully performs real-time color detection using OpenCV and RGB analysis techniques.

**Achievements**
- Accurate color extraction from images
- Real-time interactive color identification
- Dynamic RGB value analysis
- Efficient dataset-based color matching

## Conclusion

This project demonstrates how computer vision systems can process image data and identify colors dynamically using Python and OpenCV. It provides a strong foundation for advanced computer vision applications involving object detection, tracking, and intelligent image analysis.

## Future Improvements

Possible enhancements include:

- Real-time webcam color detection
- Deep Learning-based color classification
- HSV color space implementation
- GUI integration using Tkinter or PyQt
- Multi-object color segmentation
- Live object tracking


## 📬 Contact

### **Deorshi Nishant**
*Data Analyst & Business Intelligence Professional*

---

### 🔗 Connect with me

<p align="left">
  <a href="https://www.linkedin.com/in/itsyournish/" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
  </a>
  <a href="mailto:itsyournish07@gmail.com">
    <img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail"/>
  </a>
</p>

---

*💼 Open to collaborations and new opportunities in Data Analytics & Business Intelligence*

*⭐ If you found this project helpful, please consider giving it a star!*

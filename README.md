🏭 Industrial Defect Detector
The Industrial Defect Detector is an image processing application built with Python and OpenCV, designed to automatically identify and highlight surface defects in industrial components. It simplifies quality inspection by analyzing uploaded images, detecting irregularities, and marking them with bounding boxes.

This tool is particularly useful in manufacturing domains for automating visual inspection and ensuring product consistency.

📌 Table of Contents
Features

How It Works

Technologies Used

Installation

Usage Instructions

Sample Output

Project Structure

Contributing

License

✅ Features
Upload industrial component images for analysis.

Converts images to grayscale and applies preprocessing filters.

Uses adaptive thresholding to isolate potential defects.

Identifies contours and filters them based on area thresholds.

Marks detected defect regions using bounding rectangles.

Displays the processed image with visual cues and a defect count.

🔍 How It Works
Here's a breakdown of the core logic in main.py:

Image Upload
Users upload an image interactively using google.colab.files.upload() (works best in Colab).

Image Conversion & Preprocessing

Image is converted to RGB, then to BGR (OpenCV standard).

Image is resized to 600x400.

Converted to grayscale and blurred using Gaussian blur to remove noise.

Adaptive Thresholding
The grayscale image is thresholded using cv2.adaptiveThreshold to create a binary map emphasizing edges and contours.

Contour Detection
Contours are extracted using cv2.findContours.

Defect Filtering

Each contour is analyzed by area.

Only contours with an area between 100 and 10,000 pixels are considered "defects".

Bounding rectangles are drawn around detected defects.

Visualization
The processed image is converted back to RGB and displayed using PIL.Image and IPython.display.

🛠 Technologies Used
Library	Purpose
OpenCV	Image processing and computer vision
NumPy	Array and numerical operations
Pillow	Image format conversion
IPython.display	Inline image rendering in Colab
Google Colab	Interactive runtime and UI

💻 Installation
1. Clone the Repository
bash
Copy
Edit
git clone https://github.com/SriAbhirami/Industrial-defect-detector.git
cd Industrial-defect-detector
2. Install Dependencies
bash
Copy
Edit
pip install opencv-python numpy pillow
💡 It’s recommended to run this project in Google Colab for seamless image uploads and display.

🚀 Usage Instructions
Option 1: Run on Google Colab
Open this notebook in Colab.

Upload your image when prompted.

The system will analyze the image and display defects.

Option 2: Run Locally (with limitations)
bash
Copy
Edit
python main.py
Note: Local version requires modifying the file upload logic to use cv2.imread() for reading local files instead of Colab's upload interface.

🖼 Sample Output
The system draws red bounding boxes around suspected defects and prints the total number of detected defects.

plaintext
Copy
Edit
Detected defects: 5
📸 Example result available in the repository: Screenshot (1).pdf

📁 Project Structure
bash
Copy
Edit
Industrial-defect-detector/
│
├── main.py                  # Main Python script for defect detection
├── Screenshot (1).pdf       # Example output image with bounding boxes
└── README.md                # Project documentation (this file)
🙌 Contributing
We welcome contributions! If you have suggestions or want to improve this project:

Fork the repository

Create a new branch (git checkout -b feature-xyz)

Commit your changes (git commit -m 'Add new feature')

Push to the branch (git push origin feature-xyz)

Open a Pull Request


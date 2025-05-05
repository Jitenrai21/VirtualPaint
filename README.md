Virtual Painting Application 🎨
Overview 📖
This Python-based virtual painting application uses OpenCV to transform your webcam into an interactive digital canvas! 🌟 It detects colored objects in real-time, allowing you to draw on a virtual screen by moving them. A companion color detection tool helps you fine-tune HSV color ranges for precise color tracking. Perfect for creative projects or fun experiments! 😄
Features ✨

Real-time Color Detection 🌈: Identifies specific colors (e.g., purple) using HSV color space.
Virtual Drawing ✍️: Draws circles on the canvas at the detected object's position, simulating painting.
Persistent Drawing 📍: Retains all drawn points for continuous artwork.
Customizable Colors 🎨: Supports multiple colors with configurable HSV ranges and BGR display colors.
HSV Tuning Tool ⚙️: Interactive trackbars to adjust HUE, SATURATION, and VALUE ranges for color detection.
Visual Feedback 🖼️: Displays original, masked, and filtered images for color tuning.
Easy Exit 🚪: Press q to quit either application.

Requirements 🛠️

Python 3.x 🐍
OpenCV (cv2): Install via pip install opencv-python
NumPy: Install via pip install numpy
A webcam 📷

Installation ⚙️

Clone the repository:git clone https://github.com/your-username/virtual-painting.git
cd virtual-painting


Install dependencies:pip install opencv-python numpy


Ensure a webcam is connected 📹.

Usage 🚀
The repository includes two scripts: one for painting and one for tuning color detection.
Virtual Painting (virtual_paint.py) 🖌️

Run the script:python virtual_paint.py


Hold a colored object (matching predefined HSV ranges) in front of the webcam.
Move the object to draw on the canvas 🖼️.
Press q to exit ❌.

HSV Color Tuning (color_tuner.py) 🎚️

Run the script:python color_tuner.py


Adjust the trackbars in the HSV window to set HUE, SATURATION, and VALUE ranges 🎛️.
Observe the Horizontal Stacking window showing:
Original webcam feed 📷
Masked image (white where the color is detected) 😷
Filtered result (color in detected areas) 🌈


Note the HSV values for use in virtual_paint.py.
Press q to exit ❌.

Code Structure 🧱
Virtual Painting (virtual_paint.py)

Main Loop 🔄: Captures frames, detects colors, and updates the canvas.
findColor() 🎯: Converts frames to HSV, applies color masks, and locates object centers.
getContours() 📏: Finds contours and calculates drawing points.
drawOnCanvas() 🖌️: Draws colored circles at tracked points.
Configuration ⚙️:
myColors 🌈: HSV ranges for detectable colors (e.g., purple).
myColorValues 🎨: BGR colors for drawing.
frameWidth, frameHeight 📐: 640x480 resolution.
Brightness set to 150 for better detection 🔆.



HSV Color Tuning (color_tuner.py)

Main Loop 🔄: Captures frames, applies HSV filters based on trackbar values, and displays results.
Trackbars 🎚️: Adjust HUE (0-179), SATURATION (0-255), and VALUE (0-255) min/max.
Display 🖼️: Horizontally stacks original, mask, and filtered images for real-time feedback.
Configuration ⚙️: Same resolution (640x480) and brightness (150) as the painting script.

Customization 🛠️

Add New Colors to Painting 🌟:
Use color_tuner.py to find suitable HSV ranges.
Add the range to myColors in virtual_paint.py (format: [H_min, S_min, V_min, H_max, S_max, V_max]).
Add a matching BGR color to myColorValues (format: [B, G, R]).


Adjust Resolution 📏: Modify frameWidth and frameHeight in both scripts.
Tweak Brightness 💡: Change cap.set(10, 150) in both scripts for lighting conditions.

Contributing 🤝
Contributions are welcome! Fork the repo, submit issues, or send pull requests to enhance features or fix bugs. Let’s make this app even better! 🚀

# Air Canvas & Sign Language Detection System

A real-time computer vision application built with Python that enables **touch-free drawing in the air** using hand gestures and **sign language recognition** through a standard webcam — no special hardware required.

> **Capstone Project-I** | M.Sc. Data Science | Osmania University, Hyderabad | 2023–2025  
> **Guided by:** Dr. Ch. Raju, Department of Computer Science

---

## What It Does

This application has two modes:

### Mode 1 — Air Canvas
- Draw on a virtual whiteboard using just your **index finger**
- Select from **4 colors**: Blue, Green, Red, Yellow
- **Clear the canvas** by pointing to the CLEAR button at the top
- Bring your **thumb and index finger together** to lift the pen (stop drawing)

### Mode 2 — Sign Language Detection
- Show hand gestures to the camera
- The system reads the position of all 5 fingertips in real time
- Recognized signs are displayed as text on screen

| Gesture | Detected Sign |
|---|---|
| All fingers pointing downward in order | Yes |
| Spread hand (thumb + index up) | I Love You |
| Fingers spread horizontally | Hello |
| All fingers curled below thumb | No |
| All fingers above thumb level | Thank You |

---

## Demo

| Air Canvas Mode | Sign Language Mode |
|---|---|
| Draw in the air with your index finger | Show a hand sign and see it translated to text |

---

## Tech Stack

| Tool | Version | Purpose |
|---|---|---|
| Python | 3.11.2 | Core language |
| OpenCV | 4.9.0.80 | Webcam capture, frame processing, drawing |
| MediaPipe | 0.10.14 | Hand landmark detection (21 points) |
| NumPy | 1.26.3 | Image array operations |

---

## How It Works

1. Webcam captures live video frames
2. Each frame is flipped (mirror effect) and converted from BGR to RGB
3. **MediaPipe Hands** detects 21 hand landmarks per frame
4. **Landmark 8** (index fingertip) acts as the drawing cursor
5. **Landmark 4** (thumb tip) acts as the pen-lift trigger
6. Drawing points are stored in `deque` objects per color for smooth strokes
7. In Sign Language mode, fingertip Y/X coordinates are compared using rule-based logic to classify gestures

---

## Installation

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/air-canvas-sign-language-detection.git
cd air-canvas-sign-language-detection

# Install dependencies
pip install opencv-python==4.9.0.80
pip install numpy==1.26.3
pip install mediapipe==0.10.14
```

---

## Run

```bash
python air_canvas.py
```

**Controls:**
| Key | Action |
|---|---|
| `1` | Switch to Air Canvas mode |
| `2` | Switch to Sign Language mode |
| `m` | Return to main menu |
| `q` | Quit the application |

---

## Hardware Requirements

- Any laptop or desktop with a built-in or external webcam
- Minimum 256 MB RAM
- No GPU required

---

## Project Structure

```
air-canvas-sign-language-detection/
│
├── air_canvas.py        # Main application file
├── requirements.txt     # Python dependencies
└── README.md            # Project documentation
```

---

## Future Scope

- Expand sign language vocabulary beyond basic gestures
- Add voice output for detected signs
- Integrate with Zoom/video conferencing for real-time sign interpretation
- Support multi-user interaction
- Improve accuracy using trained ML classification models

---

## References

- OpenCV Documentation: https://opencv.org
- MediaPipe Hands: https://mediapipe.dev
- Sign Language Recognition Reference: https://data-flair.training/blogs/sign-language-recognition-python-ml-opencv/

---

## Author

**Mandala Archana**  
M.Sc. Data Science, University College of Science, Osmania University, Hyderabad  
[LinkedIn](https://linkedin.com/in/mandala-archana) | mandalaarchana123@gmail.com

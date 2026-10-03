# Virtual Mouse

A webcam-based virtual mouse that uses hand gestures to control the computer.

The project tracks hand landmarks and translates hand movements and gestures into mouse movement, scrolling, and zoom controls.

> **Status:** Work in progress. The project is **not perfect yet**. Drag-and-drop is currently not implemented.

## Features

- Webcam-based hand tracking
- 21 hand landmarks
- Smooth cursor movement
- Cursor jitter reduction
- Open-palm Cursor ↔ Scroll mode switching
- Native Windows mouse-wheel scrolling
- OK-sign gesture for Zoom mode
- Zoom control using the finger position
- Five-finger gesture to return from Zoom to Cursor
- Hand-distance-normalized gesture detection
- Native Windows keyboard/mouse input

## Requirements

- Windows
- Python 3.10 or newer recommended
- Webcam
- Webcam available at camera index `1`

## Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
cd YOUR_REPOSITORY
```

Create a virtual environment:

```bash
python -m venv .venv
```

Activate it:

```bash
.venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Or install them manually:

```bash
pip install opencv-python mediapipe numpy pyautogui
```

## Running

Run:

```bash
python virtual_mouse.py
```

The default camera index is:

```python
CAMERA_INDEX = 1
```

If your webcam uses another index, change it to `0`, `2`, etc.

## Controls

### Cursor

Move your hand in front of the webcam to control the mouse cursor.

The cursor uses smoothing and jitter reduction to make movement more stable.

### Cursor ↔ Scroll

Show an open palm to switch between Cursor and Scroll mode.

Scroll mode divides the camera view into three zones:

| Area | Action |
|---|---|
| Top 42.5% | Scroll Up |
| Middle 15% | Stop |
| Bottom 42.5% | Scroll Down |

Keep your hand in the desired area to continue scrolling.

### Zoom

Make an **OK sign** to enter Zoom mode.

While in Zoom mode:

| Area | Action |
|---|---|
| Top 42.5% | Zoom In |
| Middle 15% | Stop |
| Bottom 42.5% | Zoom Out |

The program sends keyboard input equivalent to:

```text
Ctrl + +
Ctrl + -
```

### Exit Zoom

Show an open palm with all five fingers extended to return to Cursor mode.

## Camera Tips

For better tracking:

- Keep the entire hand inside the camera frame.
- Use reasonably even lighting.
- Avoid strong backlighting.
- Avoid backgrounds containing hand-like shapes.
- Keep the camera roughly at hand level.
- Avoid moving the hand extremely fast.

## Current Limitations

This project is still under development.

Known limitations:

- **Drag-and-drop is not implemented yet.**
- Gesture recognition can occasionally be affected by lighting and camera angle.
- Very fast hand movements can reduce tracking accuracy.
- Different webcams may produce different results.
- Some applications may respond differently to simulated keyboard/mouse input.
- Gesture sensitivity may need adjustment for different users.

## Roadmap

Possible future improvements:

- Drag-and-drop
- More reliable clicking
- Custom gesture configuration
- User calibration
- Better multi-monitor support
- Adjustable cursor sensitivity
- Additional gestures

## Project Structure

```text
.
├── virtual_mouse.py
├── README.md
└── requirements.txt
```

## License

You can use an MIT License or another license appropriate for your project.

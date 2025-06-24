
# 🖐️ Virtual Mouse using Hand Gestures (Python + OpenCV + MediaPipe)

This project implements a virtual mouse using hand gestures captured from a webcam. The system recognizes specific finger movements and performs actions such as **left click**, **right click**, **double click**, **screenshot**, and **cursor control**.

---

## 🚀 Features

- Cursor movement using index finger tracking
- Left Click, Right Click, Double Click
- Screenshot capture using specific gesture
- Hand landmark detection using MediaPipe
- Real-time gesture feedback on video feed

---

## 🧰 Dependencies

Install the required libraries using the following command:

```bash
pip install opencv-python mediapipe pyautogui pynput numpy
```

---

## 🗃️ File Structure

```
├── main.ipynb              # Jupyter Notebook with full implementation
├── util.py                 # Utility functions (angle, distance)
└── FINAL_README.md         # Updated README with accurate gesture logic
```

---

## 🤖 Gesture Controls

| Gesture                                        | Action           |
|------------------------------------------------|------------------|
| Index finger up + Thumb finger closed          | Move mouse       |
| Index close + Middle up + Thumb open           | Left click       |
| Thumb open + Index up + Middle close           | Right click      |
| Index + Middle close                           | Double click     |
| All fingers close                              | Take screenshot  |

These gestures are interpreted using angles and distances between hand landmarks detected by MediaPipe.

---

## ⚙️ Logic (Inside `util.py`)

- `get_angle(a, b, c)`: Calculates angle between three points.
- `get_distance(landmark_list)`: Measures Euclidean distance between two points for proximity gestures.

```python
def get_angle(a, b, c):
    radians = np.arctan2(c[1] - b[1], c[0] - b[0]) - np.arctan2(a[1] - b[1], a[0] - b[0])
    angle = np.abs(np.degrees(radians))
    return angle
```

---

## 🖥️ How to Run

1. Clone the repository or download the files.
2. Make sure your webcam is working.
3. Open the `main.ipynb` notebook in **VS Code / Jupyter**.
4. Run all cells and try different gestures.

---

## 📝 Notes

- Tested on Python 3.11+
- Works best in **good lighting** and against **plain backgrounds**
- Adjust `min_detection_confidence` and gesture logic for better accuracy if needed

---

Built using [MediaPipe](https://google.github.io/mediapipe/), [OpenCV](https://opencv.org/), and [PyAutoGUI](https://pyautogui.readthedocs.io/).

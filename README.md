# Real-Time Sign Language to Text and Voice

![Python](https://img.shields.io/badge/python-3.8%2B-blue)
![OpenCV](https://img.shields.io/badge/OpenCV-computer%20vision-green)
![MediaPipe](https://img.shields.io/badge/MediaPipe-hand%20tracking-orange)
![Status](https://img.shields.io/badge/status-prototype-yellow)

A computer-vision application that reads sign language gestures through an ordinary webcam and turns them into on-screen text and spoken audio in real time. No gloves, depth cameras or special hardware needed.

<!-- TODO: add a demo GIF or screenshot here. This is the single most useful thing you can add to a README.
![Demo](docs/demo.gif)
-->

## Table of Contents

- [Problem Statement](#problem-statement)
- [Team](#team)
- [What We Built and Why](#what-we-built-and-why)
- [How It Works](#how-it-works)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Troubleshooting](#troubleshooting)
- [Known Limitations](#known-limitations)
- [Roadmap](#roadmap)

## Problem Statement

**Sign language to text and voice, in real time.**

Build a computer-vision application that reads hand gestures through an ordinary webcam and converts sign language into written text or spoken audio as it happens, closing the communication gap between signers and people who do not sign.

The hard parts:

- Tracking hands reliably across different lighting, skin tones and backgrounds
- Classifying movement over time, not just single frames
- Keeping the full loop fast enough to hold a conversation

## Team

| Name | USN |
| --- | --- |
| Ayush Chaudhary | `[USN]` |
| `[Team member 2]` | `[USN]` |

## What We Built and Why

### What we built

- **Live video capture:** reads frames from a standard webcam with low latency.
- **Hand landmark detection:** extracts 21 3D landmarks per hand per frame.
- **Gesture classification:** a trained model maps landmark data to recognised signs.
- **Text output:** recognised signs appear on screen as text.
- **Voice output:** recognised words are spoken aloud using a text-to-speech engine.

### Why we built it

Many sign language translation systems depend on sensor gloves or fixed, specialised setups, which makes them expensive and hard to deploy. Ours runs on a normal laptop webcam, so it is cheap, portable and easy to try.

## How It Works

```text
Webcam stream
     │
     ▼
Frame capture and preprocessing   (OpenCV)
     │
     ▼
Hand landmark extraction          (MediaPipe)
     │
     ▼
Gesture classification            (trained model)
     │
     ├──────────────┐
     ▼              ▼
On-screen text   Text-to-speech
```

1. OpenCV grabs each frame from the webcam.
2. MediaPipe detects the hand(s) and returns landmark coordinates.
3. The landmarks are fed to the classifier, which predicts the sign.
4. The predicted word is shown on screen and passed to the text-to-speech engine.

## Tech Stack

| Area | Tools |
| --- | --- |
| Language | Python 3.8+ |
| Computer vision | OpenCV, MediaPipe |
| Machine learning | `[TensorFlow / PyTorch / scikit-learn: keep only what you use]`, NumPy |
| Speech | `[pyttsx3 / gTTS: keep only what you use]` |
| Interface | `[OpenCV window / Tkinter / Streamlit: keep only what you use]` |

<!-- TODO: make this table match requirements.txt exactly. -->

## Project Structure

```text
realtime-sign-language-to-text/
├── data/              # Dataset samples and training logs
├── models/            # Trained model weights
├── utils/             # Landmark extraction and preprocessing helpers
├── main.py            # Entry point: launches the application
├── requirements.txt   # Python dependencies
├── .gitignore
└── README.md
```

<!-- TODO: update this tree to match the real repository. -->

## Getting Started

### Prerequisites

- Python 3.8 or newer
- A working webcam
- Git

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/Ayush-Chaudhary-02/realtime-sign-language-to-text.git
cd realtime-sign-language-to-text

# 2. Create a virtual environment
python -m venv venv

# 3. Activate it
#    Windows:
venv\Scripts\activate
#    macOS / Linux:
source venv/bin/activate

# 4. Install dependencies
python -m pip install --upgrade pip
pip install -r requirements.txt
```

## Usage

```bash
python main.py
```

1. Allow the app to access your camera if your OS asks.
2. Sit in a well-lit area with your hand(s) clearly in frame.
3. Perform a sign. The recognised text appears on screen and is spoken aloud.
4. Press **`q`** to quit.

**Tips for best results:** use even lighting, a plain background, and keep your hands fully inside the frame.

## Troubleshooting

| Problem | Fix |
| --- | --- |
| Camera does not open | Close other apps using the webcam, and check OS camera permissions for Python/your terminal. |
| Wrong camera is used | Change the camera index in `main.py` (for example `0` to `1`). |
| `pip install` fails | Make sure you are on Python 3.8+ and inside the virtual environment. |
| No voice output | Check your system volume and that your speech library installed correctly. |
| Laggy or low FPS | Close heavy apps, improve lighting, or lower the capture resolution. |

## Known Limitations

- **Isolated signs, not full sentences.** The prototype handles individual words or letters; grammatical sentence-level translation is not supported yet.
- **Small vocabulary.** The model is trained on a limited set of signs (`[list or number of supported signs]`).
- **Sensitive to environment.** Tracking degrades in very low light or cluttered backgrounds.
- **Desktop only.** No mobile or browser version yet.
- **Accuracy:** `[add your measured accuracy and how you tested it, or remove this line]`

## Roadmap

- [ ] Expand the dataset and supported vocabulary
- [ ] Add sequence models (for example Transformers) for continuous signing
- [ ] Improve robustness to lighting and backgrounds
- [ ] Browser-based version (WebRTC / MediaPipe Web)
- [ ] Mobile app for Android and iOS

## Acknowledgements

- [MediaPipe](https://developers.google.com/mediapipe) for hand landmark tracking
- [OpenCV](https://opencv.org/) for video capture and processing
- `[Dataset or other sources you used]`

## License

`[Add a license, for example MIT, and a LICENSE file. Without one, others cannot legally reuse your code.]`

# 🤟 Real-Time Sign Language to Text and Voice

> Bridging the communication gap between sign language users and non-signers through computer vision and real-time audio synthesis.

---

## 📌 1. Chosen Problem Statement
**Sign language to text and voice, in real time**  
Build a computer-vision application that reads hand gestures through an ordinary webcam and turns sign language into written text or spoken audio as it happens, closing the gap between signers and people who do not sign. The hard parts are tracking hands reliably, classifying movement rather than single frames, and keeping the whole loop fast enough to hold a conversation.

---

## 👥 2. Team Member Names + USNs
* **Ayush Chaudhary** – [Your USN Here]
* *(Add other team members here if applicable)*

---

## 💡 3. What We Built & Why

### What We Built
A lightweight desktop/web application that captures video input from a standard webcam, tracks hand landmarks frame-by-frame, and processes spatial-temporal movement patterns using machine learning to predict sign gestures. The recognized signs are dynamically displayed as text on screen and converted into spoken voice output.

### Why We Built It
Millions of individuals rely on sign language as their primary mode of communication, yet society often lacks accessible translation tools in everyday public spaces. Traditional translation solutions are usually expensive, hardware-heavy, or restricted to static alphabets (like simple finger-spelling). We wanted to build a practical, software-first tool using an ordinary webcam to make real-time, fluid conversations accessible anywhere.

---

## ⚙️ 4. Clear Run & Installation Instructions

Follow these steps to set up and run the project locally on your machine:

### Prerequisites
* Python 3.8 or higher installed on your system.
* A working webcam.

### Step-by-Step Setup

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/your-username/sign-language-translator.git](https://github.com/your-username/sign-language-translator.git)
   cd sign-language-translator

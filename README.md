# Real-Time Sign Language to Text and Voice

> A robust, computer-vision-powered application that translates sign language gestures into written text and natural-sounding speech in real time using an ordinary webcam.

---

## Table of Contents
1. [Project Overview](#-1-project-overview)
2. [Team Members & USNs](#-2-team-members--usns)
3. [Problem Statement](#-3-problem-statement)
4. [What We Built & Why](#-4-what-we-built--why)
5. [System Architecture & Workflow](#-5-system-architecture--workflow)
6. [Tech Stack & Dependencies](#-6-tech-stack--dependencies)
7. [Project Directory Structure](#-7-project-directory-structure)
8. [Installation & Setup Instructions](#-8-installation--setup-instructions)
9. [How to Run the Application](#-9-how-to-run-the-application)
10. [Unfinished Features & Known Limitations](#-10-unfinished-features--known-limitations)
11. [Future Roadmap](#-11-future-roadmap)

---

## 📌 1. Project Overview
Communication barriers between sign language users and non-signers create daily challenges in public and professional spaces. This project implements an end-to-end computer vision and machine learning pipeline that captures hand landmarks via a standard webcam, classifies spatial-temporal motion patterns, and instantly converts them into readable text and synthesized audio output.

---

## 👥 2. Team Members & USNs
* **Ayush Chaudhary** – [Your USN Here]
* *[Team Member 2 Name]* – *[USN]*

---

## 🎯 3. Problem Statement
**Sign language to text and voice, in real time**  
Build a computer-vision application that reads hand gestures through an ordinary webcam and turns sign language into written text or spoken audio as it happens, closing the gap between signers and people who do not sign. The hard parts are tracking hands reliably, classifying movement rather than single frames, and keeping the whole loop fast enough to hold a conversation.

---

## 💡 4. What We Built & Why

### What We Built
* **Real-Time Video Capture & Preprocessing:** Interfaces with standard webcams to process live video streams with minimal latency.
* **Hand Landmark Detection:** Leverages advanced coordinate tracking frameworks to isolate 21 3D hand knuckle coordinates per hand frame.
* **Spatial-Temporal Classification:** Maps frame sequences over time to recognize dynamic gesture patterns rather than isolated static frames.
* **Text-to-Speech (TTS) Synthesis:** Instantly converts successfully recognized word tokens into audible speech output to facilitate a two-way conversation loop.

### Why We Built It
Most existing sign language translation systems rely on expensive, proprietary hardware gloves or restricted stationary setups. By building a software-first solution that functions purely via an ordinary laptop webcam, we aim to deliver an accessible, affordable, and easily deployable tool that bridges daily communication gaps.

---

## 📊 5. System Architecture & Workflow

```text
[Webcam Stream] 
       │
       ▼
[Frame Capture & Preprocessing (OpenCV)]
       │
       ▼
[Hand Landmark Extraction (MediaPipe)]
       │
       ▼
[Gesture Classification Model (LSTM / ML Classifier)]
       │
       ├─────────────────────────┐
       ▼                         ▼
[Text UI Display]      [Text-to-Speech Engine (Audio)]

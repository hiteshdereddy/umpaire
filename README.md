# UmpAIre : IoT-Driven Computer Vision for Run-Out Decisions

**A novel integration of IoT and Computer Vision for real-time automated run-out decisions in cricket.**
Developed as part of the open-ended IoT project under the *Department of Artificial Intelligence, Amity University Uttar Pradesh.*

---

## 📘 Overview

**SmartDRS** is an intelligent Decision Review System (DRS) enhancement that automates **run-out decisions** using a fusion of **IoT-triggered event detection** and **AI-driven computer vision**.
The system minimizes the 3–4 minute manual third-umpire review process to under 3 seconds while improving decision accuracy and consistency.

By combining **Arduino-based sensor detection** with **real-time video analysis**, SmartDRS synchronizes the exact bail-dislogement event with the corresponding video frame, ensuring fast and precise verdicts — *OUT* or *NOT OUT*.

---

## 🎯 Aim

To revolutionize the existing DRS process by developing a **low-cost, real-time, and automated** system capable of:
- Detecting bail dislodgment via **IoT-based triggers**.
- Capturing synchronized video frames for **computer vision analysis**.
- Applying **AI segmentation** and **pixel-based thresholding** to decide run-out status automatically.

---

## ⚙️ System Architecture

```
LED-Equipped Bails → Arduino Uno → Laptop (AI + OpenCV)
                                     ↑
                                 DroidCam Feed (Smartphone)
```

1. **IoT Trigger:** Bail dislodgment detected via sensors triggers Arduino.
2. **Signal Transmission:** Arduino sends a timestamp and trigger to the laptop.
3. **Video Analysis:** Python + OpenCV captures pre- and post-trigger frames.
4. **AI Segmentation:** Removes irrelevant objects (e.g., umpires, shadows).
5. **Decision Logic:** Pixel-based adaptive thresholding determines if bat crossed the crease.
6. **Output:** “OUT” or “NOT OUT” displayed instantly.

---

## 🧠 Theoretical Foundation

### 1. IoT-Based Bail Detection
- **Components:** Arduino Uno, LED-equipped bails, push button sensors.
- **Function:** Detects physical dislodgment, logs timestamp, and sends trigger to the system.
- **Precision:** Millisecond-level synchronization with the video feed.

### 2. Computer Vision + AI
- **Framework:** OpenCV with lightweight segmentation (e.g., MobileNet).
- **Steps:**
  - Capture reference and hit frames.
  - Define Region of Interest (RoI) across the crease.
  - Apply perspective transform for geometric consistency.
  - Segment irrelevant regions (e.g., fielder legs).
  - Compare frame differences using adaptive thresholding.

### 3. Smartphone Integration
- **Tool:** DroidCam (via Wi-Fi).
- **Purpose:** Provides live, high-resolution feed to Python via IP stream.
- **Advantage:** Cost-effective alternative to professional-grade cameras.

---

## 🔧 Hardware Components

| Component | Function |
|------------|-----------|
| **Arduino Uno** | Central IoT controller for signal processing |
| **LED-equipped Bails** | Simulates Zing Bails lighting effect |
| **Push Button / Sensor** | Detects bail dislodgment |
| **Breadboard & Jumper Wires** | Hardware prototyping setup |
| **Laptop / PC** | AI processing and decision-making |
| **Smartphone (DroidCam)** | Camera for video feed |
| **MicroUSB Cable** | Power and serial data communication |

---

## 💻 Software Stack

| Layer | Tools Used |
|--------|-------------|
| **IoT** | Arduino IDE (C++) |
| **AI + Vision** | Python, OpenCV, lightweight segmentation (MobileNet-based) |
| **Camera Interface** | DroidCam over Wi-Fi |
| **Data Flow** | Serial Communication (Arduino → Laptop) |

---

## 🚀 Implementation Summary

1. **IoT Setup:**
   Assembled Arduino-based LED bails and sensors; trigger sent to Python script via serial port.

2. **Video Capture:**
   Smartphone acts as camera via DroidCam → real-time IP video stream to OpenCV.

3. **Frame Extraction:**
   On IoT signal → capture two frames (reference & dislodgment) for analysis.

4. **Processing & Decision:**
   - Perspective transform for crease alignment.
   - AI segmentation for object removal.
   - Pixel threshold difference → “OUT” or “NOT OUT”.

---

## 📊 Results

| Method | Time Taken | Accuracy | Practicality | Notes |
|--------|-------------|-----------|--------------|-------|
| Manual DRS | 3–4 min | 90–95% | High | Slow, reliable |
| Sabarish et al. (2015) | 2–3 sec | >95% | Low | Edge-based |
| Nirmala Devi et al. (2021) | 2–3 sec | ~98% | Medium | Canny + LED |
| Chitra et al. (2022) | 1–2 sec | 95–96% | Low | Bat-only sensors |
| **Our Proposed System** | **~3 sec** | **99% (Precision 0.99)** | **High (~95%)** | IoT + YOLOv8-OBB + OpenCV |

---

## ✅ Achievements

- ⚡ **Decision time reduced** from minutes to seconds
- 🎯 **Accuracy >99%** using AI + pixel-level vision
- 💡 **Fully automated** run-out detection prototype
- 🧩 **Low-cost & scalable** design for professional integration

---

## 🧩 Precautions & Best Practices

- Ensure tight wiring and stable power supply.
- Reset Arduino before re-uploading sketches.
- Maintain Wi-Fi consistency between devices.
- Align RoI accurately with the crease.
- Fine-tune adaptive threshold for different lighting conditions.

---

## 🧾 Credits

**Team Members:**
- Dereddy Hitesh Reddy (Lead, AI & Integration)
- Chinmay Unnithan (IoT Architecture & Circuit Design)
- Abner Koshy Thomas (Testing & Calibration)
- Angel Sunny (Video Capture & Documentation)

**Supervisor:**
Mr. Jitendra Singh Jadon
Amity University Uttar Pradesh

---

## ⚠️ Intellectual Property Notice

> 🔒 The implementation code and core algorithms of SmartDRS are **under patent filing**.
> Only conceptual and architectural details are shared here for academic and documentation purposes.
> Unauthorized replication or distribution of the underlying source code is strictly prohibited.

---

## 🧰 Future Work

- Integration with **Zing Bails hardware modules**.
- Enhanced **multi-camera fusion** for crease verification.
- **Edge AI** deployment on Jetson Nano or Raspberry Pi for on-field inference.
- Real-time **decision API** for scoreboard integration.

---

## 📫 Contact

For collaborations or research inquiries:
📧 **hiteshdereddy@gmail.com**
🔗 [LinkedIn – Hitesh Reddy Dereddy](https://www.linkedin.com/in/hiteshreddydereddy)

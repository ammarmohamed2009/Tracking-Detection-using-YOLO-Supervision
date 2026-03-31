# 🚶‍♂️ Real-Time Pedestrian Tracking & Crowd Analytics (YOLO + Supervision)
<img width="1495" height="836" alt="image" src="https://github.com/user-attachments/assets/9de6ac73-7b0c-4709-b6ae-d7a66617b918" />


### 📌 Project Overview
This project implements a sophisticated **Multi-Object Tracking (MOT)** system designed for urban environments and crowd monitoring. By combining **YOLO**'s detection capabilities with persistent tracking, the system identifies pedestrians and their belongings (handbags, backpacks) while maintaining a unique identity for each entity across the video stream.

---

### 🧠 Core Features & Logic
* **Multi-Class Detection:** Detects and distinguishes between `person`, `handbag`, and `backpack` in high-density scenes.
* **Persistent Identity:** Utilizes `sv.ByteTrack` to assign a unique **Tracker ID** to every person and object, preventing ID switches during occlusions.
* **Intelligent Visualization:** * Sleek bounding boxes via `sv.BoxAnnotator`.
    * Custom-coded labels using `cv2` to display **Class Name**, **Confidence Score**, and **Track ID**.

---

### 📊 Technical Implementation
The pipeline follows a structured workflow:
1. **Inference:** YOLO extracts features and generates candidate detections.
2. **Data Transformation:** Converts Ultralytics results into the `Supervision` format for advanced manipulation.
3. **Tracking:** Updates the tracker state to link detections across consecutive frames.
4. **Custom Rendering:** Applies specific color logic and text overlays to the frame before saving.

---

### ⚙️ Color Logic (Customized)
In the provided code, the system applies a dynamic color scheme:
- **Primary Class (Person):** Green 🟢 `(0, 255, 0)`
- **Secondary Classes (Bags/Accessories):** Red 🔴 `(0, 0, 255)`

---

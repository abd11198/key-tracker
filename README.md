# 🔑 Smart Key Detection & Tracking System (YOLOv8)

An end-to-end AI system that learns to detect personal objects (e.g., keys) from video input and tracks them in real-time, generating smart notifications when objects move and describing their location relative to surrounding items.

---

## 📌 Overview

This project implements a full computer vision pipeline combining:

- Automated dataset generation  
- Custom YOLOv8 model training  
- Real-time object detection and tracking  
- Context-aware notifications and logging  

The system is designed to work in real-world environments, focusing on **small object detection and movement analysis**.

---

## 🚀 Key Features

### 🎯 Training Pipeline
- Train custom YOLOv8 models directly from video input  
- Automatic frame extraction and labeling (no manual annotation)  
- Optional reference image matching using SIFT  
- Multi-class support for detecting multiple keys  
- Smart dataset splitting (train/validation)  
- Optimized for small object detection  

---

### 🎥 Real-Time Tracking System
- Live webcam-based detection and tracking  
- Unique ID assignment for each detected object  
- Movement detection triggered only after stabilization  
- Duplicate detection filtering (IoU + spatial distance)  

---

### 🔔 Smart Notifications
- Alerts triggered when objects are moved  
- Human-readable descriptions:  
  > "Your key moved next to a wallet and laptop"  
- Desktop notifications (if supported)  

---

### 📍 Location Awareness
- Detects nearby objects using YOLO  
- Generates contextual descriptions of object location  
- Supports interactive queries:
  ```bash
  where is <key_name>

---

## 🧱 Project Structure

             Training Stage (Google Colab)
           ┌──────────────────────────────┐
           │ Upload video of keys         │
           │ Frame extraction             │
           │ Dataset generation           │
           │ YOLOv8 training              │
           │ Export best.pt               │
           └──────────────┬───────────────┘
                          │
                          ▼
             Runtime Detection (Local App)

        ┌────────────────────────────────────┐
        │ Load trained YOLO model            │
        │ Open live cameras                  │
        │ Detect keys                        │
        │ Track movement                     │
        │ Trigger notifications              │
        └────────────────────────────────────┘





# key-tracker

# Camera-Based-AI-Detection-System — KeyTracker (YOLOv8)

Real-time detection & tracking of personal keys with **movement alerts, screenshots, and multi-camera support**.  
Train quickly on **Google Colab**, then run the **multi-camera app in PyCharm** (or plain Python) to watch your keys and get notified when they move.

> Built for: Abed Elkareem Nassar · Updated: 2025-08-17

---

## ✨ What it does
- **Detects multiple keys** you trained on (e.g., `first_key`, `second_key`, `third_key`).
- **Watches for motion** and fires an event only **after the key finishes moving** (to avoid spam).
- **Saves screenshots** of the scene when movement is confirmed.
- **Sends notifications** (desktop toast / web push hooks ready).
- **Opens multiple live cameras** simultaneously for monitoring.
- **Shows per-class metrics & stats** after runs.

![Detection statistics](images/detection_stats.jpg)

---

## 🧠 Architecture (high level)
- **Training (Colab)**: a notebook builds a YOLOv8 dataset from your video(s), optionally assists labeling, trains, and exports `best.pt`.
- **Runtime (Local App)**: Python app loads `best.pt`, opens N live camera streams, detects keys, tracks motion, and triggers events (notifications + screenshots).
- **Modular design**: `training/`, `inference/`, `ui/`, `events/` for clean separation.


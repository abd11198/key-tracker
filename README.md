🔑 KeyTracker
Camera-Based AI Key Detection & Movement Monitoring (YOLOv8)

KeyTracker is an AI-powered computer vision system that detects and tracks personal keys using YOLOv8 and real-time camera feeds.

The system monitors your environment, detects trained keys, tracks their movement, and automatically sends alerts when a key has been moved or relocated.

It is designed as a practical smart-environment assistant that helps prevent losing important personal items.

🚀 Features

🔍 Real-time key detection using YOLOv8

🧠 Custom key training pipeline from user videos

🎥 Multi-camera monitoring

📸 Automatic screenshot capture when movement is detected

📢 Movement notifications when a key is relocated

📊 Per-class detection statistics

⚡ Optimized for small-object detection

🧩 Modular architecture for training, inference, and event handling

🧠 How It Works

The system has two main stages:

1️⃣ Training Pipeline (Google Colab)

Upload a video of your keys

Extract frames automatically

Generate training images

Train a YOLOv8 object detection model

Export the trained model (best.pt)

The training pipeline includes:

Smart frame extraction

Dataset splitting

Auto labeling support

Augmentation

Small-object optimization

2️⃣ Real-Time Detection (Local Python App)

After training:

The system loads the trained model

Opens one or more live camera feeds

Detects keys in real time

Tracks motion across frames

Triggers events when a key stops moving

When movement is confirmed the system:

Saves a screenshot

Logs the event

Sends a notification

Example message:

Key "abed_key" has been moved.
Detected near: wallet





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

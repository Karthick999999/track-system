                                                  https://0d6d15e5-057f-4687-a7e1-cdebed4f50a9-00-wz4o5nck8i5k.spock.replit.dev
                                                  🎯 Intelligent Face Tracker with Auto-Registration & Visitor Counting

An AI-driven face detection, recognition, and tracking system built for real-time visitor counting.
The system processes a video stream (file or RTSP camera) to detect, auto-register, recognize, and track unique visitors. Every entry and exit is logged with timestamped images and stored in both the filesystem and a database.

🚀 Objective

The goal of this project is to accurately count the number of unique visitors in a video stream by combining:

Real-time face detection (YOLO)

Facial embedding generation (InsightFace / ArcFace)

Face tracking across frames (OpenCV + DeepSort/ByteTrack)

Structured logging & database storage

🧩 Core Functional Modules
1. Face Detection, Recognition & Tracking (Python + YOLO + InsightFace + DB)

Input: Sample video (provided) → later tested with live RTSP stream

Detection: YOLOv8 for real-time face detection

Recognition: Embedding generation with InsightFace / ArcFace

Auto-registration of new faces → assign unique IDs and store in DB

Configurable frame skip parameter (config.json) to optimize performance

2. Logging System (Python + Filesystem + Database)

Each entry/exit event generates:

Cropped face image

Timestamp

Event type (Entry / Exit)

Face ID

Storage:

Local filesystem → logs/entries/YYYY-MM-DD/

Database → metadata for each event

events.log tracks all system-level actions:

Face registration, recognition, entry/exit

Embedding generation & tracking

3. Unique Visitor Counting

Maintain accurate count of unique visitors per stream

Prevent duplicate counting if a visitor reappears

Count retrievable via database queries or log parsing

📂 Project Structure
intelligent-face-tracker/
│── app.py               
│── config.json           
│── requirements.txt     
│── /logs                
│── /database             
│── events.log  

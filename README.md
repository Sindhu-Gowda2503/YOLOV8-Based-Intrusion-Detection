# Real-Time Weapon Detection System

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Flask](https://img.shields.io/badge/Flask-2.0+-green.svg)
![YOLO](https://img.shields.io/badge/YOLO-v8-orange.svg)
![Twilio](https://img.shields.io/badge/Twilio-SMS-red.svg)
![License](https://img.shields.io/badge/License-MIT-blue.svg)

A **real-time weapon detection system** built with Flask, YOLOv8, and OpenCV, designed for surveillance and security applications. This project processes live video feeds to detect weapons (e.g., guns, knives, suspicious objects), logs detections in a database, sends instant alerts via a web interface and SMS, and provides historical analysis of detected threats.

## Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Model Training](#model-training)
- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Database Structure](#database-structure)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgements](#acknowledgements)

## Project Overview

This project leverages the power of **YOLOv8** for real-time object detection to identify weapons in video streams, making it suitable for enhancing security in public spaces like schools, malls, or airports. The system processes video feeds from a webcam or file, detects predefined weapon classes, and performs the following actions:

- **Logs Detections**: Stores details (timestamp, weapon type, location, screenshot) in a SQLite database.
- **Real-Time Alerts**: Notifies users instantly via a web interface (using WebSocket) and SMS (using Twilio).
- **Historical Analysis**: Provides APIs to retrieve past detections and analyze weapon distribution.
- **Screenshots**: Captures and saves images of detected weapons for evidence.

The backend is built with **Flask**, ensuring a robust and scalable server, while the frontend (assumed to be a separate React-based application) offers a user-friendly interface for monitoring.

## Features

- **Real-Time Weapon Detection**: Identifies guns, knives, and suspicious objects in live video with high accuracy.
- **Live Video Streaming**: Displays annotated video feed with bounding boxes around detected weapons.
- **Instant Notifications**:
  - Web alerts via Flask-SocketIO for immediate user updates.
  - SMS alerts via Twilio, including weapon details and timestamp.
- **Database Storage**: Logs all detections in SQLite for record-keeping.
- **Historical Data Access**: API to retrieve past detections for review.
- **Weapon Distribution Analysis**: API to analyze the frequency of different weapon types.
- **Cooldown Mechanism**: Prevents duplicate alerts for the same detection event (60-second cooldown).
- **Screenshot Capture**: Saves images of detected weapons for evidence or investigation.


## Technologies Used

### Backend
- **Python 3.8+**: Core programming language.
- **Flask**: Web framework for server-side logic and API endpoints.
- **Flask-SocketIO**: Enables real-time WebSocket communication for alerts.
- **Flask-SQLAlchemy**: Manages SQLite database interactions.
- **Flask-CORS**: Supports cross-origin requests from the frontend.
- **Ultralytics YOLOv8**: Object detection model for identifying weapons.
- **OpenCV (cv2)**: Handles video capture and frame processing.
- **Twilio**: Sends SMS notifications for detected threats.
- **Threading**: Ensures non-blocking SMS sending.

### Database
- **SQLite**: Lightweight database for storing detection records.

### Frontend (Assumed)
- **React/Vue/Angular**: Likely used for the client-side interface (running at `http://localhost:3000`).
- **Socket.IO Client**: Receives real-time detection alerts.
- **Axios/Fetch**: Makes HTTP requests to backend APIs.






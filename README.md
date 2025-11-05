# 📹 Video Surveillance System with Raspberry Pi

[![Raspberry Pi](https://img.shields.io/badge/Raspberry%20Pi-Compatible-red)](https://www.raspberrypi.org/)
[![Python](https://img.shields.io/badge/Python-3.x-blue)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-Web%20Framework-green)](https://flask.palletsprojects.com/)
[![Telegram](https://img.shields.io/badge/Telegram-Bot%20API-blue)](https://telegram.org/)

**Final Degree Project**: A low-cost intelligent video surveillance system built on Raspberry Pi that enables real-time monitoring through Telegram and a web interface.

## 📋 Project Overview

This project demonstrates the development of a complete home security solution using affordable, accessible hardware. The goal was to create a surveillance system that combines advanced features with low cost, making home security accessible to everyone.

The system was designed for personal and home environments, offering homeowners an additional security tool that can be monitored from anywhere in the world using just a smartphone with internet access.

### Why This Project?

- **Affordability**: Uses inexpensive hardware (Raspberry Pi) instead of costly commercial systems
- **Accessibility**: Control everything through Telegram - an app most people already have
- **Flexibility**: Easy to configure and adapt to different environments
- **Learning**: Demonstrates integration of IoT, web technologies, and mobile communication

## 🎯 Main Objectives

1. **Remote Monitoring**: Enable users to monitor their home from anywhere with internet
2. **Automated Alerts**: Detect movement and send instant notifications
3. **Dual Interface**: Provide both mobile (Telegram) and web access
4. **Cost-Effective**: Prove that effective security doesn't require expensive equipment
5. **Educational**: Showcase practical application of embedded systems and web development

## 🏗️ System Architecture

The project consists of two main components working together:

### 1. Security System (Telegram Bot)

The core security module that runs continuously on the Raspberry Pi:

- **Motion Detection**: PIR sensor monitors for movement in the area
- **Camera Module**: Captures photos and streams video on demand
- **Telegram Integration**: Bot interface for remote control and notifications
- **IR Remote**: Physical remote control to activate/deactivate without phone
- **Alert System**: Buzzer provides local audio alerts when motion is detected
- **Authentication**: Verifies user identity through Telegram chat_id

**How it works:**
1. User sends commands through Telegram (like "take photo" or "activate system")
2. Bot processes the request and interacts with hardware (camera, sensors)
3. When motion is detected, PIR sensor triggers an alert
4. System captures photo and sends it instantly to user's Telegram
5. Buzzer sounds locally to alert anyone present

### 2. Web Platform

A Flask-based web interface for viewing and managing captured content:

- **User Authentication**: Login system to secure access
- **Media Gallery**: View all captured photos and videos
- **Live Streaming**: Watch real-time video feed from the camera
- **Responsive Design**: Works on desktop and mobile browsers
- **Storage Management**: Automatically saves and organizes captures

**How it works:**
1. User accesses web interface through browser
2. Logs in with credentials
3. Views gallery of all stored images and videos
4. Can watch live streaming directly in the browser

## ✨ Key Features

### Telegram Bot Commands
- 🤖 `/start` - Initialize bot and display control menu
- 📸 **Instant Capture** - Request photo of current view
- 🚨 **Activate System** - Enable motion detection and alerts
- 🔕 **Deactivate System** - Disable motion detection
- 🎥 **Video Streaming** - Get link to live video feed

### Technical Capabilities
- **Real-time notifications** when motion is detected
- **Multi-platform access** (Telegram mobile app + web browser)
- **Local and remote control** (IR remote + internet)
- **Automated recording** of security events
- **Low power consumption** suitable for 24/7 operation

## 🛠️ Technology Stack

### Hardware Components
- **Raspberry Pi**: Main computing unit (any model with GPIO and camera support)
- **Pi Camera Module**: Captures photos and video streams
- **PIR Motion Sensor**: Detects movement in monitored area
- **IR Receiver**: Receives signals from infrared remote control
- **Buzzer**: Provides audible alerts
- **Power Supply**: Ensures stable 24/7 operation

### Software & Libraries
- **Python 3**: Main programming language
- **python-telegram-bot**: Telegram Bot API integration
- **Flask**: Web framework for the interface
- **picamera**: Raspberry Pi camera control
- **wiringpi**: GPIO pin control for sensors and buzzer
- **Pillow (PIL)**: Image processing and manipulation

## 📁 Project Structure

```
├── Código fuente/
│   ├── Sistema seguridad/          # Telegram bot and security system
│   │   ├── Main.py                 # Application entry point
│   │   ├── Bot.py                  # Telegram bot implementation
│   │   ├── Bot_Manager.py          # Handles bot requests and responses
│   │   ├── Bot_Message.py          # Message formatting and sending
│   │   ├── Camara_Pi.py           # Camera control and image capture
│   │   ├── Sensor_Pir.py          # Motion sensor monitoring
│   │   ├── Buzzer.py              # Alert buzzer control
│   │   ├── IR_Remote.py           # Infrared remote handler
│   │   ├── Server.py              # Network server for streaming
│   │   ├── Data_Server.py         # Data management
│   │   ├── Hilo.py                # Thread management
│   │   ├── piBot.py               # Bot utilities
│   │   └── Constantes.py          # Configuration constants
│   │
│   └── Plataforma web/             # Web interface
│       ├── Main.py                 # Web app launcher
│       ├── app.py                  # Flask application
│       ├── camera_pi_streaming.py  # Video streaming handler
│       └── templates/              # HTML templates
│           ├── index.html          # Main gallery page
│           ├── login.html          # Authentication page
│           └── stream_video.html   # Live stream viewer
│
├── Fotografias/                    # Stored photo captures
├── Videos demostración/            # Demo videos of the system
├── Informes/                       # Project documentation and reports
└── Poster/                         # Presentation materials
```

## 🔧 How It Works

### Motion Detection Flow
```
PIR Sensor detects movement
    ↓
System triggers alert
    ↓
Camera captures photo
    ↓
Photo sent to Telegram
    ↓
Buzzer sounds alert
    ↓
Photo saved to storage
```

### User Request Flow
```
User sends command via Telegram
    ↓
Bot authenticates user (chat_id)
    ↓
Bot_Manager processes request
    ↓
Appropriate hardware module activated
    ↓
Result sent back to user
```

## 💡 Design Decisions

### Why Telegram?
- **Universal Access**: Works on any device with internet
- **No Custom App**: Users don't need to install a special app
- **Reliable Notifications**: Telegram's push notifications are fast and reliable
- **Bot API**: Well-documented, easy to integrate
- **Secure**: Built-in encryption and authentication

### Why Flask for Web?
- **Lightweight**: Doesn't overload the Raspberry Pi
- **Python Integration**: Works seamlessly with camera and bot code
- **Simple Deployment**: Easy to run on the Pi
- **Flexible**: Easy to customize and extend

### Why Raspberry Pi?
- **Affordable**: Much cheaper than commercial security systems
- **GPIO Pins**: Easy to connect sensors and other hardware
- **Camera Support**: Native camera module integration
- **Low Power**: Can run 24/7 without high electricity costs
- **Community**: Large community for support and resources

## 🎓 Learning Outcomes

This project demonstrates practical skills in:

- **Embedded Systems**: Working with Raspberry Pi, sensors, and GPIO
- **IoT Development**: Connecting physical devices to the internet
- **Web Development**: Creating functional web interfaces with Flask
- **Bot Development**: Building interactive Telegram bots
- **Multi-threading**: Managing concurrent operations (streaming, motion detection, bot)
- **System Integration**: Combining multiple technologies into one cohesive system
- **Hardware-Software Interface**: Bridging physical sensors with software logic

## 🚀 Potential Improvements

Future enhancements could include:

- **Cloud Storage**: Upload captures to cloud services (Google Drive, Dropbox)
- **Face Recognition**: Identify known vs unknown people
- **Multiple Cameras**: Support for monitoring multiple rooms
- **Video Recording**: Automatic video recording when motion detected
- **Machine Learning**: Smart detection to reduce false alarms
- **Mobile App**: Native mobile application instead of just web/Telegram
- **Two-way Audio**: Communicate through the system
- **Smart Home Integration**: Connect with other IoT devices

## 📝 About This Project

This was developed as a **final degree project** to demonstrate the practical application of various technologies in creating a real-world solution. The project shows that with modern, affordable hardware and open-source software, anyone can build sophisticated systems that were once only available from expensive commercial vendors.

The focus was on creating something functional, useful, and educational - proving that the Raspberry Pi ecosystem is mature enough for serious home security applications.

## 👨‍💻 Author

**domenss**

## 📧 Contact

For questions about the project or implementation details, feel free to open an issue in the repository.

---

⭐ If you found this project interesting or useful for your own learning, please give it a star!

# 🎮 Eye Controlled Cursor Using Python 

**Control YouTube with your face and voice!** An enhanced version of FaceMouse that integrates facial gesture control with YouTube playback control and voice commands.

![OpenCV](https://img.shields.io/badge/OpenCV-4.5+-red) ![Selenium](https://img.shields.io/badge/Selenium-4.15+-orange)

## ✨ Features

### 🎯 **Facial Gesture Control**
- **Head Movement**: Control mouse cursor by moving your head
- **Eye Blinks**: Different blink patterns control different actions
- **Real-time Processing**: Smooth, responsive facial tracking

### 🎬 **YouTube Control**
- **Play/Pause**: Toggle video playback
- **Volume Control**: Increase/decrease volume
- **Video Navigation**: Next/previous video, seek forward/backward
- **Video Controls**: Like, subscribe, fullscreen toggle
- **Settings Access**: Open YouTube settings menu

### 🎤 **Voice Commands**
- **Playback**: "play", "pause", "stop"
- **Audio**: "mute", "unmute", "volume up", "volume down"
- **Navigation**: "next", "previous", "forward", "backward"
- **Interface**: "fullscreen", "settings", "like", "subscribe"

### 🔄 **Dual Mode System**
- **Mouse Mode**: Traditional mouse control with facial gestures
- **YouTube Mode**: YouTube-specific controls with voice commands

## 📋 System Requirements

### **Hardware Requirements**
- **Webcam**: Any standard webcam (built-in or external)
- **Microphone**: For voice commands
- **Internet Connection**: For YouTube access and model download
- **Minimum RAM**: 4GB (8GB recommended)
- **Processor**: Intel i3 or equivalent (i5+ recommended)

### **Software Requirements**
- **Operating System**: Windows 10/11, macOS, or Linux
- **Python**: 3.8 or higher
- **Chrome Browser**: Latest version (for YouTube control)
- **Visual C++ Redistributable**: For Windows users

## 🚀 Quick Start (3-Command Setup)

### **Command 1: Install Python Dependencies**
```bash
pip install -r requirements.txt
```

### **Command 2: Download Facial Recognition Model**
```bash
# Download the facial landmark model
curl -O http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2

# Decompress the model
python -c "import bz2; data = bz2.decompress(open('shape_predictor_68_face_landmarks.dat.bz2', 'rb').read()); open('shape_predictor_68_face_landmarks.dat', 'wb').write(data); print('✅ Model downloaded and decompressed successfully!')"
```

### **Command 3: Run FaceMouse YouTube Controller**
```bash
python face_mouse_youtube.py
```

## 📁 Project Files

```
FaceMouse-YouTube/
├── face_mouse_youtube.py      # Main application (enhanced with YouTube control)
├── youtube_controller.py      # YouTube control module
├── test_youtube_controller.py # Test script for YouTube functionality
├── requirements.txt           # Python dependencies
├── README.md                  # This file
├── shape_predictor_68_face_landmarks.dat  # Facial landmark model (99MB)
└── shape_predictor_68_face_landmarks.dat.bz2  # Compressed model file
```

## 🎮 Usage Guide

### **Starting the Application**
```bash
python face_mouse_youtube.py
```

### **Keyboard Controls**
- **`h`** - Show help menu
- **`y`** - Toggle YouTube mode ON/OFF
- **`q`** - Quit application

### **Mouse Mode Gestures** (Default Mode)
- **1 Blink** → Left Click
- **2 Blinks** → Double Click
- **3 Blinks** → Mouse Down (Drag)
- **4+ Blinks** → Right Click

### **YouTube Mode Gestures** (Press 'y' to activate)
- **1 Blink** → Play/Pause video
- **2 Blinks** → Next video
- **3 Blinks** → Mute/Unmute
- **4 Blinks** → Fullscreen toggle
- **5 Blinks** → Like video
- **6 Blinks** → Volume up
- **7 Blinks** → Volume down
- **8+ Blinks** → Subscribe

### **Voice Commands** (YouTube Mode)
- **"play"** - Start/resume playback
- **"pause"** - Pause playback
- **"mute"** - Mute audio
- **"unmute"** - Unmute audio
- **"volume up"** - Increase volume
- **"volume down"** - Decrease volume
- **"next"** - Next video
- **"previous"** - Previous video
- **"fullscreen"** - Toggle fullscreen
- **"like"** - Like current video
- **"subscribe"** - Subscribe to channel
- **"settings"** - Open settings menu

## 🔧 Detailed Setup Instructions

### **Step 1: Install Python**
1. Download Python 3.8+ from [python.org](https://python.org)
2. During installation, check "Add Python to PATH"
3. Verify installation: `python --version`

### **Step 2: Install Dependencies**
```bash
# Upgrade pip first
python -m pip install --upgrade pip

# Install all required packages
pip install -r requirements.txt
```

### **Step 3: Download Facial Recognition Model**
```bash
# Download compressed model (64MB)
curl -O http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2

# Decompress model (creates 99MB .dat file)
python -c "import bz2; data = bz2.decompress(open('shape_predictor_68_face_landmarks.dat.bz2', 'rb').read()); open('shape_predictor_68_face_landmarks.dat', 'wb').write(data); print('✅ Model decompressed successfully!')"
```

### **Step 4: Verify Installation**
```bash
# Test core dependencies
python -c "import cv2, dlib, mouse, numpy as np, scipy; print('✅ Core dependencies working!')"

# Test YouTube controller
python -c "from youtube_controller import YouTubeController; print('✅ YouTube controller ready!')"

# Test audio system
python -c "import pygame; pygame.mixer.init(); print('✅ Audio system working!')"
```

### **Step 5: Run Application**
```bash
python face_mouse_youtube.py
```

## 🐛 Troubleshooting

### **Common Issues & Solutions**

#### **1. Camera Not Working**
```bash
# Check available cameras
python -c "import cv2; print([i for i in range(5) if cv2.VideoCapture(i).isOpened()])"

# Try different camera index in code (change cv2.VideoCapture(0) to cv2.VideoCapture(1))
```

#### **2. Chrome Driver Issues**
```bash
# Install Chrome driver manually
python -c "from webdriver_manager.chrome import ChromeDriverManager; print(ChromeDriverManager().install())"

# Or update Chrome to latest version
```

#### **3. Audio/Microphone Issues**
```bash
# Test microphone
python -c "import speech_recognition as sr; sr.Microphone().list_microphone_names()"

# Install PyAudio dependencies for Windows
pip install pipwin
pipwin install pyaudio
```

#### **4. Permission Errors**
```bash
# Run as administrator (Windows)
# Or check antivirus settings
```

#### **5. Import Errors**
```bash
# Reinstall specific package
pip uninstall package_name
pip install package_name

# Clear pip cache
pip cache purge
```

### **Error Messages & Solutions**

| Error | Solution |
|-------|----------|
| `No module named 'dlib'` | `pip install dlib` |
| `No module named 'selenium'` | `pip install selenium` |
| `Chrome driver not found` | `pip install webdriver-manager` |
| `Microphone not working` | `pip install pyaudio` |
| `OpenCV camera error` | Check camera permissions/connections |
| `Model file not found` | Download and decompress the facial model |

## ⚙️ Configuration

### **Adjust Sensitivity**
Edit these values in `face_mouse_youtube.py`:
```python
sclFact = 6          # Cursor movement sensitivity (default: 6)
EYE_AR_THRESH = 0.20 # Blink detection threshold (default: 0.20)
```

### **Camera Settings**
```python
vs = cv2.VideoCapture(0)  # Change 0 to 1, 2, etc. for different cameras
```

### **Chrome Options**
Edit `youtube_controller.py` for browser preferences:
```python
chrome_options.add_argument("--start-maximized")  # Window size
chrome_options.add_argument("--disable-gpu")      # Performance
```

## 📊 Performance Tips

### **For Better Performance**
1. **Good Lighting**: Ensure well-lit environment
2. **Stable Position**: Sit at consistent distance from camera
3. **Reduce Background Movement**: Minimize distractions behind you
4. **Close Other Applications**: Free up system resources
5. **Use External Webcam**: Better quality than built-in cameras

### **System Optimization**
```bash
# Update graphics drivers
# Close unnecessary background applications
# Use SSD storage for better I/O performance
```

## 🔮 Advanced Features

### **Custom Gestures**
Modify gesture mappings in `youtube_controller.py`:
```python
self.gesture_commands = {
    1: 'play_pause',      # 1 blink = play/pause
    2: 'next',            # 2 blinks = next video
    # Add your custom gestures here
}
```

### **Voice Command Languages**
```python
# Add language support in youtube_controller.py
recognizer.recognize_google(audio, language='en-US')  # English
recognizer.recognize_google(audio, language='es-ES')  # Spanish
```

## 📞 Support & Help

### **Getting Help**
1. Check the troubleshooting section above
2. Verify all dependencies are installed
3. Test individual components before full integration
4. Check console output for specific error messages

### **Common Questions**
- **Q: Can I use it without a camera?**
  - A: The facial gestures require a camera, but voice commands work without camera
- **Q: Does it work on Mac/Linux?**
  - A: Yes, with appropriate dependencies installed
- **Q: Can I customize the gestures?**
  - A: Yes, modify the gesture mappings in the code

## 📄 License

This project is based on the original FaceMouse project. Please refer to the original license terms.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

---

**🎮 Enjoy hands-free YouTube control with FaceMouse!**

*Made with ❤️ for the computer vision and automation community*

---

## 📝 Quick Reference

### **3-Command Setup:**
```bash
pip install -r requirements.txt
curl -O http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2
python -c "import bz2; data = bz2.decompress(open('shape_predictor_68_face_landmarks.dat.bz2', 'rb').read()); open('shape_predictor_68_face_landmarks.dat', 'wb').write(data); print('✅ Setup complete!')"
```

### **Run Application:**
```bash
python face_mouse_youtube.py
```

### **Controls:**
- **Press 'y'** → YouTube mode
- **Press 'h'** → Help
- **Press 'q'** → Quit

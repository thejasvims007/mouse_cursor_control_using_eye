# 🎮 Eye Controlled Cursor Using Python

**Control your mouse with facial gestures!** A Python application that uses computer vision to track facial movements and eye blinks for hands-free mouse control.

![OpenCV](https://img.shields.io/badge/OpenCV-4.5+-red) ![Dlib](https://img.shields.io/badge/Dlib-19.22+-blue)

## ✨ Features

### 🎯 **Facial Gesture Control**
- **Head Movement**: Control mouse cursor by moving your head
- **Eye Blinks**: Different blink patterns control different actions
- **Real-time Processing**: Smooth, responsive facial tracking

### 🔄 **Mouse Controls**
- **1 Blink** → Left Click
- **2 Blinks** → Double Click
- **3 Blinks** → Mouse Down (Drag)
- **4+ Blinks** → Right Click

## 📋 System Requirements

### **Hardware Requirements**
- **Webcam**: Any standard webcam (built-in or external)
- **Minimum RAM**: 4GB (8GB recommended)
- **Processor**: Intel i3 or equivalent (i5+ recommended)

### **Software Requirements**
- **Operating System**: Windows 10/11
- **Python**: 3.8 or higher
- **Visual C++ Redistributable**: For Windows users

## 🚀 Quick Start (2-Command Setup)

### **Command 1: Install Python Dependencies**
```bash
pip install -r requirements.txt
```

### **Command 2: Run the Application**
```bash
# Option 1: Run directly with Python
python face_mouse_youtube.py

# Option 2: Use the Windows batch file (recommended)
run.bat
```

## 📁 Project Files

```
mouse_cursor_control_using_eye/
├── face_mouse_youtube.py      # Main application script
├── requirements.txt           # Python dependencies
├── run.bat                    # Windows batch file to run the app
├── README.md                  # This file
├── shape_predictor_68_face_landmarks.dat  # Facial landmark model (99MB)
├── shape_predictor_68_face_landmarks.dat.bz2  # Compressed model file
└── dlib-19.22.99-cp38-cp38-win_amd64.whl  # Dlib wheel for Windows
```

## 🎮 Usage Guide

### **Starting the Application**
Run one of the commands above. The application will:
- Check for the facial landmark model file
- Initialize the webcam
- Start tracking your face

### **Controls**
- **Move head** → Move cursor
- **1 blink** → Left click
- **2 blinks** → Double click
- **3 blinks** → Mouse down (drag)
- **4+ blinks** → Right click
- **Press 'h'** → Show help
- **Press 'q'** → Quit

### **Tips for Best Results**
- Ensure good lighting on your face
- Sit at a consistent distance from the camera
- Keep your head movements smooth
- Blink deliberately for clicks

## 🔧 Detailed Setup Instructions

### **Step 1: Install Python**
1. Download Python 3.8+ from [python.org](https://python.org)
2. During installation, check "Add Python to PATH"
3. Verify installation: `python --version`

### **Step 2: Install Dependencies**
```bash
# Install all required packages
pip install -r requirements.txt
```

### **Step 3: Verify Installation**
```bash
# Test core dependencies
python -c "import cv2, dlib, mouse, numpy as np, scipy; print('✅ Core dependencies working!')"
```

### **Step 4: Run Application**
```bash
python face_mouse_youtube.py
```

## 🐛 Troubleshooting

### **Common Issues & Solutions**

#### **1. Camera Not Working**
```bash
# Check available cameras
python -c "import cv2; print([i for i in range(5) if cv2.VideoCapture(i).isOpened()])"
```
- Try different camera index in code (change `cv2.VideoCapture(0)` to `cv2.VideoCapture(1)`)

#### **2. Import Errors**
```bash
# Reinstall specific package
pip uninstall package_name
pip install package_name

# Clear pip cache
pip cache purge
```

#### **3. Model File Missing**
The model file `shape_predictor_68_face_landmarks.dat` should be present. If missing:
```bash
# Download and decompress
curl -O http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2
python -c "import bz2; data = bz2.decompress(open('shape_predictor_68_face_landmarks.dat.bz2', 'rb').read()); open('shape_predictor_68_face_landmarks.dat', 'wb').write(data); print('✅ Model decompressed successfully!')"
```

#### **4. Permission Errors**
- Run as administrator (Windows)
- Check antivirus settings

### **Error Messages & Solutions**

| Error | Solution |
|-------|----------|
| `No module named 'dlib'` | `pip install dlib` or use the provided wheel |
| `No module named 'cv2'` | `pip install opencv-python` |
| `Camera not opened` | Check camera permissions/connections |
| `Model file not found` | Download and decompress the facial model |

## ⚙️ Configuration

### **Adjust Sensitivity**
Edit these values in `face_mouse_youtube.py`:
```python
sclFact = 4          # Cursor movement sensitivity (default: 4)
EYE_AR_THRESH = 0.20 # Blink detection threshold (default: 0.20)
```

### **Camera Settings**
```python
vs = cv2.VideoCapture(0)  # Change 0 to 1, 2, etc. for different cameras
```

## 📊 Performance Tips

### **For Better Performance**
1. **Good Lighting**: Ensure well-lit environment
2. **Stable Position**: Sit at consistent distance from camera
3. **Reduce Background Movement**: Minimize distractions behind you
4. **Close Other Applications**: Free up system resources
5. **Use External Webcam**: Better quality than built-in cameras

### **System Optimization**
- Update graphics drivers
- Close unnecessary background applications
- Use SSD storage for better I/O performance

## 📞 Support & Help

### **Getting Help**
1. Check the troubleshooting section above
2. Verify all dependencies are installed
3. Test individual components before full integration
4. Check console output for specific error messages

### **Common Questions**
- **Q: Can I use it without a camera?**
  - A: No, the facial gestures require a camera
- **Q: Does it work on Mac/Linux?**
  - A: The code is cross-platform, but dependencies may need adjustment
- **Q: Can I customize the gestures?**
  - A: Yes, modify the blink thresholds and actions in the code

## 📄 License

This project is open-source. Please refer to standard open-source licenses.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

---

**🎮 Enjoy hands-free mouse control with FaceMouse!**

*Made with ❤️ for the computer vision community*

---

## 📝 Quick Reference

### **2-Command Setup:**
```bash
pip install -r requirements.txt
python face_mouse_youtube.py
```

### **Controls:**
- **Move head** → Cursor movement
- **1 blink** → Left click
- **2 blinks** → Double click
- **3 blinks** → Drag
- **4+ blinks** → Right click
- **'h'** → Help
- **'q'** → Quit

# 🎭 MoodSense - AI Emotion Detection App

A real-time emotion detection web application that uses advanced facial landmark tracking and machine learning to analyze emotions through your webcam. Built with TensorFlow.js and MediaPipe for accurate facial expression recognition.


## ✨ Features

### 🎥 Real-time Camera Integration
- **Seamless webcam access** with comprehensive permission handling
- **Front-facing camera preference** for optimal face detection
- **High-resolution video capture** (640x480 ideal, 320x240 minimum)
- **Cross-platform compatibility** (Chrome, Firefox, Safari, Edge)

### 🔍 Advanced Facial Tracking
- **468 facial landmark points** tracked in real-time
- **Dynamic tracking lines** that follow your facial movements
- **Visual feedback** with color-coded elements:
  - 🟢 Green bounding box around detected faces
  - 🌸 Pink tracking lines connecting facial landmarks
  - 🔵 Cyan dots highlighting key facial points
- **Responsive tracking** that adapts to head movements and angles

### 🧠 Intelligent Emotion Detection
- **Six emotion categories** detected:
  - 😊 Happy
  - 😢 Sad
  - 😮 Surprised
  - 😠 Angry
  - 😨 Fearful
  - 😐 Neutral
- **Confidence scoring** for each detected emotion
- **Real-time analysis** based on facial geometry:
  - Mouth aspect ratio and width
  - Eye openness measurements
  - Facial proportions and distances

### 📊 Interactive Dashboard
- **Live emotion display** showing current detected emotion
- **Confidence percentage** for accuracy feedback
- **Mood history chart** tracking emotions over time
- **Visual legend** with color-coded emotion indicators
- **Responsive design** that works on desktop and mobile

## 🚀 Quick Start

### Prerequisites
- Modern web browser with camera support
- Webcam or built-in camera
- Internet connection (for loading AI models)

### Installation & Setup

1. **Clone or download** the project files
   ```bash
   git clone [your-repo-url]
   cd AI-Emotion-detect
   ```

2. **Start a local web server** (recommended for best performance)
   
   **Option A: Python (if installed)**
   ```bash
   python3 -m http.server 4000
   ```
   
   **Option B: Node.js (if installed)**
   ```bash
   npx serve . -p 4000
   ```
   
   **Option C: Direct file opening**
   - Double-click `Ai Motion.html` to open in your default browser
   - ⚠️ Note: Some features may be limited without a local server

3. **Open in browser**
   - Navigate to `http://localhost:4000/Ai%20Motion.html`
   - Or open the HTML file directly in your browser

4. **Allow camera access** when prompted by your browser

## 📱 How to Use

### Getting Started
1. **Launch the app** and ensure your camera is working
2. **Click "Start Detection"** to begin emotion tracking
3. **Position your face** in front of the camera
4. **Watch the magic happen** as tracking lines follow your facial movements

### Using the Interface

#### 🎮 Control Panel
- **Start Detection**: Initiates real-time emotion analysis
- **Stop Detection**: Pauses tracking and clears the display
- **Status Messages**: Real-time feedback on app state

#### 📊 Dashboard Elements
- **Current Emotion**: Shows the most recently detected emotion
- **Confidence Score**: Indicates the reliability of the detection (0-1 scale)
- **Mood Chart**: Visual history of detected emotions
- **Tracking Visualization**: Live facial landmark overlay

### Tips for Best Results
- **Good lighting**: Ensure your face is well-lit for better detection
- **Face the camera**: Position yourself directly in front of the webcam
- **Stable position**: Avoid rapid movements for more accurate tracking
- **Clear view**: Remove glasses or hats if they interfere with detection

## 🛠️ Technical Details

### Architecture
- **Frontend**: Pure HTML5, CSS3, and JavaScript (ES6+)
- **AI Framework**: TensorFlow.js 3.11.0
- **Face Detection**: MediaPipe Face Landmarks Detection
- **Camera API**: MediaDevices.getUserMedia()
- **Canvas API**: For real-time overlay rendering

### Key Components

#### Face Detection Model
```javascript
// Uses MediaPipe FaceMesh for 468 facial landmark points
model = await faceLandmarksDetection.load(
    faceLandmarksDetection.SupportedPackages.mediapipeFacemesh
);
```

#### Emotion Analysis Algorithm
- **Facial Geometry Analysis**: Calculates mouth aspect ratio, eye openness, and facial proportions
- **Threshold-based Classification**: Uses predefined thresholds for emotion detection
- **Confidence Scoring**: Based on measurement consistency and facial feature clarity

#### Tracking Visualization
- **468 Landmark Points**: Complete facial mesh mapping
- **Key Connections**: Face outline, eyes, eyebrows, nose, and mouth
- **Real-time Rendering**: Canvas-based overlay with smooth 60fps updates

### Browser Compatibility
| Browser | Version | Status |
|---------|---------|---------|
| Chrome | 88+ | ✅ Full Support |
| Firefox | 85+ | ✅ Full Support |
| Safari | 14+ | ✅ Full Support |
| Edge | 88+ | ✅ Full Support |

## 🔧 Configuration

### Camera Settings
The app automatically configures optimal camera settings:
```javascript
const stream = await navigator.mediaDevices.getUserMedia({ 
    video: { 
        width: { ideal: 640, min: 320 },
        height: { ideal: 480, min: 240 },
        facingMode: 'user' // Front-facing camera
    } 
});
```

### Detection Parameters
- **Detection Interval**: 300ms for smooth tracking
- **Model Precision**: MediaPipe FaceMesh for high accuracy
- **Confidence Threshold**: 0.5 minimum for emotion classification

## 🐛 Troubleshooting

### Common Issues

#### Camera Not Working
- **Check permissions**: Ensure camera access is allowed in browser settings
- **Try HTTPS**: Some browsers require secure context for camera access
- **Restart browser**: Close and reopen your browser
- **Check camera**: Ensure no other applications are using the camera

#### Poor Detection Accuracy
- **Improve lighting**: Add more light to your face
- **Adjust position**: Move closer to or further from the camera
- **Clear obstructions**: Remove glasses, masks, or hair covering face
- **Stable environment**: Reduce background movement

#### Model Loading Issues
- **Check internet**: Ensure stable internet connection for model download
- **Refresh page**: Reload the application
- **Clear cache**: Clear browser cache and cookies
- **Try different browser**: Test with Chrome or Firefox

### Debug Mode
Open browser console (F12) to see detailed logging:
- Face detection status
- Model loading progress
- Emotion analysis metrics
- Error messages and warnings

## 📈 Performance Optimization

### Best Practices
- **Close other applications** using the camera
- **Use a modern browser** with hardware acceleration
- **Ensure good lighting** for better detection accuracy
- **Stable internet connection** for initial model loading

### System Requirements
- **RAM**: 4GB minimum, 8GB recommended
- **CPU**: Modern multi-core processor
- **GPU**: Hardware acceleration supported
- **Network**: Broadband connection for model download

## 🔒 Privacy & Security

### Data Handling
- **No data storage**: All processing happens locally in your browser
- **No server communication**: No facial data sent to external servers
- **Real-time only**: No recording or saving of video/audio
- **Local processing**: All AI inference runs on your device

### Browser Permissions
The app requests only necessary permissions:
- **Camera access**: For real-time face detection
- **No microphone**: Audio is not captured or processed
- **No location**: Location data is not accessed

## 🚀 Future Enhancements

### Planned Features
- [ ] **Emotion history export** to CSV/JSON
- [ ] **Multiple emotion detection** for multiple faces
- [ ] **Custom emotion training** with user data
- [ ] **Mobile app version** for iOS/Android
- [ ] **Voice emotion analysis** integration
- [ ] **Emotion-based music recommendations**
- [ ] **Mood journaling** with emotion tracking


## 🙏 Acknowledgments

- **TensorFlow.js** team for the amazing ML framework
- **MediaPipe** team for facial landmark detection
- **WebRTC** community for camera access APIs
- **Open source contributors** who made this possible


---

**Made with ❤️ for the AI and emotion recognition community**



# 🦴 X-Ray Hand Tracker

A real-time hand skeleton tracking application that uses AI-powered computer vision to detect and visualize hand joints in real-time. Point your hand at the camera and watch as it tracks all 21 joints per hand with an X-ray skeletal visualization.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Status](https://img.shields.io/badge/status-active-brightgreen.svg)

## ✨ Features

- **Real-time Hand Detection** - Detects up to 2 hands simultaneously with high accuracy
- **Skeletal Visualization** - Shows 21 joint landmarks per hand connected with bones
- **Color-Coded Output** - Blue for left hand, red for right hand
- **Performance Metrics** - Live FPS counter and hand detection statistics
- **Responsive Design** - Works on desktop and mobile devices
- **No Installation Required** - Just open the HTML file in your browser
- **Privacy-Focused** - All processing happens locally in your browser (no data sent to servers)

## 🚀 Quick Start

### Option 1: Direct File (Recommended for Quick Use)
1. Download `index.html`
2. Double-click to open in your browser
3. Click "Start Camera" button
4. Point your hand at the camera

### Option 2: Clone Repository
```bash
git clone https://github.com/yourusername/xray-hand-tracker.git
cd xray-hand-tracker
open index.html
```

### Option 3: Deploy Online
1. Upload the `index.html` file to a web hosting service (GitHub Pages, Netlify, Vercel, etc.)
2. Access it through the provided URL

## 📋 Requirements

- **Modern Web Browser** - Chrome, Firefox, Safari, or Edge (latest versions)
- **Webcam/Camera** - Built-in or external camera
- **Internet Connection** - For loading MediaPipe library (processing is offline)
- **Permissions** - Allow camera access when prompted

## 🎮 How to Use

1. **Start Tracking**
   - Click the "Start Camera" button
   - Grant camera permissions when prompted

2. **Position Your Hand**
   - Move your hand in front of the camera
   - Ensure good lighting for best results

3. **View Tracking Data**
   - See real-time joint positions and connections
   - Monitor FPS and hand detection count
   - Watch the total joints being tracked

4. **Stop Tracking**
   - Click the "Stop Camera" button to end the session

## 🎨 Visual Guide

### Hand Landmarks (21 joints per hand)
```
┌─ Thumb:       0-4
├─ Index:       5-8
├─ Middle:      9-12
├─ Ring:        13-16
├─ Pinky:       17-20
└─ Palm:        0 (Wrist)
```

### Color Coding
- 🔵 **Blue** = Left Hand
- 🔴 **Red** = Right Hand

## ⚙️ Technical Details

### Technologies Used
- **MediaPipe Hands** - ML model for hand detection and tracking
- **TensorFlow.js** - Machine learning framework
- **Canvas API** - Real-time visualization
- **WebRTC** - Camera access

### Browser Support
- ✅ Google Chrome (v90+)
- ✅ Mozilla Firefox (v88+)
- ✅ Apple Safari (v14+)
- ✅ Microsoft Edge (v90+)

### Performance
- Processing speed: 30+ FPS on modern devices
- Latency: < 100ms typically
- CPU usage: Moderate (varies by device)

## 🔒 Privacy & Security

- **No Data Collection** - All video processing happens locally
- **No Uploads** - Your camera feed never leaves your device
- **No Cookies** - No tracking or analytics
- **Open Source** - Code is fully transparent and auditable

## 🛠️ Customization

### Modify Detection Confidence
Edit line ~65 in `index.html`:
```javascript
minDetectionConfidence: 0.5,  // 0.0 to 1.0 (lower = more sensitive)
minTrackingConfidence: 0.5,   // 0.0 to 1.0
```

### Change Hand Limit
Edit line ~64:
```javascript
maxNumHands: 2,  // Change to 1 or 3
```

### Adjust Visual Style
- Change colors by modifying hex values in the color arrays
- Adjust joint size by editing the `ctx.arc()` radius values
- Modify line thickness with `ctx.lineWidth`

## 🐛 Troubleshooting

### Camera Not Working
- Check if browser has camera permissions
- Try restarting the browser
- Test if other apps can access the camera

### Poor Hand Detection
- Ensure adequate lighting
- Move hand closer to camera
- Reduce motion blur (slow hand movements)
- Clean camera lens

### Low FPS
- Close other browser tabs
- Update your browser
- Reduce video resolution in browser settings
- Use a more powerful device

## 📱 Mobile Support

The app works on mobile devices with:
- Chrome for Android
- Safari on iOS 14+
- Firefox Mobile

Touch controls are supported but camera positioning can be tricky.

## 🤝 Contributing

Contributions are welcome! Here's how:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📚 References

- [MediaPipe Hands Documentation](https://mediapipe.dev/docs/mediapipe_solutions/python/solutions/hands)
- [Web Cameras API](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia)
- [Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)

## 📄 License

This project is licensed under the MIT License - see the `LICENSE` file for details.

## 🙏 Acknowledgments

- Built with [MediaPipe](https://mediapipe.dev/) by Google
- Inspired by XR and computer vision research
- Thanks to the open-source community

## 📧 Contact & Support

- Found a bug? Open an issue on GitHub
- Have suggestions? Create a discussion
- Want to collaborate? Drop a message

---

**Made with ❤️ for hand tracking enthusiasts**

⭐ Star this repo if you find it useful!

---

## Quick Stats

- 📦 Single HTML file - no build process
- ⚡ Instant deployment
- 🎯 Real-time performance
- 🌍 Works offline (after first load)
- 🔐 100% privacy-preserving
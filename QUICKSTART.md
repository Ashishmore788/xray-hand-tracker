# 🚀 Quick Start Guide

## How to Run Locally

### Option 1: Direct Open (Easiest)
1. Double-click `index.html`
2. Grant camera permission
3. Click "Start Camera"
4. Done! 🎉

### Option 2: With Python Server
```bash
python -m http.server 8000
# Then visit: http://localhost:8000
```

### Option 3: With Node.js
```bash
npx http-server
```

---

## How to Deploy on GitHub Pages

### Step 1: Create GitHub Repo
```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/xray-hand-tracker.git
git push -u origin main
```

### Step 2: Enable GitHub Pages
1. Go to Repository Settings
2. Select "Pages" from left menu
3. Choose "main" branch
4. Save
5. Your site will be at: `https://YOUR_USERNAME.github.io/xray-hand-tracker/`

---

## File Structure

```
xray-hand-tracker/
├── index.html           # 🎯 Main app (open this!)
├── README.md            # 📖 Full documentation
├── package.json         # 📦 Project info
├── LICENSE              # ⚖️ MIT License
├── .gitignore           # 🙈 Git ignore rules
├── CONTRIBUTING.md      # 🤝 How to contribute
├── CHANGELOG.md         # 📝 Version history
└── QUICKSTART.md        # ⚡ This file
```

---

## Troubleshooting

**Camera not working?**
- Check browser permissions
- Try a different browser
- Restart your browser

**Poor detection?**
- Increase lighting
- Move hand closer
- Use clear hand gestures

**Slow FPS?**
- Close other apps
- Lower screen resolution
- Use a faster device

---

## Features at a Glance

✨ Real-time hand tracking
👐 Detects 2 hands max (21 joints each)
🔵 🔴 Color-coded (left/right)
📊 Live FPS counter
🔒 100% private (offline processing)
📱 Mobile friendly
⚡ Zero setup needed

---

**Enjoy! 🦴✨**

# Filip's Sora AI - To-Do List App with Cross-Platform Support

This guide will help you build and run **Filip's Sora AI** - a powerful To-Do List application on **Android**, **iOS**, **Windows**, and **Linux**.

---

## 📱 Platform-Specific Setup

### **Option 1: Quick Start (All Platforms)**

We provide built app files for download:
- **Windows**: `filips-sora-ai-windows.exe`
- **Linux**: `filips-sora-ai-linux.AppImage`
- **Android**: `filips-sora-ai-android.apk`
- **iOS**: Available on App Store or TestFlight

---

## 🖥️ **Desktop (Windows & Linux)**

### Requirements:
- Node.js (v14+)
- npm or yarn

### Installation Steps:

```bash
# 1. Clone the repository
git clone https://github.com/FilipDaniel16/MyModels.git
cd MyModels/FilipsSoraAI

# 2. Install dependencies
npm install

# 3. Run in development mode
npm start

# 4. Build for production
npm run build

# Windows build
npm run build:windows

# Linux build
npm run build:linux

# Both
npm run build:all
```

### Download Pre-built Executables:
- **Windows**: [filips-sora-ai-windows.exe](https://github.com/FilipDaniel16/MyModels/releases)
- **Linux**: [filips-sora-ai-linux.AppImage](https://github.com/FilipDaniel16/MyModels/releases)

---

## 📱 **Mobile (Android & iOS)**

### Requirements:
- Node.js (v14+)
- React Native CLI
- Android Studio (for Android)
- Xcode (for iOS - macOS only)

### **Android Setup:**

```bash
# 1. Install dependencies
npm install

# 2. Install Android dependencies
npm install -g react-native-cli

# 3. Connect Android device or start emulator
# For emulator, use Android Studio

# 4. Run on Android
npm run android

# 5. Build APK
npm run build:android

# Built APK location: android/app/build/outputs/apk/release/app-release.apk
```

**OR Download Pre-built:**
- Download [filips-sora-ai-android.apk](https://github.com/FilipDaniel16/MyModels/releases)
- Transfer to Android phone
- Open file manager and install

### **iOS Setup (macOS only):**

```bash
# 1. Install dependencies
npm install

# 2. Install CocoaPods
sudo gem install cocoapods

# 3. Install iOS dependencies
cd ios
pod install
cd ..

# 4. Run on iOS
npm run ios

# 5. Build for App Store
npm run build:ios
```

---

## 📦 Installation Methods by Platform

### **Windows**
1. Download `filips-sora-ai-windows.exe`
2. Double-click to install
3. Follow installation wizard
4. App launches automatically

### **Linux (Ubuntu/Debian)**
```bash
# Method 1: AppImage (Recommended)
chmod +x filips-sora-ai-linux.AppImage
./filips-sora-ai-linux.AppImage

# Method 2: Install system-wide
sudo dpkg -i filips-sora-ai-linux.deb
filips-sora-ai  # Run from terminal
```

### **Android**
1. Download `filips-sora-ai-android.apk`
2. Transfer to phone via USB or cloud
3. Go to Settings → Security → Enable "Unknown Sources"
4. Open file manager and tap APK to install
5. Grant permissions when prompted
6. Launch from app drawer

### **iOS**
1. Download from App Store: Search "Filip's Sora AI"
2. OR Join TestFlight: [Invite Link]
3. Tap Install
4. Grant permissions
5. Launch app

---

## 🔧 Build from Source

### **All-in-One Build Script:**

```bash
# For Windows & Linux (Desktop)
npm run build:all

# For Android
npm run build:android

# For iOS (macOS)
npm run build:ios
```

### **Build Outputs:**
```
dist/
├── filips-sora-ai-windows.exe           # Windows installer
├── filips-sora-ai-windows-portable.exe  # Windows portable
├── filips-sora-ai-linux.AppImage        # Linux AppImage
├── filips-sora-ai-linux.deb             # Linux Debian package
android/app/build/outputs/apk/
└── release/app-release.apk              # Android APK
```

---

## 🌐 System Requirements

### **Windows**
- Windows 7 or later (64-bit or 32-bit)
- Minimum 100MB free space
- .NET Framework 4.5+

### **Linux**
- Ubuntu 16.04+, Debian 9+, Fedora 24+
- 100MB free space
- glibc 2.17+

### **Android**
- Android 5.0 (API level 21) or higher
- 50MB free space
- Phone storage

### **iOS**
- iOS 12.0 or higher
- 50MB free space
- iPhone, iPad, or iPod Touch

---

## 📝 Features

✅ Add, edit, delete tasks  
✅ Mark tasks complete  
✅ Filter (All, Pending, Completed, High Priority)  
✅ Local storage (offline support)  
✅ Statistics & analytics  
✅ Priority badges  
✅ Export to JSON  
✅ Dark mode support  
✅ Notifications (mobile)  
✅ Sync across devices (optional)  
✅ AI-powered task suggestions  
✅ Sora AI video generation integration  

---

## ⚙️ Advanced: Manual Build

### **Windows Build:**
```bash
cd desktop
npm install
npm run dist:windows
```

### **Linux Build:**
```bash
cd desktop
npm install
npm run dist:linux
```

### **Android Build:**
```bash
cd mobile
npm install
cd android
./gradlew assembleRelease
```

### **iOS Build:**
```bash
cd mobile
npm install
cd ios
pod install
cd ..
npm run build:ios
```

---

## 🐛 Troubleshooting

### **Windows Installation Issues**
- If installer won't run, disable antivirus temporarily
- Run as Administrator
- Try portable version instead

### **Linux Installation Issues**
```bash
# If AppImage won't run
chmod +x filips-sora-ai-linux.AppImage
./filips-sora-ai-linux.AppImage --no-sandbox
```

### **Android Installation Issues**
- Enable installation from unknown sources
- Clear Google Play cache if needed
- Try different USB cable/connection
- Update Google Play Services

### **iOS Installation Issues**
- Ensure enough storage space
- Update iOS to latest version
- Sign in with valid Apple ID
- Check internet connection

---

## 🔗 App Store Links

- **Android**: [Google Play Store - Filip's Sora AI](https://play.google.com/store/apps/details?id=com.filipkodan.soraaI)
- **iOS**: [App Store - Filip's Sora AI](https://apps.apple.com/app/filips-sora-ai/id1234567890)
- **Windows**: [Microsoft Store - Filip's Sora AI](https://www.microsoft.com/store/apps/9NBLGGH4NNS1)
- **Linux**: [Snap Store - Filip's Sora AI](https://snapcraft.io/filips-sora-ai)

---

## 📞 Support

- **GitHub Issues**: https://github.com/FilipDaniel16/MyModels/issues
- **Email**: filipkodaniel2000@gmail.com
- **Discord**: [Join Community]
- **Twitter**: [@FilipsSoraAI](https://twitter.com/FilipsSoraAI)

---

## 📄 License

MIT License - See LICENSE file

---

## 🎨 App Features Overview

### **Core Functionality**
- Create unlimited to-do tasks
- Set priorities (High, Medium, Low)
- Track completion status
- Filter and search tasks
- Export task lists

### **Sora AI Integration**
- AI-powered task suggestions
- Smart scheduling
- Natural language input
- Task automation

### **Cross-Platform Sync**
- Cloud backup (optional)
- Sync across all devices
- Real-time updates
- Offline mode

---

**Last Updated**: July 14, 2026  
**Version**: 1.0.0  
**App Name**: Filip's Sora AI  
**Platforms**: Windows, Linux, Android, iOS  
**Developer**: Filip Daniel  
**GitHub**: https://github.com/FilipDaniel16/MyModels

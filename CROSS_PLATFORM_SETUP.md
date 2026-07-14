# To-Do List App - Cross-Platform Setup Guide

This guide will help you build and run the To-Do List application on **Android**, **iOS**, **Windows**, and **Linux**.

---

## 📱 Platform-Specific Setup

### **Option 1: Quick Start (All Platforms)**

We provide built app files for download:
- **Windows**: `todo-app-windows.exe`
- **Linux**: `todo-app-linux.AppImage`
- **Android**: `todo-app-android.apk`
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
cd MyModels/TodoApp

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
- **Windows**: [todo-app-windows.exe](https://github.com/FilipDaniel16/MyModels/releases)
- **Linux**: [todo-app-linux.AppImage](https://github.com/FilipDaniel16/MyModels/releases)

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
- Download [todo-app-android.apk](https://github.com/FilipDaniel16/MyModels/releases)
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
1. Download `todo-app-windows.exe`
2. Double-click to install
3. Follow installation wizard
4. App launches automatically

### **Linux (Ubuntu/Debian)**
```bash
# Method 1: AppImage (Recommended)
chmod +x todo-app-linux.AppImage
./todo-app-linux.AppImage

# Method 2: Install system-wide
sudo dpkg -i todo-app-linux.deb
todo-app  # Run from terminal
```

### **Android**
1. Download `todo-app-android.apk`
2. Transfer to phone via USB or cloud
3. Go to Settings → Security → Enable "Unknown Sources"
4. Open file manager and tap APK to install
5. Grant permissions when prompted
6. Launch from app drawer

### **iOS**
1. Download from App Store: Search "To-Do List Pro"
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
├── todo-app-windows.exe           # Windows installer
├── todo-app-windows-portable.exe  # Windows portable
├── todo-app-linux.AppImage        # Linux AppImage
├── todo-app-linux.deb             # Linux Debian package
android/app/build/outputs/apk/
└── release/app-release.apk        # Android APK
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
chmod +x todo-app-linux.AppImage
./todo-app-linux.AppImage --no-sandbox
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

## 📞 Support

- **GitHub Issues**: https://github.com/FilipDaniel16/MyModels/issues
- **Email**: filipkodaniel2000@gmail.com
- **Discord**: [Join Community]

---

## 📄 License

MIT License - See LICENSE file

---

**Last Updated**: July 14, 2026  
**Version**: 1.0.0  
**Platforms**: Windows, Linux, Android, iOS

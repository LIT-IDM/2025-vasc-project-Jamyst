#  AR Snowman Bauble – Unity AR Project

This project is a festive augmented reality experience built with Unity and AR Foundation.  
When the user scans a custom QR marker, a 3D snowman bauble appears with falling snow particles and a UI button that plays a Christmas jingle.

---

##  Project Overview
- **Platform:** Android (APK)
- **Framework:** Unity + AR Foundation
- **Tracking Method:** AR Tracked Image (QR code marker)
- **Interaction:** UI button to play audio  
- **Goal:** Provide a simple, joyful AR Christmas experience for mobile users.

---

#  Unity Version & Dependencies

### **Unity Version**
- **Unity 2022.3 LTS**

### **Installed Packages**
| Package | Version | Purpose |
|--------|---------|---------|
| **AR Foundation** | 5.x (AR Foundation 5 for Unity 2022+) | Core AR framework |
| **ARCore XR Plugin** | 5.x | Android tracking support |
| **ARKit XR Plugin** | 5.x | iOS tracking support (for testing in Editor) |
| **Input System** | 1.5+ | UI / button interactions |
| **Visual Scripting (Script Machine)** | Built-in | Used to trigger audio playback |

> Note: Script Machine was used instead of C# scripts to keep the project visual and accessible.

---

#  Build Setup (Android)

### **Build Target**
- **Android**
- Architecture: **ARM64**
- Minimum API Level: **Android 9 (API 28)** or higher
- Scripting Backend: **IL2CPP**
- Target API Level: **Highest installed**

### **Required Player Settings**
- **XR Plug-in Management → ARCore Enabled**
- **Graphics API:** Vulkan or OpenGLES3 (default)
- **Install Location:** Automatic
- **Internet Access:** Auto

### **AR Required**
Make sure to enable:
- **Project Settings → XR Plug-in Management → ARCore → Required**

This forces the app to run only on compatible AR devices.

---

# AR Image Tracking Setup

### **Reference Image Library**
- Contains a **custom QR code** generated for the project.
- Physical image size was set based on the printed QR dimensions.

### **Tracking Behaviour**
1. ARTrackedImageManager detects the QR marker.
2. When detected, it spawns the Snowman prefab at the marker position.
3. When tracking is lost, the model remains but may freeze based on AR Foundation behaviour.

### **Marker Notes**
- Smaller QR codes improved tracking consistency.
- Marker should be printed with matte finish to avoid glare.

---

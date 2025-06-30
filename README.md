# 🧠 Synapse

### *A Cross-Device Real-Time Focus Management System*

---

## 📍 Overview

**Synapse** is an intelligent cross-platform focus management tool designed to reduce digital distractions by syncing focus status across your **PC, browser, and phone**. Whether you're writing code, studying, or working remotely, Synapse ensures that when you're in **focus mode**, distractions are **blocked everywhere** automatically.

> 💡 Imagine using VS Code on your PC. Synapse ensures WhatsApp and Instagram are blocked on your phone and Reddit/YouTube are blocked on your browser all in real time.

---

## 🔧 Problem Statement

Today’s work and study sessions are constantly disrupted by multi-device distractions — even when we put our PCs in "focus mode", phones and browsers remain open doors to temptation.

### ❌ Challenge

* PC focus mode doesn't block phone distractions.
* Browser plugins don’t stop mobile app usage.
* Manual app blocking is tedious and often forgotten.

### ✅ Solution: **Synapse**

* Centralized focus state synced across all devices.
* Real-time blocking of blacklisted apps/websites.
* Unified dashboard to configure work and distraction lists.

---

## 🧩 Architecture Diagram

```
+-----------------+       Firebase Realtime DB        +--------------------+
|  💻 Desktop App |  <------------------------------> |  📱 Mobile App       |
|  (Python)       |                                   |  (Flutter Android)  |
+-----------------+                                   +--------------------+
        ↑                                                    ↑
        |                                                    |
        |   +-------------------+              +----------------------+
        |   | 🌐 Chrome Extension|              |  User Phone (Android)|
        |   |  (JavaScript)     |              |  e.g., Instagram     |
        |   +-------------------+              +----------------------+
```

---

## 🚀 Key Components

| Component               | Role                                                                      | Technology                                    |
| ----------------------- | ------------------------------------------------------------------------- | --------------------------------------------- |
| 💻 **Desktop App**      | Monitors active apps (e.g., VSCode, Notion). Sets `isWorking` in Firebase | `Python`, `Tkinter`, `psutil`                 |
| 📱 **Mobile App**       | Shows overlay on blacklisted apps if `isWorking = true`                   | `Flutter`, `Firebase`, `AccessibilityService` |
| 🌐 **Chrome Extension** | Detects and overlays blocking message on distraction sites                | `JavaScript`, `Firebase Web SDK`              |
| ☁️ **Firebase DB**      | Realtime state sharing across devices                                     | `Firebase Realtime DB`                        |

---

## 🔄 How Synapse Works

| Action                                       | Result                                                     |
| -------------------------------------------- | ---------------------------------------------------------- |
| 👨‍💻 Starts using Notion / VS Code on PC    | Sets `isWorking = true` in Firebase                        |
| 📱 Opens Instagram on phone during this time | Phone App shows **fullscreen overlay**, blocks access      |
| 🌐 Opens YouTube/Reddit in browser           | Chrome Extension blocks page with a **distraction prompt** |
| 👋 Closes all work apps on PC                | Sets `isWorking = false`, all blocks lifted                |

---

## ✅ Core Features

* 📡 **Real-time Device Sync** via Firebase
* 🧠 **Smart Focus Mode Detection**
* ❌ **Cross-Platform App & Website Blocking**
* ⚙️ **Editable Whitelist & Blacklist**
* 🔐 **No Backend Server Needed**

---

## 🧪 Technologies Used

| Stack              | Tools                                              |
| ------------------ | -------------------------------------------------- |
| Python Desktop App | `psutil`, `tkinter`, `firebase REST API`           |
| Flutter Mobile App | `Dart`, `firebase_database`, `Overlay Permissions` |
| Chrome Extension   | `Manifest v3`, `DOM Injection`, `Firebase JS SDK`  |
| Sync Layer         | `Firebase Realtime Database`                       |

---

## 📁 Repositories

| Component           | Repo                                                                       |
| ------------------- | -------------------------------------------------------------------------- |
| 📱 Mobile App       | [Synapse-Mobile](https://github.com/Utsavvv1/browser-ext)                  |
| 💻 Desktop App      | [Synapse-Desktop](https://github.com/Utsavvv1/harmonicdisruption)          |
| 🌐 Chrome Extension | [Synapse-Extension](https://github.com/Zyphon12342/HarmonicDistruptionApp) |

---

## 💻 Desktop App Highlights

* Python-based GUI (Tkinter)
* Detects active processes every `5 seconds`
* Prompts reason when blacklisted app is opened
* Sends `focus state` to Firebase

---

## 📱 Mobile App Highlights

* Built in Flutter
* Monitors foreground app via AccessibilityService
* If blacklisted app opened when `isWorking = true`, shows overlay

### Key Permissions:

* 📲 Overlay permission
* 🛡️ Accessibility permission
* 🔗 Firebase config

---

## 🌐 Chrome Extension Highlights

* Injects DOM overlay into distraction sites
* Live blocks sites if Firebase `isWorking = true`
* Lightweight, instant blocking via content script

---

## 🔮 MVP Demo (Suggested Flow)

1. Start using VS Code on PC → Firebase: `isWorking = true`
2. Try to open Instagram on phone → Blocked with fullscreen warning
3. Open Reddit on Chrome → Blocked with popup
4. Close VS Code → All devices unblock

---

## 📊 Future Scope

* 📊 Focus session analytics (time saved, apps blocked)
* 🧘‍♂️ Pomodoro + break reminders
* 💪 Auto screen lock if distraction persists
* 🔒 Auto whitelist/blacklist tuning via ML
* 🍎 iOS support
* 💻 Desktop Flutter App for uniform UI/UX

---

## 👥 Contributors

| Name                  | GitHub                                                         |
| --------------------- | -------------------------------------------------------------- |
| Utsav Verma           | [@Utsavvv1](https://github.com/Utsavvv1)                       |
| Aaryan Singh Rathore  | [@AaryanSingthRathore](https://github.com/AaryanSingthRathore) |
| Anomitra Bhattacharya | [@anomitroid](https://github.com/anomitroid)                   |
| Aditya Negi           | [@Aditya11835](https://github.com/Aditya11835)                 |
| Shivansh Kandpal      | [@Zyphon12342](https://github.com/Zyphon12342)                 |

---

## 🛠️ Installation Summary

### 🔹 Desktop App:

* Install Python + `requirements.txt`
* Set Firebase API Key and URL
* Build .exe using PyInstaller
* Run Synapse.exe

### 🔹 Mobile App:

* Flutter SDK setup
* Firebase Android JSON config
* Grant Accessibility + Overlay permissions

### 🔹 Chrome Extension:

* Load unpacked extension in Chrome
* Set Firebase config in `popup.js`

---

## 📜 License

This project is licensed under the [MIT License](./LICENSE).

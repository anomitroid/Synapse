# 📌 Synapse: Cross-Device Focus Management System

**Synapse** helps you stay focused by preventing distractions across all your devices.  
If you're doing focused work on your **PC**, it blocks distractions like **Instagram, YouTube, WhatsApp, TikTok** on your **phone**.  
Similarly, if you open distracting websites or apps on **PC**, it shows a blocking popup there too.

---

## 🚀 High-Level Architecture

| Component | Purpose | Tech |
| --- | --- | --- |
| 🖥️ **Desktop App** | Detects currently running PC programs (e.g., VS Code, Notion) and sends focus status to Firebase | Python |
| 🌐 **Browser Extension** | Detects open distraction websites (e.g., Reddit, YouTube) on Chrome and shows a screen blocker | JavaScript (Chrome Extension) |
| 📱 **Mobile App** | Shows fullscreen overlays blocking apps like Instagram, WhatsApp when user is in focus mode on PC | Flutter (Android) |
| ☁️ **Sync Layer** | Real-time focus state sync across devices | Firebase Realtime Database |

---

## 📡 How It Works

1. **Focus Detection (PC)**  
   If user is using a "work app" on PC (e.g., VS Code), the **Desktop App** sets `isWorking = true` in Firebase.

2. **Distraction Monitoring (Phone)**  
   If user opens Instagram/YouTube during this time → **Mobile App shows a fullscreen overlay** blocking the screen.

3. **Distraction Monitoring (PC Browser)**  
   If user opens Reddit/YouTube/other distraction websites → **Chrome Extension overlays a blocking popup** on the site.

4. **Real-time Sync**  
   Firebase acts as the communication layer → all devices listen to the same focus status in real time.

---

## 🛠️ Repositories

| Repo | Purpose | Link |
| --- | --- | --- |
| 📱 Mobile App | Flutter app that listens for focus state and blocks apps with overlays | [Synapse-Mobile](https://github.com/Utsavvv1/browser-ext) |
| 🖥️ Desktop App | Python script that detects running work programs and updates Firebase | [Synapse-Desktop](https://github.com/Utsavvv1/harmonicdisruption) |
| 🌐 Chrome Extension | Browser extension that blocks distracting websites | [Synapse-Extension](https://github.com/Zyphon12342/HarmonicDistruptionApp) |

---

## ✅ Features (MVP Scope)

- 🔄 Real-time cross-device syncing
- 🚫 App and website blockers
- 🕒 Work session detection (based on active desktop apps)
- 🌍 Firebase-backed state sync (No backend server needed)

---

## 📝 Setup Overview for Each Repo

### Mobile App:
- Flutter project
- Needs Firebase Android config
- Requires overlay and accessibility permissions on device

### Desktop App:
- Python
- Uses `psutil` for process detection
- Uses Firebase REST API for updates
- Needs a whitelist.json for allowed work apps

### Chrome Extension:
- JavaScript + HTML + Firebase Web SDK
- Needs Firebase Web config keys
- Injects DOM overlays into distraction sites

---

## 📈 Future Scope (Optional Extensions)

- Focus analytics dashboard
- Allow user-defined work/distraction app lists
- Add iOS support
- Pomodoro / time tracking features

---

## 👥 Contributors

- [Utsav Verma](https://github.com/Utsavvv1)
- [Aaryan Singh Rathore](https://github.com/AaryanSingthRathore)
- [Anomitra Bhattacharya](https://github.com/anomitroid)
- [Aditya Negi](https://github.com/Aditya11835)
- [Shivansh Kandpal](https://github.com/Zyphon12342)


---

## 📌 License

[MIT License](LICENSE)

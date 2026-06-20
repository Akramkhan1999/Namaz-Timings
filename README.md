# 🕌 SalahSync

> **Your personal Islamic companion — track prayers, read Qur'an, and sync across devices.**

SalahSync is an Android app built around a powerful single-file WebView architecture. It combines a beautiful HTML/CSS/JS front-end with Firebase for cross-device cloud sync, and wraps it all in a native Android shell.

---

## ✨ Features

| Feature | Description |
|---|---|
| 🙏 **Prayer Tracker** | Mark each of the 5 daily prayers as done with beautiful toggle switches |
| 🕒 **Salah Timetable** | Full monthly prayer times table with today's row highlighted |
| 📖 **Qur'an Reader** | Browse all 114 surahs, read full Arabic text with English translation |
| 🤲 **Duas Collection** | Searchable collection of duas with Arabic text and transliteration |
| 🕌 **How to Pray Namaz** | Step-by-step prayer guide |
| ☁️ **Cloud Sync** | Real-time Firestore sync — data stays identical across all your devices |
| 🔐 **Account System** | Email/Password and Google Sign-In via Firebase Auth |
| 🎨 **22 Premium Themes** | Islamic, Luxury, Nature, and Tech themed color palettes |
| 🌙 **Dark / Light Mode** | Toggle between dark and light modes |
| 📱 **Android Native** | Packaged as a native Android app with back-navigation support |

---

## 🖼️ App Sections

The app uses a tab-based layout with the following main views:

- **Today** — Daily prayer checklist with live toggle switches
- **Qur'an** — Full Qur'an with surah list and verse-by-verse reader
- **Duas** — Searchable duas library
- **Salah Times** — Monthly prayer timetable
- **Dashboard** — Prayer stats and streaks

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Android Shell** | Kotlin, Jetpack Compose, WebView |
| **Front-end** | HTML5, Vanilla CSS, Vanilla JavaScript |
| **Authentication** | Firebase Auth v8 (Email/Password + Google Sign-In) |
| **Database** | Cloud Firestore (real-time listener) |
| **Fonts** | Google Fonts — Lexend, Noto Naskh Arabic, Bangers, Teko |
| **Icons** | Font Awesome 6 |
| **Min SDK** | Android 7.0 (API 24) |
| **Target SDK** | Android 17 (API 37) |
| **Version** | 2.0.0 |

---

## 📁 Project Structure

```
SalahSyncApp/
├── app/
│   ├── src/main/
│   │   ├── assets/
│   │   │   ├── SalahSync.html      # Main app (entire front-end in one file)
│   │   │   └── login.html          # Login / Register / Password Reset page
│   │   ├── java/com/example/salahsync/
│   │   │   ├── MainActivity.kt     # WebView host + AndroidBridge JS interface
│   │   │   ├── data/
│   │   │   │   ├── PrayerDatabase.kt       # Hardcoded prayer times data
│   │   │   │   ├── FirestoreRepository.kt  # Firestore read/write helpers
│   │   │   │   ├── SurahRepository.kt      # Quran surah data
│   │   │   │   ├── TrackingData.kt         # Prayer tracking data model
│   │   │   │   ├── DataRepository.kt       # General data access
│   │   │   │   └── TimeUtils.kt            # Date/time helpers
│   │   │   ├── ui/
│   │   │   │   ├── main/
│   │   │   │   │   ├── MainScreen.kt       # Compose main screen
│   │   │   │   │   └── MainScreenViewModel.kt
│   │   │   │   └── tabs/
│   │   │   │       ├── DashboardTab.kt     # Prayer stats dashboard
│   │   │   │       ├── DataTab.kt          # Salah timetable table
│   │   │   │       ├── LiveTab.kt          # Today's prayer checklist
│   │   │   │       ├── SurahTab.kt         # Quran surah browser
│   │   │   │       └── ViewModels...
│   │   │   └── theme/                      # Compose theme definitions
│   │   ├── res/                            # Android resources (icons, strings)
│   │   └── AndroidManifest.xml
│   ├── google-services.json               # Firebase project config
│   └── build.gradle.kts
├── build.gradle.kts
├── settings.gradle.kts
└── gradle.properties
```

---

## 🔥 Firebase Setup

The app uses Firebase for authentication and cloud sync.

**Firebase services used:**
- **Firebase Authentication** — Email/Password + Google Sign-In
- **Cloud Firestore** — Real-time prayer tracking data sync

**Firestore data structure:**
```
elite_users/
  └── {userId}/
        └── trackingData: { "2024-01-15": { fajr: true, dhuhr: false, ... }, ... }
```

> ⚠️ If you fork this project, replace `google-services.json` and the `firebaseConfig` object inside both `SalahSync.html` and `login.html` with your own Firebase project credentials.

---

## 🚀 Getting Started

### Prerequisites

- Android Studio Meerkat (2024.3.1) or newer
- JDK 17
- Android SDK API 24+
- A Firebase project with Authentication and Firestore enabled

### Build & Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/SalahSync.git
   cd SalahSync/SalahSyncApp
   ```

2. **Open in Android Studio**
   - File → Open → select the `SalahSyncApp` folder

3. **Sync Gradle**
   - Android Studio will automatically sync. If not, click **Sync Now**.

4. **Run the app**
   - Connect a device or start an emulator
   - Click ▶️ Run or press `Shift + F10`

### Building a Release APK

```bash
./gradlew assembleRelease
```

The APK will be output to `app/build/outputs/apk/release/`.

---

## 🔐 Authentication Flow

```
App Launch
    │
    ▼
SalahSync.html  (main app)
    │
    ├─ User not signed in → taps "Sign In / Sign Up"
    │       │
    │       ├─ Android:  AndroidBridge.openLogin() → loads login.html in WebView
    │       └─ Desktop:  window.location.href = 'login.html'
    │
    ▼
login.html
    ├─ Email/Password Sign In
    ├─ Email/Password Register
    ├─ Google Sign-In (popup on desktop)
    └─ Forgot Password (Firebase reset email)
    │
    ▼
On success → AndroidBridge.onLoginSuccess() / window.location.replace('SalahSync.html')
    │
    ▼
Back to SalahSync.html  (signed in, cloud sync active)
```

---

## 📱 Android Bridge

The `AndroidBridge` Kotlin class is registered as a JavaScript interface in the WebView, letting the HTML pages call native Android functions:

| JS Call | What it does |
|---|---|
| `AndroidBridge.openLogin()` | Loads `login.html` in the WebView |
| `AndroidBridge.onLoginSuccess()` | Returns to `SalahSync.html` after sign-in |
| `AndroidBridge.openGoogleSignIn()` | *(Reserved)* Triggers native Google Sign-In |

---

## 🎨 Themes

SalahSync includes **22 hand-curated themes** across 4 categories:

| Category | Themes |
|---|---|
| ☪️ Islamic & Spiritual | Sacred Gold, Madinah Green, Al-Aqsa Blue, Pre-Dawn Purple, Iftar Amber, Jannah Emerald |
| 💎 Luxury & Premium | Royal Gold, Diamond Ice, Platinum, Rose Gold, Deep Velvet, Obsidian Violet |
| 🌿 Nature & Elements | Midnight Blue, Aurora Borealis, Sahara Dunes, Deep Ocean, Volcanic Fire, Nebula Pink |
| ⚡ Modern & Tech | Matrix Green, Neon Cyber, Steel & Amber, Monochrome |

---

## 👤 Developer

**Type01warrior**

- 📸 Instagram: [@type01warrior](https://www.instagram.com/type01warrior/)
- 💬 WhatsApp: [+91 96036 11435](https://wa.me/919603611435)

---

## 📄 License

This project is for personal and educational use. All rights reserved © Type01warrior.

---

*May Allah accept our prayers. 🤲*

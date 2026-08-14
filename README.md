# 🕌 SalahSync Pro

<div align="center">

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Firebase](https://img.shields.io/badge/Firebase-Cloud%20Sync-orange?logo=firebase)](https://firebase.google.com)
[![PWA](https://img.shields.io/badge/PWA-Ready-5A0FC8?logo=pwa)](https://web.dev/progressive-web-apps/)
[![Made with Love](https://img.shields.io/badge/Made%20with-❤️-ff69b4.svg)](https://type01warrior.github.io/SalahSync/)

**Your all-in-one Islamic companion for prayer tracking, Qur'an reading, and spiritual growth.**

[🌐 Live Demo](https://your-demo-link.com) • [📱 Install PWA](https://your-demo-link.com) • [🐛 Report Bug](https://github.com/yourusername/salahsync/issues) • [✨ Request Feature](https://github.com/yourusername/salahsync/issues)

</div>

---

## 📸 Preview

<div align="center">
  <img src="assets/screenshot-today.png" alt="Today Tab" width="250"/>
  <img src="assets/screenshot-quran.png" alt="Quran Reader" width="250"/>
  <img src="assets/screenshot-dashboard.png" alt="Dashboard" width="250"/>
</div>

---

## ✨ Features

### 🕐 Prayer Times & Tracking
- **Accurate Prayer Timings** — Daily Salah schedules with automatic countdown timers
- **Ramadan Mode** — Special Sehri & Iftar timings during Ramadan with automatic detection
- **Prayer Checklist** — Toggle prayers (Fajr, Zohr/Jum'ah, Asr, Maghrib, Isha, Tahajjud) as complete
- **Precision Timer** — Secondary countdown showing current prayer window status
- **Auto Day/Night Theme** — Automatically switches between light and dark modes based on prayer times

### 📊 Performance Dashboard
- **Monthly Record Table** — Visual prayer history with clickable icons for each day
- **Score Calculator** — Daily, weekly, monthly, and yearly performance percentages
- **Pie Chart Visualizations** — Beautiful conic-gradient charts for tracking consistency
- **Cloud Sync** — Real-time Firebase Firestore sync across all your devices
- **PDF Export** — Export your prayer records for personal archiving

### 📖 Qur'an Reader
- **Complete Qur'an** — All 114 Surahs and 30 Juz with Arabic, Transliteration, English & Urdu translations
- **Audio Recitation** — Inline verse-by-verse audio playback by Sheikh Mishary Alafasy
- **Playback Modes** — Single verse, Full Surah, or Full Juz sequential playback
- **Speed Control** — Adjustable playback speed (0.5× to 2×)
- **Bookmarks** — Bookmark Surahs and specific Ayahs for quick access
- **Reading Progress** — Auto-saves your position and offers "Continue Reading"
- **Font Customization** — Adjustable Arabic script size, Naskh/Uthmani font styles
- **Text Visibility** — Toggle Transliteration, English Translation, and Urdu Meaning independently

### 🤲 Duas & Supplications
- **80+ Authentic Duas** — Categorized collection from Quran and Sunnah
- **Categories Include:**
  - 🕌 Daily Essentials (Sleep, Waking, Eating, Wudu, etc.)
  - 🤲 Morning & Evening Adhkar
  - 🙏 Salah & Worship (Qunoot, Tashahhud, etc.)
  - ❤️ Personal Supplications
  - ✈️ Travel & Movement
  - 🌙 Night & Tahajjud
  - 🤝 Social & Relationships
  - ☪️ Dhikr & Glorification
- **Search & Favorites** — Quickly find duas and save favorites
- **Copy & Share** — One-tap copy to clipboard or share

### 🧎 Namaz Guide
- **Step-by-Step Prayer Guide** — Detailed instructions for all prayer types
- **Visual References** — Prayer posture images with Arabic recitations
- **Rak'at Information** — Clearly marked rak'at counts for each prayer

### 📿 Digital Tasbih
- **Interactive Counter** — Tap-to-count with animated ring progress indicator
- **Presets** — SubhanAllah (33×), Alhamdulillah (33×), Allahu Akbar (34×), La ilaha illallah (100×)
- **Custom Dhikr** — Add your own dhikr with custom target counts

### 🧭 Qibla Compass
- **Real-time Compass** — Device orientation-based Qibla direction
- **Calibration Status** — Visual feedback on sensor accuracy
- **Distance to Kaaba** — Shows your distance from Masjid al-Haram
- **Location Info** — Current coordinates and city detection

### 📅 Hijri Calendar
- **Full Hijri Calendar** — Monthly grid view with Gregorian date mapping
- **Event Tracking** — Highlights Islamic events (Ramadan, Eid, White Days, etc.)
- **Yearly Events** — List of important Hijri dates
- **Monthly Fasting** — Sunnah fasting days tracker
- **Jump to Date** — Navigate to any Hijri month/year

### 🎨 Customization
- **24 Premium Themes** — Including:
  - ☪️ Islamic & Spiritual (Kaaba Gold, Madinah Green, Al-Aqsa Blue, etc.)
  - 💎 Luxury & Premium (Royal Gold, Diamond Ice, Platinum, etc.)
  - 🌌 Nature & Elements (Midnight Blue, Aurora, Sahara, etc.)
  - ⚡ Modern & Tech (Matrix, Neon Cyber, Monochrome, etc.)
- **Light & Dark Modes** — Manual toggle or auto-switch based on prayer times
- **Tab Management** — Show/hide tabs according to your preference
- **Screen Wake Lock** — Keep screen awake during prayer or Qur'an reading

### ☁️ Cloud Sync & Auth
- **Firebase Authentication** — Google Sign-In support
- **Real-time Sync** — Instant data sync across devices via Firestore
- **Offline First** — All data cached locally; syncs when online
- **Privacy Focused** — Your prayer data belongs to you

---

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| **HTML5** | Semantic markup & PWA structure |
| **CSS3** | Custom properties, animations, responsive design |
| **Vanilla JavaScript** | Zero-dependency core logic |
| **Firebase** | Authentication, Firestore database, cloud sync |
| **Al-Quran Cloud API** | Qur'an text, translations & transliterations |
| **Islamic Network CDN** | High-quality Qur'an audio recitations |
| **Fawaz Ahmed Quran API** | Urdu translations |
| **Web APIs** | Wake Lock, Clipboard, Vibration, Device Orientation |

---

## 🚀 Getting Started

### Prerequisites
- A modern web browser (Chrome, Firefox, Safari, Edge)
- For PWA install: Chrome/Edge on Android, Safari on iOS
- For Qibla compass: Device with magnetometer & accelerometer

### Installation

#### Option 1: Use as PWA (Recommended)
1. Open the app in your mobile browser
2. Tap **"Add to Home Screen"** or **"Install App"**
3. Enjoy the full-screen native app experience!

#### Option 2: Self-Host
```bash
# Clone the repository
git clone https://type01warrior.github.io/SalahSync/.git

# Navigate to project directory
cd salahsync

# Serve locally (example using Python)
python -m http.server 8000

# Or using Node.js
npx serve .
```

#### Option 3: Deploy to Firebase
```bash
# Install Firebase CLI
npm install -g firebase-tools

# Login and initialize
firebase login
firebase init hosting

# Deploy
firebase deploy
```

### Firebase Configuration
Create a `.env` file or update the Firebase config in `index.html`:

```javascript
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_AUTH_DOMAIN",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_STORAGE_BUCKET",
  messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
  appId: "YOUR_APP_ID"
};
```

---

## 📱 Usage Guide

### Prayer Tracking
1. Open the **Today** tab to see current prayer times
2. Toggle the switches as you complete each prayer
3. View your progress in the **Dashboard** tab
4. Check the **Salah Times** tab for the full monthly timetable

### Reading Qur'an
1. Go to the **Qur'an** tab
2. Browse Surahs or Juz
3. Tap any Surah to open the reader
4. Use the floating buttons to adjust font size
5. Tap the ▶ button on any verse to listen to recitation
6. Use the playback mode bar to switch between single verse / full Surah / full Juz

### Using the Tasbih
1. Open the **Tasbih** tab
2. Select a preset or add custom dhikr
3. Tap the center or the button to count
4. Watch the progress ring fill up!

### Finding Qibla
1. Go to the **Qibla** tab
2. Tap **Enable Compass**
3. Hold your device flat and rotate until the needle aligns
4. The pointer shows the exact Qibla direction

---

## 🗂️ Project Structure

```
salahsync/
├── index.html          # Main application file
├── manifest.json       # PWA manifest
├── login.html          # Authentication page
├── 55340.png           # App icon
├── assets/
│   └── screenshots/    # App screenshots for README
└── README.md           # This file
```

> **Note:** This is a single-page application (SPA) with all logic contained in `index.html` for simplicity and offline reliability.

---

## 🌟 Roadmap

- [ ] Multi-language support (Urdu, Arabic, French, Indonesian)
- [ ] Prayer time calculation using GPS coordinates
- [ ] Azan notifications with custom sounds
- [ ] Community challenges & leaderboards
- [ ] Zakat calculator
- [ ] Islamic date converter widget
- [ ] Hadith of the day
- [ ] Prayer time widgets for iOS/Android home screens

---

## 🤝 Contributing

Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Contributors
<a href="https://type01warrior.github.io/SalahSync/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=type01warrior/salahsync" />
</a>

---

## 📜 License

Distributed under the MIT License. See `LICENSE` for more information.

---

## 🙏 Acknowledgments

- **Al-Quran Cloud API** — For providing comprehensive Qur'an data
- **Islamic Network** — For high-quality audio recitations
- **Fawaz Ahmed** — For the open-source Quran API
- **Firebase** — For backend infrastructure
- **Allah SWT** — For the guidance to build this

---

<div align="center">

**Made with ❤️ by [Type01warrior](https://instagram.com/type01warrior)**

[📧 Contact](mailto:your-email@example.com) • [💬 WhatsApp](https://wa.me/919603611435) • [📷 Instagram](https://instagram.com/type01warrior)

*"Indeed, prayer has been decreed upon the believers a decree of specified times."* — Quran 4:103

</div>

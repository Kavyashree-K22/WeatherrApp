# 🌦️ MyWeatherApp

> A modern, elegant, cross-platform weather application built with HTML, CSS, JavaScript, Electron (Windows), and Capacitor (Android), powered by the free Open-Meteo API.

---

## ✨ Features

- 🔍 **City Search with Live Autocomplete**: Search any city worldwide with real-time suggestions powered by the Open-Meteo Geocoding API.
- 🌡️ **Current Temperature & Unit Toggle**: View accurate temperatures in Celsius (°C) with an instant toggle to Fahrenheit (°F).
- ⛅ **Dynamic Weather Conditions**: Accurate condition mappings (Clear/Sunny, Partly Cloudy, Overcast, Drizzle, Rain, Snow, Thunderstorm, Fog) with animated vector icons.
- 💧 **Detailed Weather Metrics**:
  - **Humidity**: Relative humidity with visual progress gauge and comfort level status.
  - **Wind Speed & Direction**: Real-time speed (km/h or mph) with a rotating compass direction indicator and cardinal heading.
  - **Surface Pressure**: Barometric atmospheric pressure in hPa.
  - **Sun Cycle**: Precise local sunrise and sunset timings.
- 📅 **5-Day Weather Forecast**: Upcoming day forecasts with weather icons, condition descriptions, precipitation probability, and visual temperature range bars.
- ⏱️ **24-Hour Hourly Forecast**: Interactive scrollable strip showing next 24 hours of conditions and temperatures.
- 📍 **Automatic Location Detection**: Automatically detects your current location with user permission (GPS / IP Geolocation fallback).
- 🔄 **Refresh Button**: Instantly refresh current weather data with an animated spinner.
- ⚠️ **Graceful Error Handling**: User-friendly toast notifications for invalid city names or network issues.
- 📱 **Cross-Platform & Responsive**: Designed to look stunning on Windows Desktop (Electron), Android Mobile (Capacitor), and Modern Web Browsers.
- 🎨 **Glassmorphism & Dynamic Themes**: Atmospheric ambient glowing backdrops that dynamically adapt to the current weather condition and day/night cycle.

---

## 📁 Project Structure

```text
MyWeatherApp/
├── src/                          # Core Web Application
│   ├── index.html                # Semantic HTML5 Structure
│   ├── style.css                 # Glassmorphic Design System & Responsive CSS
│   └── script.js                 # App Logic, Open-Meteo API & Geolocation
├── assets/
│   └── icons/
│       ├── icon.png              # High-Resolution Application Icon (512x512)
│       └── favicon.svg           # Vector Favicon
├── electron/
│   └── main.js                   # Electron Windows Desktop Entry & Native Menu
├── android/                      # Native Android Studio Project (Capacitor)
├── dev-server.js                 # Zero-dependency local development server
├── package.json                  # Scripts and Dependencies
├── capacitor.config.json         # Capacitor Mobile Configuration
├── .gitignore                    # Git Ignore for Node, Android, and Electron
└── README.md                     # Documentation & Build Guide
```

---

## 🚀 Getting Started

### Prerequisites

1. **Node.js** (v18.0.0 or higher recommended) - [Download Node.js](https://nodejs.org/)
2. **Git** - [Download Git](https://git-scm.com/)
3. *(For Android APK build)* **Android Studio** and **Java JDK 17+** - [Download Android Studio](https://developer.android.com/studio)

### Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/your-username/MyWeatherApp.git
cd MyWeatherApp
npm install
```

---

## 🖥️ Platform 1: Browser Version (Testing & Web)

Run the included lightweight local development server:

```bash
npm run dev
```

Open your browser and navigate to:
```
http://localhost:3000
```

---

## 🪟 Platform 2: Windows Desktop Application (Electron)

### 1. Run in Desktop Window (Development Mode)

To launch MyWeatherApp directly in an Electron desktop window:

```bash
npm run start
```
*or*
```bash
npm run dev:electron
```

### 2. Build Windows Executable (.exe)

To generate a standalone portable `.exe` and NSIS Windows Installer:

```bash
npm run build:electron
```

Or to build a single portable executable:

```bash
npm run build:electron:portable
```

The generated `.exe` files will be output to the `release/` directory:
- `release/MyWeatherApp 1.0.0.exe` (Standalone Portable Executable)
- `release/MyWeatherApp Setup 1.0.0.exe` (Windows Installer)

---

## 📱 Platform 3: Android Mobile Application (Capacitor)

Capacitor bridges the web application into a native Android Studio project.

### 1. Initialize Android Project (Run Once)

```bash
npm run cap:add:android
```

This creates the native `android/` directory configured with Gradle and AndroidManifest.

### 2. Sync Web Assets to Android

Whenever you update files in `src/`, sync them to the native Android build:

```bash
npm run cap:sync
```

### 3. Open in Android Studio & Build APK

Launch the native Android project in Android Studio:

```bash
npm run cap:open
```

#### Steps in Android Studio to Generate `.apk`:
1. Wait for Android Studio to complete Gradle sync.
2. In the top menu, click **Build** > **Build Bundle(s) / APK(s)** > **Build APK(s)**.
3. Once completed, a notification will appear: `APK(s) generated successfully for 1 module`.
4. Click **locate** to find your installable APK file:
   ```text
   android/app/build/outputs/apk/debug/app-debug.apk
   ```
5. Transfer `app-debug.apk` to your Android phone or run it directly on an emulator / connected physical device.

#### Alternative: Build APK via Command Line (Requires Android SDK & Gradle)
```bash
cd android
./gradlew assembleDebug
```
The APK will be located at `android/app/build/outputs/apk/debug/app-debug.apk`.

---

## 🌐 API Attribution & Credits

- Weather data and Geocoding are provided free of charge by **[Open-Meteo](https://open-meteo.com/)**.
  - No API key or secret token is required.
  - Free for non-commercial and open-source use under CC-BY 4.0.
- Reverse geocoding provided by **[BigDataCloud](https://www.bigdatacloud.net/)**.
- Fonts: **Outfit** and **Plus Jakarta Sans** via Google Fonts.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

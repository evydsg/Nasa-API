# 🚀 NASA Picture of the Day — Android App

> An Android app that brings the universe to your fingertips. Browse NASA's Astronomy Picture of the Day (APOD), read expert explanations, and explore the cosmos — one day at a time.

---

## 📱 Demo

[![Watch the demo](https://drive.google.com/thumbnail?id=1Z5sSGxlpa188UtACN35kgaDUd7S5sZYO)](https://drive.google.com/file/d/1Z5sSGxlpa188UtACN35kgaDUd7S5sZYO/view?usp=sharing)

▶️ **[Click to watch the full walkthrough](https://drive.google.com/file/d/1Z5sSGxlpa188UtACN35kgaDUd7S5sZYO/view?usp=sharing)**

---

## 🌌 About the Project

This Android app consumes **NASA's public APOD (Astronomy Picture of the Day) API** to surface a new piece of the cosmos every day. Users can fetch the latest image or video, read the scientific caption, and browse by date — all from a clean, two-screen experience built natively in Android.

This project was built as part of the AND101  curriculum, focusing on async networking, REST API integration, and multi-screen navigation in Android.

---

## ✨ Features

- 🌠 **Daily Astronomy Image** — Fetches and displays the current APOD including title, date, and full explanation
- 🔄 **Refresh on Demand** — A button triggers a new API call and live-updates all displayed data
- 📅 **Date Query Support** — Users can query a specific date to explore past astronomy pictures
- 🖼️ **Multi-Screen Navigation** — A dedicated detail screen provides an expanded view of the selected image and its description
- ⚡ **Async Networking** — Built with `AsyncHTTPClient` for non-blocking API calls on the main thread

---

## 🛠️ Tech Stack

| Category | Technology |
|---|---|
| Language | Kotlin  |
| Platform | Android (Android Studio) |
| Networking | AsyncHTTPClient |
| Data Format | JSON (NASA REST API) |
| UI | XML Layouts, RecyclerView |
| Image Loading | Glide |
| API | [NASA APOD API](https://api.nasa.gov/) |

---

## 📸 API Overview

This app uses NASA's **Astronomy Picture of the Day (APOD)** endpoint:

```
GET https://api.nasa.gov/planetary/apod?api_key=YOUR_KEY&date=YYYY-MM-DD
```

**Sample response fields displayed in-app:**
- `title` — Name of the astronomy object or event
- `date` — Publication date
- `explanation` — Scientific description authored by NASA astronomers
- `url` — Link to the image or video
- `media_type` — Distinguishes images from video entries

---

## 🚀 Getting Started

### Prerequisites
- Android Studio (Flamingo or later recommended)
- A free NASA API key — [get one here](https://api.nasa.gov/)
- Android device or emulator running API 24+

### Setup

```bash
# 1. Clone the repository
git clone https://github.com/evydsg/Nasa-API.git

# 2. Open in Android Studio
File → Open → select the cloned folder

# 3. Add your API key
# In the project, locate the constants/config file and replace:
const val NASA_API_KEY = "YOUR_API_KEY_HERE"

# 4. Run the app
# Press the green Run ▶ button or use Shift + F10
```

> ⚠️ The demo key (`DEMO_KEY`) works out of the box but has lower rate limits (30 req/hour). Registering a free key gives you 1,000 req/hour.

---

## 🧩 Project Structure

```
app/
├── activities/
│   ├── MainActivity.kt         # Home screen — displays APOD data
│   └── DetailActivity.kt       # Secondary screen — expanded image/description
├── network/
│   └── NasaApiClient.kt        # AsyncHTTPClient setup and API calls
├── models/
│   └── ApodModel.kt            # Data model for API response
└── res/
    ├── layout/                 # XML UI layouts
    └── values/                 # Strings, colors, themes
```

---

## 🔧 Challenges & How I Solved Them

**Async threading on Android**
Handling network calls without blocking the UI thread required understanding Android's threading model. Using `AsyncHTTPClient` kept the main thread free and prevented ANR errors.

**Parsing nested JSON responses**
NASA's API returns a mix of image and video media types. I added a conditional check on the `media_type` field to handle both gracefully, falling back to a placeholder for video entries.

**Passing data between activities**
Navigating from the list screen to the detail screen required serializing the APOD model and passing it via `Intent` extras — a good real-world exercise in Android's inter-activity communication patterns.

---

## 📄 License

```
Copyright 2023 Evelise Guenda

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

---

<p align="center">
  Built with ❤️ and a lot of curiosity about the universe &nbsp;·&nbsp;
  <a href="https://www.linkedin.com/in/evelise-guenda">LinkedIn</a> &nbsp;·&nbsp;
  <a href="https://github.com/evydsg">GitHub</a>
</p>IONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

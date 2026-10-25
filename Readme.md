# NutriScan AI - Food Logging & Verification Agent

NutriScan AI is a lightweight, single-page web application designed for intelligent food logging and macro tracking. It leverages Google Gemini AI Vision, Open Food Facts API, and natural language text processing to identify food items, calculate nutritional metrics, and present them through a human-in-the-loop verification workflow before logging to a structured local database.

---

## 🚀 Key Features

* **Multi-Modal Input Support:**
  * **AI Vision Lens:** Snap a live photo, capture via native device camera, or upload an image file to analyze dishes using Google Gemini 3 Flash.
  * **Barcode Scanner:** Real-time barcode scanning via live camera feed, photo upload barcode recognition, or manual barcode lookup backed by the Open Food Facts API.
  * **Natural Language Text:** Input free-form descriptions (e.g., *"1 bowl of grilled chicken salad with olive oil"*) for automatic macro breakdown extraction.
* **Human-in-the-Loop Verification Loop:**
  * Every AI detection or API lookup presents a verification step allowing users to inspect, adjust, or override calculated calories and macronutrients (Protein, Carbs, Fats) before committing entries to the log.
* **Nutritional Analytics & Database:**
  * Real-time aggregate tracking for total daily calories and macro splits (Protein, Carbs, Fats).
  * In-memory relational log database allowing quick entry deletions and complete session clears.
* **Secure Context & Hardware Fallbacks:**
  * Built-in HTTP vs. HTTPS security context detection with intelligent error handling, offering native camera upload fallbacks when streaming APIs are restricted.

---

## 🛠️ Tech Stack & Dependencies

* **Frontend Framework:** Plain HTML5, Modern Vanilla JavaScript (ES6+)
* **Styling:** [Tailwind CSS](https://tailwindcss.com/) (via CDN)
* **Icons:** [Lucide Icons](https://lucide.dev/) (via CDN)
* **Barcode Detection:** [html5-qrcode](https://github.com/mebjas/html5-qrcode) Library
* **AI & Data APIs:**
  * Google Gemini 3 Flash Vision API (`gemini-3-flash-preview`)
  * Open Food Facts REST API v2

---

## 🚦 Getting Started

### Prerequisites

No complex build pipeline or package manager (npm/yarn) is required. The application runs directly in any modern web browser.

### API Key Setup

To use the AI Vision and Text Processing features powered by Google Gemini:
1. Obtain an API Key from [Google AI Studio](https://aistudio.google.com/).
2. Pass or define your key in the global browser environment prior to invoking AI queries:
   ```javascript
   window.apiKey = "YOUR_GEMINI_API_KEY";
   ```

### Running Locally

1. Download or save `nutriscan_ai_food_logging_verification_agent (1).html`.
2. Open the file directly in any modern web browser (Chrome, Safari, Firefox, Edge).
3. **Note on Camera Permissions:** 
   * Live streaming video features (WebRTC `getUserMedia`) require an **HTTPS** connection or `localhost`/`127.0.0.1`.
   * If running over standard `http://`, use the **Take Photo (Native)** button to trigger device camera capture without security warnings.

---

## 📁 Application Architecture

```text
├── Index (HTML Entry)
│   ├── Warning Banners & Header (Stats Tracker)
│   ├── Input Panel (Photo / Barcode / Text Tabs)
│   ├── Verification Loop Modal (Human Confirmation)
│   └── Analytics & Database Table
└── Script Logic
    ├── Security & HTTPS Detector
    ├── Gemini Vision API Handler
    ├── Open Food Facts Fetch Engine
    ├── HTML5 QR/Barcode Scanner
    └── Dynamic Data Store & State Management
```

---

## 📜 License

This project is open-source and available under the standard MIT License.

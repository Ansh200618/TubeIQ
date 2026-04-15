# TubeIQ

**TubeIQ** is a modern YouTube channel intelligence dashboard that analyzes public channel performance and generates actionable growth insights with AI-assisted recommendations.

---

## ✨ Features

- **Channel analysis** by Channel ID, `@handle`, or username
- **KPI dashboard** for subscribers, views, engagement, and upload consistency
- **Niche classification** and confidence scoring
- **Content mix + radar charts** powered by Chart.js
- **Monthly engagement trends** with CSV export for Power BI
- **Pattern insights** from recent video performance
- **Owner mode (Google Sign-In)** for personalized channel workflows
- **AI recommendations + advisor chat** powered by Gemini models
- **Channel health audit** and side-by-side channel comparison

---

## 🧱 Tech Stack

- HTML5 + CSS3 + Vanilla JavaScript (single-page app)
- [Chart.js](https://www.chartjs.org/) for visualization
- YouTube Data API v3
- Google Identity Services (OAuth)
- Gemini API for AI features

---

## 🚀 Quick Start

Since this project is a static single-file app, no build step is required.

1. Clone the repository.
2. Open `index.html` in your browser  
   **or** run a local static server (recommended), for example:
   ```bash
   python3 -m http.server 8080
   ```
3. Visit `http://localhost:8080`.

---

## ⚙️ Configuration

API credentials are configured directly in `index.html` under the **CONFIG** section:

- YouTube Data API key
- Google OAuth Client ID
- Gemini API key (split parts)

For production use, rotate keys and move secrets to a secure backend/proxy instead of exposing them client-side.

---

## 📌 Current Project Structure

```text
TubeIQ/
└── index.html   # UI, styles, analytics logic, auth flow, and AI integration
```

---

## 🛣️ Suggested Next Improvements

- Move API calls and secrets to a backend service
- Split `index.html` into modular files (`/css`, `/js`)
- Add CI checks (linting + basic tests)
- Add deployment workflow (GitHub Pages / Vercel / Netlify)

---

## 📄 License

No license file is currently defined in this repository. Add a `LICENSE` file (MIT/Apache-2.0 recommended) before public distribution.


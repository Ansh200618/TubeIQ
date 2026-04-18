# TubeIQ

TubeIQ is a single-page web app for YouTube channel intelligence.  
It helps you analyze channels, visualize performance signals, and surface actionable insights from channel data.

## Features

- Channel-focused analytics dashboard
- Visual charts and trend indicators
- Fast, single-file frontend architecture
- Google Sign-In and YouTube/Gemini API integration

## Tech Stack

- HTML
- CSS
- Vanilla JavaScript
- Chart.js

## Project Structure

```text
TubeIQ/
└── index.html
```

## Getting Started

1. Clone the repository.
2. Configure required API credentials in the `CONFIG` section of `index.html`.
3. Serve the app from `http://localhost` or an `https://` domain (do not open with `file://`).

## Google Login + YouTube API Setup (new OAuth)

1. In **Google Cloud Console**, create/select a project.
2. Enable APIs:
   - **YouTube Data API v3**
   - **Google People API** (optional, for profile details)
3. Configure **OAuth consent screen**:
   - Choose External/Internal
   - Add app name + support email
   - Add test users while app is in testing
   - Add scope: `https://www.googleapis.com/auth/youtube.readonly`
4. Create **OAuth Client ID**:
   - APIs & Services → Credentials → Create Credentials → OAuth client ID
   - Type: **Web application**
   - Add Authorized JavaScript origins:
     - `http://localhost:<port>` (replace `<port>` with your real local port, e.g. `3000`, `5500`, `8080`)
     - your deployed domain (exact origin)
   - Add redirect URIs only if your flow requires it
5. Copy your new client ID and replace:
   - In `index.html` → `CONFIG` section, set:
     - `const G_CLIENT = 'YOUR_CLIENT_ID.apps.googleusercontent.com';`
     - `const API_KEY = 'YOUR_YOUTUBE_DATA_API_KEY';`
     - Gemini key variables (`_gk1`, `_gk2`) or equivalent `getGemKey()` source
6. Verify API key restrictions:
   - Restrict key to **YouTube Data API v3**
   - Add HTTP referrer restrictions for your app domain(s)

## Login Troubleshooting

- `origin_mismatch`: authorized JavaScript origin does not match app origin exactly.
- `access_blocked`: OAuth consent/test users not configured correctly.
- `invalid_client`: wrong OAuth client ID in `G_CLIENT`.
- `403` from YouTube API: API disabled or API key restrictions are incorrect.
- Login blocked on `file://`: run via localhost/HTTPS.

## Security Note

Do not commit real production credentials.  
Use environment-specific secrets management for deployment-ready setups.

## Contributing

Contributions are welcome.  
Please keep changes focused, test manually in-browser, and keep UI/UX consistent with the existing style.

## License

Add your preferred license in this repository (for example, MIT) if you plan to distribute this project publicly.

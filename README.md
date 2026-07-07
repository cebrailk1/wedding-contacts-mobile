<div align="center">

# Wedding Contacts

**A fast, mobile-first web app that gives wedding guests one shareable place for contacts, venue, parking and the day-of schedule.**

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![PWA](https://img.shields.io/badge/PWA-5A0FC8?style=flat&logo=pwa&logoColor=white)](https://web.dev/progressive-web-apps/)
[![No build](https://img.shields.io/badge/build-none-success?style=flat)](#)
[![Vercel](https://img.shields.io/badge/deploy-Vercel-000000?style=flat&logo=vercel&logoColor=white)](https://wedding-contacts-mobile.vercel.app/)

[**Live demo →**](https://wedding-contacts-mobile.vercel.app/)

<br />

<img src="docs/preview.webp" alt="iPhone showing the wedding contacts app: venue card and contact list" width="320" />

</div>

---

## Why this exists

Wedding guests need three things on the day, and they need them fast:

1. Who do I call about what?
2. Where is the venue and where do I park?
3. What is happening when?

Most wedding sites bury this behind a landing page, a hero animation, a menu, a scroll, and a framework bundle. This app skips all of that. Open the link, everything is on screen. Tap once, you are calling the right person or looking at the venue in Maps.

## Features

- **Contact list** with one-tap call, WhatsApp, and email actions
- **Tap-to-copy** phone numbers with a `navigator.clipboard` + `execCommand` fallback
- **Venue card** with hotel contact, event team, and both Google Maps and Apple Maps links
- **Parking section** with dedicated Maps links to the recommended lot
- **Schedule page** on a separate route with a timeline of the day
- **WhatsApp share** button for the schedule so guests can forward it easily
- **PWA installable** with a Web App Manifest and Service Worker
- **Offline-resilient** via app-shell precache and cache-first static asset handling

## Performance

The app looks simple on purpose. The simplicity *is* the performance strategy.

| Choice | Effect |
|---|---|
| No framework runtime | Zero JS parse cost from libraries |
| No external dependencies | No third-party requests, no CDN roundtrips |
| Inline critical CSS | First paint without a blocking stylesheet |
| One tiny inline `<script>` | Only the interactions that need JS ship JS |
| App-shell precache | Second visit renders from cache instantly |
| Cache-first for static assets | Icons, CSS, JS come from disk on repeat views |
| Network-first for HTML | Fresh content when online, cached fallback when not |

Result: the page feels instant on mobile, and it stays usable on the flaky Wi-Fi you always get at a busy event venue.

## Tech stack

- HTML, CSS, Vanilla JavaScript
- Service Worker with the Cache API
- Web App Manifest
- Deployed as static files on Vercel

No framework. No bundler. No build step. `git push` is the pipeline.

## Project structure

```
.
├── index.html            # Contact list, venue and parking
├── ablauf.html           # Day-of schedule page
├── sw.js                 # Service Worker (app-shell + strategies)
├── manifest.webmanifest  # PWA manifest
├── icon.svg              # App icon
└── docs/
    └── preview.webp      # README screenshot
```

## Local development

```bash
# Any static server will do. Examples:
python3 -m http.server 8080
# or
npx serve .
```

Open `http://localhost:8080`. The Service Worker only registers over HTTPS or `localhost`.

## Deployment

Push to `main`. Vercel builds nothing and deploys the raw files.

## Privacy

All personal contact names, phone numbers, WhatsApp links, and email addresses in this public version are mock data. The venue and parking information are kept real so the Google Maps and Apple Maps integration works as a live demo.

## License

MIT. Use it as a template for your own event, wedding, workshop, or meetup.

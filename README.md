# Wedding Contacts

![iPhone showing the wedding contacts app: venue card and contact list](docs/preview.webp)

Mobile-first static wedding contact and schedule app built with plain HTML, CSS, and JavaScript.

Live demo: https://wedding-contacts-mobile.vercel.app/

## What It Does

The project gives wedding guests one fast, shareable place for everything they need on the day itself: venue, parking details, key contacts, quick actions, and the timeline.

## Features

- Quick-call, WhatsApp, and email actions for key contacts
- Tap-to-copy phone numbers with clipboard fallback
- Venue and parking information with Google Maps and Apple Maps links
- Separate schedule page for the wedding day timeline
- Mobile-first layout with safe-area spacing for modern phones
- Static deployment without a framework runtime or build step
- Service Worker caching for fast repeat visits and better resilience on weak mobile networks

## Why It Is Fast

This intentionally looks simple, but the simplicity is the performance strategy.

- No framework runtime
- No external dependencies
- No render-blocking third-party scripts
- Inline critical CSS for immediate rendering
- Tiny JavaScript footprint for only the interactions that need it
- App-shell precaching for the main pages and assets
- Cache-first handling for static assets
- Network-first navigation with cached fallback for HTML pages

That makes the page feel instant on mobile and keeps it usable even when the network at a busy event venue is unreliable.

## Tech Stack

- HTML
- CSS
- Vanilla JavaScript
- Service Worker Cache API
- Web App Manifest

## Privacy

All personal contact names, phone numbers, WhatsApp links, and email addresses in this public version are mock data. The venue and parking information are intentionally kept real so the Google Maps and Apple Maps integration works as a live demo.


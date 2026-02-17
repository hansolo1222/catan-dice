# Dice App for Catan

Build a single-page PWA dice roller optimized for board games (especially Catan).

## Requirements
- **2 dice** (standard d6) displayed prominently
- **Tap anywhere** to roll both dice — big touch target
- **Rolling animation** — dice tumble/shake for ~1 second before settling
- **Rolling sound effect** — generate using Web Audio API (rattling/clicking sound)
- **Sum displayed** large below the dice
- **Roll history** — small scrollable list at bottom showing last 10 rolls
- **Optional jazz music** — toggle button, plays looping lo-fi/smooth jazz from a free source (use a royalty-free audio URL or generate ambient tones with Web Audio API)
- **Catan stats** — show distribution of rolls (how many 7s, etc) since session start
- **PWA installable** — manifest.json + service worker so user can "Add to Home Screen" on iOS

## Design
- Dark background (#1a1a2e or similar deep blue/purple)
- Large white dice with black pips, rounded corners
- Dice should be 3D-ish (CSS box shadows, transforms)
- Big satisfying tap animation (haptic feedback via navigator.vibrate if available)
- Minimal UI — just dice, sum, and a small stats toggle
- Music toggle icon in corner (🎵)
- Full viewport height, centered content
- No scrolling needed for main interaction

## Tech
- Single `index.html` file (vanilla HTML/CSS/JS — no framework needed)
- Web Audio API for dice sounds (no external audio files needed for dice)
- For jazz: use Web Audio API to generate ambient chord progressions, or embed a small royalty-free loop as base64
- CSS animations for dice roll
- Service worker for offline/PWA
- manifest.json for Add to Home Screen

## Files to create
```
index.html      — the entire app
manifest.json   — PWA manifest  
sw.js           — service worker (basic cache)
icon-192.png    — app icon (can be a simple dice SVG rendered to canvas, or just use emoji)
icon-512.png    — larger icon
```

Keep it SIMPLE. One file for the app. The goal is: tap → dice roll → satisfying sound → show result. That's it.

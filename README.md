# 🛡️ CISO Career Tracker
### KAIZEN v08.0 · Built by Corvus-One

![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg)
![Version](https://img.shields.io/badge/version-v08.0-7c6af7)
![Built with](https://img.shields.io/badge/built%20with-Claude-ff8a65)

A single-file progressive web app for professionals pursuing senior security leadership roles. Track daily habits, manage goals, prep for interviews, count down to certifications, and generate weekly progress reports — all from one tool that runs in your browser and installs on your phone.

**[🚀 Open Live Tracker](https://corvus-one.github.io/ciso-career-tracker/CISO_Tracker_kaizen_v08.html)**

![CISO Career Tracker Preview](CISO_Tracker_social_preview.svg)

---

## 📸 What It Does

| Feature | Description |
|---|---|
| 📅 Daily Habit Tracking | Check off security, leadership, learning, and health habits daily |
| 🔗 Linked Resources | Attach a URL to any habit — opens your resource in one click |
| 🎯 Goal Management | Set monthly and quarterly goals with color-coded progress bars |
| 🗺️ Career Roadmap | 5-phase roadmap with progress tracking and inline editing |
| 📓 Journal Entries | Date-stamped daily reflections under Today's Habits |
| 📊 Check-In Score | Daily 1–10 score with 30-day trend chart |
| 🏅 Milestone Badges | 20 unlockable CISO career badges |
| 💡 Ideas System | On Deck / Parking Lot / Warehouse with status tracking |
| ⏱️ Cert Countdown | Countdown timer for CISM, CISSP, or any custom certification |
| 🎯 Interview Prep | 23 CISO questions with reading pane, confidence rating, and talking points |
| 📨 Weekly Wins Digest | Auto-generated weekly summary — copy and send to mentors |
| 📄 Export to PDF | Real PDF download via jsPDF + html2canvas |
| 🤖 AI Coach | Built-in CISO career coach powered by OpenRouter API |
| 🌙 Light / Dark Mode | Full theme toggle with saved preference |
| 📱 Mobile PWA | Installable on iPhone and Android — works offline |
| 🎓 Onboarding Tour | 11-step guided tour for new users |
| 📋 Change Log | Full enhancement history tracked inside the app |
| 🔥 Streak Protection | Evening alert if no habits logged — keeps your streak alive |

---

## 🚀 Quick Start

**Use it instantly — no installation required:**

1. Click → **[Open Live Tracker](https://corvus-one.github.io/ciso-career-tracker/CISO_Tracker_kaizen_v08.html)**
2. On first load, optionally add your [OpenRouter](https://openrouter.ai) API key to activate the AI Coach
3. Start tracking

**Install on iPhone (Safari only):**
1. Open the live URL in Safari
2. Tap the Share button ↑
3. Tap **Add to Home Screen**
4. Tap **Add** — the tracker appears as an app on your home screen

**Install on Android (Chrome):**
Chrome will automatically prompt you to install after a few seconds.

---

## 🧩 Use This Template for Your Own Field

This tracker was built for cybersecurity / CISO career development but the system works for **any career or self-improvement goal**. Here's how to adapt it:

### Step 1 — Use This Template
Click the green **Use this template** button at the top of this repo to create your own copy.

### Step 2 — Open the HTML file
Open `CISO_Tracker_kaizen_v08.html` in a text editor (Notepad on Windows, TextEdit on Mac, or VS Code).

### Step 3 — Customize Your Habits
Find this section in the code (search for `let HABITS`):
```javascript
let HABITS = [
  {id:1, name:"Review security framework docs (30 min)", cat:"Technical", ...},
  ...
]
```
Replace with your own habits and categories. Example for a nurse:
```javascript
let HABITS = [
  {id:1, name:"Review clinical guidelines (20 min)", cat:"Clinical", ...},
  {id:2, name:"Complete CEU module", cat:"Learning", ...},
]
```

### Step 4 — Customize Your Roadmap
Find `const ROADMAP` and replace the 5 phases with your own career milestones.

### Step 5 — Customize Categories
Find `const CAT_COLORS` and update the category names to match your field.

### Step 6 — Update the Title
Search for `CAREER_TRACKER` and replace with your own title (e.g., `NURSING_TRACKER`).

### Step 7 — Deploy
Upload to your own GitHub repo, enable GitHub Pages, and your tracker is live.

---

## 📁 File Structure

```
ciso-career-tracker/
├── CISO_Tracker_kaizen_v08.html    ← Main app (everything in one file)
├── CISO_Tracker_manifest.json      ← PWA manifest (install as app)
├── CISO_Tracker_service-worker.js  ← Offline caching
└── README.md                       ← This file
```

---

## 💾 How Your Data Is Stored

All your data (habits, goals, journal entries, ideas, roadmap, notes) is saved to your **browser's localStorage** — it lives on your device, never on any server. Your data persists between sessions as long as you:
- Use the same browser on the same device
- Don't clear your browser's cache/history

**Storage keys are stable from v05.0 forward** — upgrading to future versions will not erase your data.

---

## 🤖 AI Coach Setup (Optional)

The AI Coach uses [OpenRouter](https://openrouter.ai) — a free API gateway. To activate:

1. Go to [openrouter.ai](https://openrouter.ai) and create a free account
2. Click your profile → **Security** → **Create Key** → copy it
3. Open the tracker and paste your key when prompted
4. Your key is stored only in your browser — never on any server

---

## 🗓️ Version History

| Version | Date | Key Changes |
|---|---|---|
| v05.0 | Mar 15, 2026 | Mobile PWA, Export to PDF, Streak Alert, Sidebar Resize |
| v06.0 | Mar 16, 2026 | Lucide icons, Chart.js, jsPDF, Toasts, Tippy, Accessibility, Animations, Design tokens |
| v07.0 | Mar 17, 2026 | Onboarding tour, Check-in score, Badges, Linked resources, Interview reading pane, Social preview |
| v04.0 | Mar 12, 2026 | Interview Prep, Weekly Wins Digest, Cert Countdown |
| v03.0 | Mar 12, 2026 | Change Log, Journal Entries, Light/Dark Mode, On Deck Status |
| v02.5 | Mar 8, 2026 | AI Coach, Roadmap Editor, File Attachments |
| v02.0 | Mar 1, 2026 | Initial release |

---

## 🛠️ Built With

- Vanilla HTML, CSS, and JavaScript — zero dependencies, zero frameworks
- [Space Mono](https://fonts.google.com/specimen/Space+Mono) + [DM Sans](https://fonts.google.com/specimen/DM+Sans) — Google Fonts
- [OpenRouter API](https://openrouter.ai) — AI Coach
- GitHub Pages — free hosting

---

## 📄 License

MIT — free to use, modify, and distribute. If you build something cool with it, a ⭐ star on the repo is appreciated!

---

## 📄 License

**Copyright © 2026 Corvus-One (Brihan)**

This project is licensed under the **Creative Commons Attribution-NonCommercial 4.0 International License**.

| | |
|---|---|
| ✅ Free to use personally | ✅ Free to share with others |
| ✅ Free to modify and customize | ✅ Must credit Corvus-One (Brihan) |
| ❌ Cannot sell it | ❌ Cannot use commercially |
| ❌ Cannot remove this license | ✅ Must link back to this repo |

See the [LICENSE](LICENSE) file for the full legal text.

[![CC BY-NC 4.0](https://licensebuttons.net/l/by-nc/4.0/88x31.png)](https://creativecommons.org/licenses/by-nc/4.0/)

---

*Built with [Claude](https://claude.ai) · Pursuing CISO · KAIZEN — change for the better, every day*

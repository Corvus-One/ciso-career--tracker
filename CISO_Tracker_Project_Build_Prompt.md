# 🛡️ CISO Career Tracker — Project Build Prompt
### Project-specific rules — use alongside Claude_Universal_Build_Rules.md
### Current Version: KAIZEN v08.0 · Last Updated: March 17, 2026

---

> **How to use:** Paste BOTH this file AND `Claude_Universal_Build_Rules.md` at the start of any new Claude conversation. Start your message with:
> ```
> Continue development of the CISO Career Tracker using the rules below.
> Current version is KAIZEN v08.0.
> ```

---

## SECTION 1 — Project Identity

- **Project:** CISO Career Tracker
- **Purpose:** Single-file PWA for professionals pursuing senior cybersecurity leadership roles
- **Architecture:** Single HTML file — no frameworks, no build tools
- **Storage:** Browser localStorage — all keys use `_v30` suffix (never change)
- **License:** CC BY-NC 4.0 — Copyright © 2026 Corvus-One (Brihan)
- **Repo:** `github.com/Corvus-One/ciso-career-tracker`
- **Live URL:** `https://corvus-one.github.io/ciso-career-tracker/CISO_Tracker_kaizen_v08.html`
- **Current Version:** KAIZEN v08.0

---

## SECTION 2 — File Naming Convention

Always prefix every file with `CISO_Tracker_`:

```
CISO_Tracker_kaizen_v08.html        ← main app
CISO_Tracker_manifest.json          ← PWA manifest
CISO_Tracker_service-worker.js      ← offline cache
CISO_Tracker_Master_Build_Prompt.md ← this file
README.md                           ← repo readme
LICENSE                             ← CC BY-NC 4.0
```

After every delivery post:
`https://corvus-one.github.io/ciso-career-tracker/CISO_Tracker_kaizen_v08.html`

---

## SECTION 3 — Currently Loaded Libraries

Do not duplicate any of these:

| Library | Version | CDN |
|---|---|---|
| Lucide Icons | latest | unpkg.com |
| Chart.js | 4.4.1 | cdnjs.cloudflare.com |
| html2canvas | 1.4.1 | cdnjs.cloudflare.com |
| jsPDF | 2.5.1 | cdnjs.cloudflare.com |
| Popper.js | 2.11.8 | cdnjs.cloudflare.com |
| Tippy.js | 6.3.7 | cdnjs.cloudflare.com |
| Space Mono | — | fonts.googleapis.com |
| DM Sans | — | fonts.googleapis.com |

---

## SECTION 4 — Storage Keys

All localStorage keys use the `_v30` suffix. **Never change these.**

| Key | Data |
|---|---|
| `hc_v30` | Habit checks (daily completions) |
| `gl_v30` | Goals list |
| `pr_v30` | Priorities |
| `id_v30` | Ideas (On Deck / Parking / Warehouse) |
| `hb_v30` | Habits list |
| `qn_v30` | Quick note |
| `roadmap_v30` | Career roadmap phases |
| `changelog_v30` | Change log entries |
| `journal_v30` | Journal entries |
| `interview_v30` | Interview prep confidence + notes |
| `certdates_v30` | Cert countdown dates |
| `sidebar_width_v30` | Saved sidebar width |
| `theme_v30` | Light/dark preference |
| `ios_banner_dismissed_v30` | iOS install banner state |
| `or_api_key` | OpenRouter API key |

---

## SECTION 5 — Design Tokens

**Dark theme (default):**

```css
--bg: #0a0c10
--surface: #12151c
--surface2: #1a1e28
--surface3: #222736
--border: #272d3d
--accent: #7c6af7
--accent2: #4fc3f7
--accent3: #69f0ae
--accent4: #ff8a65
--accent5: #f06292
--red: #ff4757
--yellow: #ffd32a
--green: #2ed573
--text: #e2e8f0
--muted: #5a6480
--header-bg: rgba(18,21,28,0.97)
--overlay-bg: rgba(0,0,0,0.78)
--btn-primary-text: #0a0c10
```

**Light theme (`body.light`):**

```css
--bg: #f0f4fa
--surface: #ffffff
--surface2: #f4f6fb
--surface3: #e8ecf5
--border: #d0d6ea
--accent: #5b4fcf
--accent2: #0277bd
--accent3: #1a7a3c
--accent4: #c45000
--accent5: #ad1457
--red: #c62828
--yellow: #b8860b
--green: #1b5e20
--text: #111827
--muted: #64748b
--header-bg: rgba(255,255,255,0.97)
--overlay-bg: rgba(0,0,0,0.55)
--btn-primary-text: #ffffff
```

**Semantic tokens (both themes):**
`--shadow-sm` · `--shadow-md` · `--shadow-lg` · `--shadow-accent`
`--radius-sm` · `--radius-md` · `--radius-lg` · `--radius-xl`
`--card-hover` · `--input-bg`

---

## SECTION 6 — Version Bump Checklist

When bumping from v06.0 to the next version, update ALL of these:

- [ ] Copyright comment at top of HTML
- [ ] `<title>` tag
- [ ] `.version-tag` in header
- [ ] `aria-label` on version tag
- [ ] Setup screen `.setup-version`
- [ ] AI welcome message in `skipSetup()`
- [ ] Changelog modal subtitle
- [ ] PDF report header string
- [ ] `manifest.json` → `start_url`
- [ ] `service-worker.js` → `CACHE_NAME` and file references
- [ ] Add v0X.0 changelog entries array

---

## SECTION 7 — Current Feature Inventory

| Feature | Location | Status |
|---|---|---|
| Daily habit tracking with categories | Daily view | ✅ |
| Add / delete habits | Daily view | ✅ |
| 📓 Journal entries with date stamps | Daily view | ✅ |
| 🔥 Streak protection alert (after 8pm) | Daily view | ✅ |
| 📋 Log Day modal (mood/energy/win/notes) | Daily view | ✅ |
| Weekly habit grid — 7-day checks | Weekly view | ✅ |
| 8-week bar chart (Chart.js) | Weekly view | ✅ |
| Category balance doughnut (Chart.js) | Weekly view | ✅ |
| Monthly goals with progress bars | Monthly view | ✅ |
| Activity heatmap — 91 days | Monthly view | ✅ |
| Monthly reflection notes | Monthly view | ✅ |
| Quarterly overview mini-calendars | Quarterly view | ✅ |
| Quarterly goals | Quarterly view | ✅ |
| Year heatmap | Quarterly view | ✅ |
| Ideas — On Deck / Parking / Warehouse | Ideas view | ✅ |
| On Deck status — Doing/Done/On Hold | Ideas view | ✅ |
| 📋 Change Log modal — view/add/delete | Nav bar | ✅ |
| 📨 Weekly Wins Digest — copy to clipboard | Nav bar | ✅ |
| 🎯 Interview Prep — 23 Q + star rating | Nav bar | ✅ |
| 📄 Export PDF — jsPDF + html2canvas | Nav bar | ✅ |
| 🌙 Light / Dark mode toggle | Header | ✅ |
| 🤖 AI Coach (OpenRouter API) | Sidebar | ✅ |
| Mini calendar with entry dots | Sidebar | ✅ |
| Top 3 priorities with color cycling | Sidebar | ✅ |
| Streak counter | Sidebar | ✅ |
| Career roadmap + inline edit | Sidebar | ✅ |
| ⏱ Cert countdown — CISM/CISSP/Custom | Sidebar | ✅ |
| Quick note (auto-saved) | Sidebar | ✅ |
| Sidebar drag-to-resize (220–480px) | Desktop | ✅ |
| 📱 Mobile PWA — installable on iOS/Android | All | ✅ |
| Lucide SVG icons throughout | All | ✅ |
| Toast notifications on all key actions | All | ✅ |
| Tippy.js tooltips on feature buttons | Nav bar | ✅ |
| ARIA labels + keyboard navigation | All | ✅ |
| Entrance animations (motion-safe) | All | ✅ |
| Design token system (dark + light) | CSS | ✅ |
| Motivational quote banner with refresh | Header | ✅ |

---

## SECTION 8 — AI Coach Configuration

- Provider: OpenRouter (`openrouter.ai`)
- Model: `openai/gpt-3.5-turbo`
- Key storage: `localStorage.getItem('or_api_key')`
- Key never leaves the device — stored in browser only
- System prompt context: CISO career coach, neurodivergent-friendly
- File attachments supported: images, PDF, TXT, DOC
- Referer header: `https://corvus-one.github.io/ciso-career-tracker/`

---

## SECTION 9 — PWA Configuration

**manifest.json key values:**
```json
{
  "start_url": "/ciso-career-tracker/CISO_Tracker_kaizen_v08.html",
  "scope": "/ciso-career-tracker/",
  "display": "standalone",
  "background_color": "#0a0c10",
  "theme_color": "#0a0c10"
}
```

**Service worker:**
- Cache name: `ciso-tracker-v08`
- Base path: `/ciso-career-tracker/`
- Skips: `claudeusercontent.com`, non-GET requests, OpenRouter API calls
- Strategy: Cache-first with background network update

---

## SECTION 10 — Known Issues & Future Work Queue

**Resolved in v06.0:**
- ✅ iOS 404 error (manifest scope + start_url fix)
- ✅ Habit checkbox broken (function override conflict)
- ✅ Layout grid broken by sidebar resize handle
- ✅ Feature buttons falling into sidebar on mobile
- ✅ Dark mode hardcoded values in light theme

**Queued for future sprints:**
- Social preview image for LinkedIn sharing
- Daily check-in score + trend chart
- CISO milestone badges
- Linked resources per habit
- AI weekly debrief (auto-generated from real data)
- Setup Wizard for other career fields
- Multi-user / cohort accountability mode
- Sortable habits via drag-and-drop (Sortable.js)
- Onboarding tour for new users

---

## SECTION 11 — Quick Reference

```
Current version:      KAIZEN v08.0
Storage key suffix:   _v30 (never change)
Repo:                 github.com/Corvus-One/ciso-career-tracker
Live URL:             https://corvus-one.github.io/ciso-career-tracker/
                      CISO_Tracker_kaizen_v08.html
License:              CC BY-NC 4.0
Copyright:            © 2026 Corvus-One (Brihan)
File prefix:          CISO_Tracker_
Max tool calls/shift: ~12
Checkpoint trigger:   "checkpoint"
Next shift trigger:   "next shift"
Universal rules file: Claude_Universal_Build_Rules.md
```

---

*Built with Claude · Pursuing CISO · KAIZEN — change for the better, every day*

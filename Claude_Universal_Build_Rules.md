# 🤖 Claude Universal Build Rules
### Reusable for any project — no editing required
### Last Updated: March 16, 2026

---

> **How to use:** Paste this file at the start of any new Claude conversation alongside your project-specific prompt. These rules apply to every app you build with Claude regardless of the project.

---

## SECTION 1 — The Shift System

Every response that uses tools follows the shift format.
Post this header at the top of every build response:

```
📋 SHIFT [N] of [TOTAL]
Task: [what this shift covers]
Tool calls this shift: ~[number]
Starting from: [filename]
```

**Rules:**
- Max ~12 tool calls per shift
- When 2–3 tool calls from the limit, flag it and roll remaining work to the next response
- Before every sprint, estimate total shifts needed
- User triggers next shift by saying `"next shift"`
- Always declare scope before starting — never over-build
- Roll unfinished work into the next response automatically — never leave work incomplete

**Shift cost reference:**

| Action | Tool Calls |
|---|---|
| Read one file | 1 |
| Search for something | 1 |
| Make one code edit | 1 |
| Build a visual/diagram | 1–2 |
| Deliver a file | 1 |
| Run a code check | 1 |

**Shift estimate format — post before every sprint:**

```
📋 SHIFT ESTIMATE
Task: [what we're doing]
Shifts needed: [number]
This shift covers: [specific scope]
Tool calls this shift: ~[number]
```

---

## SECTION 2 — The 4pt Framework

All new features or sprints must follow this framework **before any code is written:**

**1. Define the Work**
What exactly is being built? Who uses it? What problem does it solve?

**2. Architect the Design / Tools**
What libraries, APIs, or tools are needed? What CDNs are approved? What are the tradeoffs?

**3. AI Rules**
Do we need special AI handling? Keychain vs localStorage? Are any new secrets or APIs introduced? What storage method is appropriate?

**4. Plan**
Break into shifts. Estimate tool calls. Identify hiccups. Lock the plan before building.

> Never start building without completing all 4 steps.
> Always QA the plan for hiccups before locking it.
> No building until the user approves the plan.

---

## SECTION 3 — File Delivery Rules

- Always deliver files **individually** — NEVER as a zip
- Maximum **3 files** delivered per shift
- After every file delivery post the live URL if applicable
- Name files clearly with version numbers where relevant
- Notify user which files changed and which are unchanged each shift
- Never deliver a file without confirming it passes the code quality checks in Section 6

---

## SECTION 4 — Approved CDN Sources

Only load external resources from these approved CDNs:
- `cdnjs.cloudflare.com`
- `unpkg.com`
- `cdn.jsdelivr.net`
- `fonts.googleapis.com`

**When suggesting new tools or plugins, always:**
1. Confirm it is available on an approved CDN
2. Check for conflicts with existing libraries
3. Estimate minified file size (prefer under 50kb)
4. Confirm it works on iOS Safari 15+
5. Check if it requires a build step — if yes, reject it
6. Assess any security risks introduced
7. Consider loading on-demand rather than on page load

**Preferred evaluation order:**
Pure CSS solution first → Vanilla JS second → Lightweight CDN library third → Heavy framework last

---

## SECTION 5 — Version Control Rules

**Recommended version format:** `vXX.0`

| Change Type | Version Impact |
|---|---|
| Bug fix / layout patch | No bump — same number |
| Cosmetic patch | No bump — same number |
| New feature added | Minor bump (v06.0 → v06.1) |
| Full sprint of new features | Major bump (v06.0 → v07.0) |

**When bumping versions:**
- Update ALL version references throughout the file
- Update any manifest or config files that reference the filename
- Update any service workers or cache names
- Add changelog entries for every change made

---

## SECTION 6 — Code Quality Standards

Before every file delivery, verify:

- [ ] No duplicate function names
- [ ] No broken function overrides (`_orig` pattern is forbidden — fold logic into original function instead)
- [ ] All localStorage / storage calls wrapped in `try/catch`
- [ ] Storage keys are stable — never change them between versions
- [ ] All modals closeable via Escape key
- [ ] ARIA labels on all interactive regions
- [ ] `prefers-reduced-motion` wraps all animations
- [ ] No hardcoded theme-specific colors in CSS — use CSS custom properties
- [ ] Copyright comment at top of every delivered file
- [ ] Service workers skip preview/sandbox domains

**Quick syntax checks to run before delivering:**
```bash
grep -n "function.*function\|_orig" [file]
grep -c "try.*localStorage" [file]
```

---

## SECTION 7 — iOS / Mobile Compatibility

Always verify these before delivering any web app file:

- [ ] `viewport-fit=cover` in meta viewport tag
- [ ] `apple-touch-icon` link tag present
- [ ] PWA manifest has absolute `start_url` and `scope`
- [ ] Service worker references correct filenames
- [ ] No `inset:0` — use `top:0; right:0; bottom:0; left:0` longhand (iOS 14 compatibility)
- [ ] `-webkit-overflow-scrolling:touch` on all scrollable areas
- [ ] `window.print()` replaced with jsPDF or has iOS fallback
- [ ] `navigator.clipboard` has iOS-safe fallback
- [ ] Service worker registration skips preview/sandbox environments

**Mobile breakpoints (recommended):**
- `768px` — tablet/mobile layout switch
- `480px` — compact mobile layout

---

## SECTION 8 — Design Standards

**Font guidance:**
- Choose distinctive, professional fonts — never Arial, Roboto, or system fonts
- Pair a display/mono font with a clean body font
- Load via Google Fonts CDN

**Icon guidance:**
- Use SVG icon libraries (Lucide recommended) — never emoji in UI elements
- Exceptions: mood indicators and decorative stamps are allowed emoji

**Color system:**
- Always use CSS custom properties — never hardcode colors in rules
- Define both dark and light theme tokens in `:root` and `body.light`
- Use semantic token names: `--shadow-sm`, `--overlay-bg`, `--header-bg`, etc.

**Animations:**
- Always wrap in `@media (prefers-reduced-motion: no-preference)`
- Modal entrances: spring cubic-bezier for polish
- View transitions: subtle fade/slide — never jarring
- Never animate for decoration alone — always serve a purpose

---

## SECTION 9 — Accessibility Standards

Every build must include:

- Semantic HTML elements (`<header>`, `<main>`, `<aside>`, `<nav>`)
- `role` and `aria-label` on all major regions
- `aria-pressed` on toggle buttons
- `aria-live` region for dynamic notifications
- `:focus-visible` ring on all interactive elements
- Escape key closes all modals and drawers
- Arrow key navigation on tab/button groups
- `.sr-only` class for screen reader only content
- All icon-only buttons have `aria-label` or `title`

---

## SECTION 10 — Changelog Standards

Every change must be logged. Entry format:

```javascript
{
  id: [unique number],
  date: 'YYYY-MM-DD',
  num: '[version]',
  cat: '[category]',
  desc: '[what changed]',
  reason: '[why it was needed]',
  tested: 'Yes / In Progress / No',
  priority: 'High / Medium / Low',
  status: 'GREEN / YELLOW / RED',
  comments: '[notes]'
}
```

**Suggested categories:**
`UI / Layout` · `Feature` · `Bug Fix` · `Data / Content` · `Integration` · `Reporting` · `Security / Access`

---

## SECTION 11 — Communication Style

The user (Brihan) is neurodivergent. Always:
- Communicate **one concept at a time**
- Provide **visual step-by-step instructions**
- Set **clear checkpoints** before proceeding
- Ask clarifying questions with **clickable options** where possible
- Estimate time and shifts **before** starting any work
- Flag issues **before** building, not during
- Never assume — confirm understanding at each step
- When introducing a new concept: define it simply, use real-world analogies, show don't tell

---

## SECTION 12 — Checkpoint Process

When user calls a checkpoint:
1. Stop building immediately
2. Deliver current file(s)
3. Post a structured test checklist covering all features in the current build
4. Wait for user confirmation before continuing
5. Log any failures as RED entries in the changelog

**Checkpoint trigger phrase:** `"checkpoint"`
**Next shift trigger phrase:** `"next shift"`

---

## SECTION 13 — GitHub Workflow

**Standard upload process — always individual files, never zip:**
1. Download each file individually from Claude (click ↓ on each file card)
2. Go to the GitHub repo
3. Click **Add file → Upload files**
4. Drag files in → **Commit changes**
5. Wait 30 seconds → GitHub Pages live URL updates automatically

**Files always go in repo root — never in subfolders**

**To enable GitHub Pages (one-time setup):**
1. Go to repo **Settings → Pages**
2. Under Branch select **main**
3. Click **Save**
4. Site publishes at `https://[username].github.io/[repo-name]/`

---

*These rules apply universally to all Claude-assisted builds.*
*For project-specific rules, see the companion project prompt file.*

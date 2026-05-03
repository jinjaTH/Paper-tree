# Paper Tree Theory — Tree Assessment

A psychology self-assessment based on **Paper Tree Theory**, which views the mind as a living tree that grows through interpretation and is shaped by those around it.

Built as a single-file HTML application. No backend, no data collection, no external API calls.

---

## What it does

Users answer 18 questions across 6 psychological dimensions, then receive a personalized tree visualization and written analysis.

**Dimensions measured:**

| Dimension | What it captures |
|---|---|
| Self-Health | Identity stability and resilience |
| Interpretive Pattern | Flexibility in how you read events |
| Core Belief Density | How fixed your foundational beliefs are |
| Internal Weather | Current emotional/cognitive state |
| Sensitivity to Outside Influence | How easily others shape your thinking |
| Processing of Past Experience | Whether old experiences are integrated or still pending |

**Languages:** Thai · English · Japanese

---

## How to use

Open `index.html` in any modern browser. No build step, no server needed.

```
open index.html
```

Or serve locally:

```bash
python -m http.server 8080
# → http://localhost:8080
```

---

## Features

- **Adaptive questions** — question flow responds to answers
- **Visual tree** — canvas drawing reflects your 6 dimension scores
- **Seeded tree rendering** — same answers always produce the same tree
- **Keyboard navigation**
  - Scale questions: press `1`–`5` to select
  - Scenario questions: press `A`–`D` to select
  - `→` or `Enter` to advance · `←` to go back
- **Back button** — navigate to previous questions
- **Save as PDF** — browser print dialog renders result cleanly
- **Share results** — encodes scores in URL hash, copies link to clipboard
- **Take again** — restart from language selection

---

## Security notes

This file was reviewed for common client-side vulnerabilities:

| Issue | Status |
|---|---|
| XSS via innerHTML | Fixed — scenario options built with `textContent`; dynamic values escaped with `esc()` |
| Unbounded text input | Fixed — textarea limited to 500 characters via `maxlength` |
| Global score exposure | Fixed — `_dimScores` is module-scoped, not on `window` |
| Tampered share URL | Fixed — `parseShareHash` validates lang, numeric range, and structure before use |
| Content Security Policy | Added — `<meta http-equiv="Content-Security-Policy">` blocks external script injection and outbound connections (`connect-src: none`) |
| Data exfiltration | Not applicable — no network requests are made after page load; all data stays in-browser |

**The app sends no data anywhere.** Answers, scores, and the tree visualization exist only in the browser session. Clearing the page discards everything.

---

## File structure

```
index.html   — complete app (HTML + CSS + JS, single file)
README.md    — this file
.gitignore   — standard web project ignores
```

---

## Based on

**Paper Tree Theory** — a psychological framework developed in 2026 that maps mental architecture using the metaphor of a tree: roots (past experience), trunk (core beliefs), branches (interpretive patterns), canopy (self), weather (internal state), and external forces (outside influence).

---

*Paper Tree Theory · 2026 · Results are a snapshot of today. Trees can always change.*

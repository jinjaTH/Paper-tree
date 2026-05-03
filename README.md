# Paper Tree Theory — Tree Assessment

A psychology self-assessment grounded in **Paper Tree Theory** (ทฤษฎีต้นไม้กระดาษ), a conceptual framework that models the architecture of the human mind as a living tree surrounded by falling papers.

**Framework conceived by jinje · Interface developed by Claude**

---

## What it measures

The assessment maps 6 psychological dimensions derived from the Paper Tree Theory framework:

| Dimension | What it captures | Tree visual |
|---|---|---|
| Self-Health | Identity stability and resilience | Trunk height, thickness, crack |
| Interpretive Pattern | Flexibility in reading events | Branch spread angle |
| Core Belief Density | How fixed core beliefs are | Red frame marks on trunk |
| Internal Weather | Current cognitive/emotional state | Paper density, leaf coverage |
| Sensitivity to Outside Influence | How easily others pre-color your papers | Trunk lean, dashed external lines |
| Processing of Past Experience | Whether old experiences are integrated | Root depth, surface tangles |

Each tree generated is unique and **psychologically meaningful** — different scores produce visually distinct trees, not just size variations.

**Languages:** Thai · English · Japanese

---

## The framework

Paper Tree Theory (2026, jinje) proposes that the mind is not a blank sheet but a vast, boundless space with a living tree at its center. Five core elements interact in a continuous cycle:

- **White Space** — unactualized potential
- **The Tree** — the Self, existing before experience
- **Papers** — experiences, memories, thoughts (which can be pre-colored by other trees)
- **The Faceless Child** — the interpretive agent (faceless because identity is not fixed)
- **Frames** — core beliefs; more influential than ordinary papers, harder to remove

The primary loop: Tree → Papers → Drawing (interpretation) → Root Absorption → back to Tree.

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

- **Adaptive question flow** — 18 questions across 6 dimensions
- **Procedural tree** — grown from your psychological profile using a seeded fractal algorithm; same answers always produce the same tree
- **Animated growth** — roots → trunk → branches → frame marks → leaves, sequenced to feel organic
- **OMORI-inspired aesthetic** — cream paper, near-black ink, OMORI red used only for core belief frames
- **Background particles** — floating paper scraps drift in the background
- **Typewriter rendering** — questions appear character by character
- **Keyboard navigation** — `1–5` for scale, `A–D` for scenario, `→`/`Enter` next, `←` back
- **Share results** — encodes scores in URL hash; copy link to share your tree
- **Save as PDF** — clean print CSS hides all navigation
- **Restart** — return to language selection

---

## Security

This app sends no data anywhere. All answers, scores, and tree rendering happen in the browser session only.

| Issue | Status |
|---|---|
| XSS via innerHTML | Fixed — all dynamic values use `textContent` or `esc()` sanitizer |
| Unbounded text input | Fixed — textarea `maxlength=500` |
| Score exposure | Fixed — `_dimScores` is module-scoped, not on `window` |
| Share URL tampering | Fixed — hash decoded with range + structure validation |
| Content Security Policy | Added — `connect-src: none` blocks all outbound requests |

---

## File structure

```
index.html         — complete app (single file, no dependencies)
README.md          — this file
.gitignore
.claude/           — design skills (impeccable, animate, harden, etc.)
.impeccable.md     — design context for this project
```

---

*Paper Tree Theory framework conceived by jinje · Interface developed by Claude · 2026*
*Trees can always change.*

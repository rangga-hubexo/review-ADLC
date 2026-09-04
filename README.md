# ADLC Review — a commit history of how we learned

A single-page, self-contained retrospective of how the **ADLC** (Agentic Development Life Cycle) process became part of our daily engineering workflow. The story is told as a `git log`: each phase of the journey is a commit, and the final entry is the merge into `main`.

Built for Hubexo in the company brand palette (plum + lime).

## What's in the repo

| File | Purpose |
|------|---------|
| `review.html` | The entire page: markup, styles, and behaviour. No build step, no dependencies beyond Google Fonts. |
| `README.md` | This file. |

## Viewing it

Open `review.html` directly in a browser:

```bash
open review.html          # macOS
xdg-open review.html      # Linux
```

Or serve it locally if you prefer a proper origin:

```bash
python3 -m http.server 8080
# then visit http://localhost:8080/review.html
```

Internet access is only needed for the Manrope and IBM Plex Mono web fonts. Without it the page falls back to system fonts and still works.

## The story it tells

The page walks through six "commits":

1. **phase/01 init** — Started from zero with simple local agents driven by well-written Markdown instructions.
2. **phase/02 feat** — Split deterministic work (guardrails, gates, repeatable steps) from non-deterministic work (reasoning, judgment) and designed the architecture around that line.
3. **phase/03 refactor** — Changed how work is distributed across the team by using Claude plugins.
4. **phase/04 release** — Agents run autonomously, with humans in the loop for critical decisions and oversight.
5. **phase/05 refactor** — The developer's role shifted from writing code by hand to reviewing plans and giving feedback on results.
6. **main merge** — The real achievement: how much the team learned and how the engineering mindset evolved.

## Interactions

- **Scroll** to reveal each commit. The gutter line animates into place as entries enter the viewport.
- **`j` / `k`** jump to the next / previous commit.
- The hero types out `git log --reverse --graph` on load.
- Respects `prefers-reduced-motion`: animations and the typing effect are disabled when the OS setting is on.

## Editing

Everything lives in `review.html`.

- **Brand colours and fonts** are CSS custom properties at the top of the `<style>` block (`--plum`, `--lime`, `--sans`, `--mono`).
- **Adding a commit:** copy an existing `<article class="commit">` block inside the log section and update the hash, message, and body. The scroll observer and `j`/`k` navigation pick up new entries automatically.
- **The merge entry** uses the `merge` class, which shortens the gutter line so the graph terminates cleanly. Keep it last.

## Sharing

Since the page is a single file with no external assets other than fonts, it can be attached to a message, dropped into any static host, or published as-is.

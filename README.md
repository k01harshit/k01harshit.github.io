# Harshit Kumar — Portfolio

Single-file portfolio site. No build step, no dependencies.

## Deploy on GitHub Pages

1. Create a public repo named **`k01harshit.github.io`**.
2. Upload `index.html` and `resume.pdf` to the repo root (and the `images/` folder once you have photos).
3. Go to **Settings → Pages**, set Source to **Deploy from a branch**, branch `main`, folder `/ (root)`, and save.
4. The site goes live at `https://k01harshit.github.io` within a minute or two.

## Adding your photos

Create an `images/` folder next to `index.html` and add:

| File | Where it appears | Suggested size |
|---|---|---|
| `images/profile.jpg` | Hero portrait card (and link previews) | 900 × 1125 px, portrait 4:5 |
| `images/gallery-1.jpg` | Large square tile at the start of the Gallery | 1200 × 1200 px |
| `images/gallery-2.jpg` … `gallery-5.jpg` | Small tiles | 800 × 600 px |
| `images/gallery-6.jpg`, `gallery-7.jpg` | Wide tiles on the last row | 1200 × 500 px |

- Until `profile.jpg` exists, the hero shows an "HK" monogram.
- The Gallery is the last section. Each tile shows a "Photo N" placeholder until its image exists, then the photo fades in automatically. Clicking a photo opens a full-screen viewer with arrow-key navigation.
- To change a caption, edit the `<figcaption>` text in `index.html` (search for "Moment 1").
- Want more tiles? Copy a `<figure>` line inside `#galleryGrid` and bump the number.
- Keep each photo under ~400 KB (compress at squoosh.app) so the site loads fast.

## Editing content

All project, paper and link data lives in the `<script>` near the bottom of `index.html`:

- `L` — every external link (papers, certificate, NewsBits images, socials)
- `projects` — the Work cards and their detail popups
- `papers` — the Publications list. Add a link to a paper once it is accepted by putting `["Read paper","https://..."]` in its `l` list.
- `KB` — the chatbot's knowledge. Each entry has keywords (`k`) and an answer (`a`). Add entries to teach it new answers.

## Features

- Customize panel (palette button in the nav), remembered per visitor:
  - Background: Morph (default, thousands of 3D particles that explode in on load and shape-shift between sphere, torus, DNA helix, galaxy and wave), Hyperspace, Flow field, Waves, Network, Minimal. Clicking empty space triggers a burst in most modes.
  - Hover effect: Spotlight (default), 3D tilt, Lift, Neon, None
  - Theme: Graphite, Paper, Aurora, Ember, Ocean, Mono
- To change the defaults for new visitors, search `getLS('hk-bg'` and `getLS('hk-hover'` near the end of `index.html` and swap `'morph'` / `'spotlight'` for another option id.
- Animated aurora gradient, subtle grain and grid, text-scramble section labels
- Custom cursor, magnetic buttons, spotlight card borders, 3D tilt on cards and portrait
- Built-in chatbot ("Ask about Harshit") that answers questions about your work. It runs entirely in the browser from the `KB` list, so no API key is needed and nothing is sent anywhere.
- Playground with three interactive pieces: Classifier Arena (live k-NN decision boundary), Spike Catcher (reflex game with best-score tracking), and Spike Agreement (SADP intuition demo)
- Command menu (Ctrl/⌘ + K) for sections, projects, themes and links
- Responsive, keyboard accessible, respects reduced-motion settings

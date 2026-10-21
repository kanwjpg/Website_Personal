# Kanawa Alfarezel Banyu Ramlan — Portfolio

Static site. Six self-contained HTML pages, no build step needed to deploy, no network dependencies.

    index.html        Home
    about.html        About
    work.html         Work (6 projects, filterable)
    services.html     Services
    skills.html       Skills
    case-study.html   Case study template

## 3D layer

Every page carries a small WebGL renderer (k3d.js, bundled inside the page) that draws
the glossy 3D objects: the hero toys, the studio shots, the lifted project covers, the
About fan cards, the micro:bit boards, the line-follower robot, the service icons, and the
contact and banner scenes (cards, rocket, orbiting toolkit, star).

- Objects follow the cursor and spin faster on hover.
- Drag a scene with the mouse to spin it; let go and it springs back.
- Click or tap an empty spot to pop a burst of 3D confetti.
- Scenes spring into place as they scroll into view.
- Easter egg: the Konami code (↑ ↑ ↓ ↓ ← → ← → B A) or typing "kanawa".

On devices without WebGL, or with "reduce motion" switched on, the page falls back to the
original flat design or a still 3D frame.

## Deploy on GitHub Pages

1. Create a repository and upload every file in this folder to the root.
2. Settings → Pages → Source: `Deploy from a branch` → Branch: `main` / `/ (root)`.
3. The site is live at `https://<username>.github.io/<repo>/`.

For a personal domain, name the repository `<username>.github.io`.

## Deploy elsewhere

Netlify Drop or Vercel: drag this folder onto the upload area. No settings needed.

## Editing

The pages here are built from `source/` in the project folder:

    source/pages/<page>.html   page markup, CSS and page scripts
    source/k3d.js              the 3D renderer and every 3D scene
    source/build.py            rebuilds these six files: python source/build.py

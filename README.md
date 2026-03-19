# ✦ Inkwell — Premium iPad Notes

A premium, fully offline note-taking app for iPad. Built as a single-file PWA (Progressive Web App) — no server, no account, no internet required after first load.

---

## Deploy to GitHub Pages in 5 minutes

### Step 1 — Create a GitHub account
Go to [github.com](https://github.com) and sign up (free).

---

### Step 2 — Create a new repository

1. Click the **+** icon top-right → **New repository**
2. Repository name: `inkwell` (or anything you like)
3. Set to **Public** ← important, Pages requires public for free accounts
4. Check **"Add a README file"**
5. Click **Create repository**

---

### Step 3 — Upload the files

You need to upload these 3 files:
- `index.html`
- `sw.js`
- `manifest.json`

**Option A — Upload via browser (easiest)**
1. In your new repository, click **Add file → Upload files**
2. Drag all 3 files onto the upload area
3. Scroll down → click **Commit changes**

**Option B — Via Git (if you have Git installed)**
```bash
git clone https://github.com/YOUR_USERNAME/inkwell.git
cd inkwell
# copy index.html, sw.js, manifest.json into this folder
git add .
git commit -m "Deploy Inkwell"
git push
```

---

### Step 4 — Enable GitHub Pages

1. In your repository, click **Settings** (top tab)
2. In the left sidebar → click **Pages**
3. Under **Source** → select **Deploy from a branch**
4. Branch: **main** | Folder: **/ (root)**
5. Click **Save**

GitHub will show: *"Your site is being published..."*

---

### Step 5 — Get your URL

After 1–2 minutes, your app is live at:
```
https://YOUR_USERNAME.github.io/inkwell/
```

Replace `YOUR_USERNAME` with your actual GitHub username.

---

### Step 6 — Install on iPad

1. Open Safari on your iPad
2. Go to `https://YOUR_USERNAME.github.io/inkwell/`
3. Tap the **Share button** (box with arrow pointing up)
4. Scroll down → tap **Add to Home Screen**
5. Name it **Inkwell** → tap **Add**

The app is now installed on your iPad home screen. It works **completely offline** — no internet needed after the first load.

---

## How offline storage works

| Storage | What it stores | Limit | Survives |
|---|---|---|---|
| **IndexedDB** | All notes, folders, strokes | ~500MB+ | App reinstalls, cache clears |
| **localStorage** | Fast startup cache | ~5MB | Normal browsing |
| **Service Worker** | App code, fonts | ~50MB | Airplane mode, no wifi |

Your notes never leave your device. No account, no server, no cloud.

---

## Export & backup your notes

Inside the app → home screen → tap the **database icon** (top right) → **Export backup**

This downloads an `.inkwell` file (plain JSON) to your device. To restore, tap **Import backup** and select the file.

---

## Update the app

When you want to update Inkwell with new features:

1. Replace `index.html` (and `sw.js` if changed) in your GitHub repository
2. The app auto-detects the update next time it loads with internet
3. A toast notification appears: *"App updated — refresh to apply"*
4. Pull down to refresh on iPad

---

## File structure

```
inkwell/
├── index.html      ← The entire app (HTML + CSS + JS)
├── sw.js           ← Service worker (offline caching)
├── manifest.json   ← PWA manifest (icon, name, display mode)
└── README.md       ← This file
```

---

## Keyboard shortcuts (when using with a keyboard)

| Key | Action |
|---|---|
| `P` | Pen tool |
| `E` | Stroke eraser |
| `X` | Pixel eraser |
| `S` | Shape tool |
| `R` | Toggle ruler |
| `B` | Bookmark current page |
| `T` | Open tags |
| `F` | Presentation mode |
| `1–5` | Pen thickness |
| `+` / `-` | Zoom in/out |
| `0` | Reset zoom |
| `⌘Z` | Undo |
| `⌘⇧Z` | Redo |
| `ESC` | Exit presentation mode |

---

## Tech stack

- **Pure HTML/CSS/JS** — zero dependencies, zero build step
- **Canvas API** — all drawing, shape recognition, ruler
- **IndexedDB** — primary offline storage
- **Service Worker** — PWA offline shell caching
- **localStorage** — fast startup cache / fallback
- **Web fonts** — Cormorant Garamond + DM Sans + DM Mono via Google Fonts (cached offline after first load)

---

## License

MIT — use, modify, deploy freely.

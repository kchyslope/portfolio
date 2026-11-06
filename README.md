# Kristen Hyslope — Portfolio (Neon Noir)

Self-contained portfolio site, deployed with GitHub Pages at
`https://kchyslope.github.io/portfolio/`.

## Files

| File | Purpose |
|------|---------|
| `index.html` | Complete self-contained portfolio page |
| `Kristen_Hyslope_Resume.pdf` | Resume served by the **$ DOWNLOAD_RESUME** button |
| `README.md` | This file |

Both `index.html` and `Kristen_Hyslope_Resume.pdf` must sit in the **repo root** (same folder).

---

## Updating your resume (do this every time)

The download button in `index.html` (around line 184) looks like this:

```html
<a href="Kristen_Hyslope_Resume.pdf?v=2026-11-05" download="Kristen_Hyslope_Resume.pdf" class="btn-sec">$ DOWNLOAD_RESUME</a>
```

- `href` is the file on the server. The `?v=...` part is a version stamp that forces browsers and GitHub's CDN to fetch the new file instead of a cached old copy.
- `download="..."` is the filename visitors see when they save it.

### Step 1 — Name the new PDF exactly

Rename your new resume to:

```
Kristen_Hyslope_Resume.pdf
```

Capitals, underscores, and `.pdf` must match exactly. GitHub Pages is case-sensitive — `kristen_hyslope_resume.pdf` is a **different file** and the button will keep serving the old one.

### Step 2 — Bump the version stamp in `index.html`

Open `index.html`, find `Kristen_Hyslope_Resume.pdf?v=` and change the date to today, e.g.:

```
?v=2026-11-05   →   ?v=2027-01-15
```

If you update twice in one day, add a letter: `?v=2027-01-15b`, `?v=2027-01-15c`.

**Skip this and visitors may keep downloading the old resume for hours.** This is the step that was missed before.

### Step 3 — Upload both files in one commit

**Option A — GitHub website**

1. Go to https://github.com/kchyslope/portfolio
2. Click **Add file → Upload files**
3. Drag in **both** `Kristen_Hyslope_Resume.pdf` and `index.html`
4. GitHub will say the files will be replaced — that's correct
5. Commit message: `Update resume YYYY-MM-DD` → **Commit changes** to `main`

**Option B — Terminal**

```bash
cd portfolio                     # your local clone
git pull origin main
cp ~/Downloads/Kristen_Hyslope_Resume.pdf .
# edit index.html and bump ?v= date
git add Kristen_Hyslope_Resume.pdf index.html
git commit -m "Update resume YYYY-MM-DD"
git push origin main
```

### Step 4 — Confirm the repo is clean

In the repo file list, check:

- There is **one** resume PDF, named `Kristen_Hyslope_Resume.pdf`
- No leftover copies like `kristen_hyslope_resume.pdf`, `Kristen_Hyslope_Resume (1).pdf`, or `resume.pdf` — delete them (open file → ⋯ → **Delete file**)
- Click the PDF → its latest commit should be the one you just made

### Step 5 — Verify it's live

1. Wait 1–2 minutes (check the **Actions** tab — the "pages build and deployment" run should be green)
2. Open a **private/incognito window**
3. Go to `https://kchyslope.github.io/portfolio/` and click **$ DOWNLOAD_RESUME**
4. Confirm the PDF is the new version

If it's still old: hard-refresh (Cmd+Shift+R), confirm the `?v=` date in the live page source changed (right-click → View Page Source → search `Resume.pdf`), and recheck Step 4.

### Optional — standalone HTML copy

If you also keep a standalone/offline copy of the site, it has the resume baked in. Regenerate it after updating the PDF, or it will still contain the old resume.

---

## Deploying the site (first time / full rebuild)

1. Upload `index.html` and `Kristen_Hyslope_Resume.pdf` to the repo root (Step 3 above)
2. Go to **Settings → Pages**
3. Source: **Deploy from a branch**
4. Branch: **main** / **(root)** → **Save**
5. Site goes live at `https://kchyslope.github.io/portfolio/` within a few minutes

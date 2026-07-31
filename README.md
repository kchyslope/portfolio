# Kristen Hyslope — Portfolio (Neon Noir)

Self-contained portfolio site, ready to deploy to GitHub Pages.

## Deploy to GitHub Pages

### Option A — Push via terminal (recommended)

```bash
# Clone your repo
git clone https://github.com/kchyslope/portfolio.git
cd portfolio

# Copy index.html into the repo root
cp /path/to/index.html .

# Commit and push
git add index.html
git commit -m "Add Neon Noir portfolio"
git push origin main
```

Then in your GitHub repo:
1. Go to **Settings → Pages**
2. Source: **Deploy from a branch**
3. Branch: **main** / root
4. Save — your site will be live at `https://kchyslope.github.io/portfolio/`

### Option B — Upload via GitHub UI

1. Go to https://github.com/kchyslope/portfolio
2. Click **Add file → Upload files**
3. Drag `index.html` in
4. Commit to main
5. Enable Pages as above

## Customisation checklist

- [ ] Update LinkedIn URL in `index.html` (search `linkedin.com/in/`)
- [ ] Update email address (search `mailto:`)
- [ ] Swap `$ DOWNLOAD_CV` link to your actual CV PDF
- [ ] Add `og:image` meta tag for social sharing preview

## Files

| File | Purpose |
|------|---------|
| `index.html` | Complete self-contained portfolio page |
| `README.md` | This file |

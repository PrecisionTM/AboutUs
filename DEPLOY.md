# About Us — Vercel Deployment Guide

## Folder Structure

```
vercel-about/
├── index.html              ← Single-file landing page (inline CSS + JS)
├── vercel.json             ← { "cleanUrls": true } only
├── DEPLOY.md               ← This file
├── download                ← Blank placeholder (required)
└── images/
    └── carlie-cannon-rius.jpg   ← CEO / founder photo
```

---

## Deployment Steps

1. **Initialize Git & push to GitHub**
   ```bash
   cd vercel-about
   git init
   git add .
   git commit -m "initial commit — About Us landing page"
   git branch -M main
   git remote add origin https://github.com/YOUR-ORG/about-landing.git
   git push -u origin main
   ```

2. **Import into Vercel**
   - Go to [https://vercel.com/new](https://vercel.com/new)
   - Click **Import Git Repository**
   - Select the `about-landing` repo
   - **Framework Preset**: Other
   - **Root Directory**: *(leave blank)*
   - **Build Command**: *(leave blank)*
   - **Output Directory**: *(leave blank)*
   - **Install Command**: *(leave blank)*
   - Click **Deploy**

3. Vercel will serve `index.html` from the folder root. No build step needed.

---

## ⚠️ Do NOT

- Add a `build` script to `package.json`
- Add a `/(.*) rewrite` in `vercel.json`
- Set a subfolder as the Root Directory in Vercel
- Use absolute image paths (e.g., `/images/...`) — always use relative (`images/...`)
- Use `vh`, `dvh`, or `svh` units for any section heights

---

## CTA URLs

| Button | URL |
|---|---|
| Primary CTA (Check Eligibility) | `https://precisiontelemed.com/get-started/` |
| Secondary CTA (Consult a Doctor) | `https://precisiontelemed.com/start-general-consultation-program/` |
| Learn About Programs | `https://www.precisiontelemed.com` |

---

## Conventions Compliance Checklist

- [x] No `vh`, `dvh`, or `svh` units anywhere in the file
- [x] Hero section uses CSS gradient background (no bg image) — no `min-height` viewport dependency
- [x] Brand tokens match conventions: `--color-bg: #fdfbf7`, `--color-bg-alt: #f5f2ec`, `--color-primary: #788C75`
- [x] `--section-gap: clamp(3rem, 6vw, 5rem)` (content-driven)
- [x] All image paths are relative (`images/...`) — no absolute `/images/...` paths
- [x] Single image asset: `images/carlie-cannon-rius.jpg`
- [x] `vercel.json` contains only `{ "cleanUrls": true }` — no rewrites or extra fields
- [x] Blank `download` placeholder file present
- [x] No `../` cross-folder image references
- [x] CTA URLs match conventions.md (`/get-started/`, `/start-general-consultation-program/`)
- [x] Tested standalone and iframe-safe (no circular viewport sizing)

---

*Last updated: April 2026*

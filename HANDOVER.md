# Cheque Book Racing — Website Handover

_Last updated: 2026-07-07_

Motorcycle workshop website — service, respray, custom paint & wraps, performance tuning, custom builds. Krugersdorp, Gauteng. Owner: **Billy**.

---

## 0. Recent changes (2026-07-07)

- **Nav wordmark redesigned.** The old plain "Cheque Book / Racing" text was tiny on desktop and hidden on mobile — leaving an empty gap next to the badge logo. Rebuilt it as a styled CSS wordmark: **"CHEQUEBOOK / RACING"**, gold fill + purple outline, racing slant — matching the printed logo look.
  - Bigger on desktop, now **visible on mobile** (fills the gap next to the logo, before the arrow button).
  - Built with CSS text (Anton font), **not an image** — stays sharp at any size and blends into the dark header (the `wordmark.jpg` file has a white background, so it would show a white box — avoided).
  - Auto-shrinks on scroll and on small screens so it never overflows or overlaps.
  - Edit in `index.html`: CSS class `.brand-word` (styling) + the `<span class="brand-word">` markup in the nav.
- **Deployed to production** via `vercel --prod`. ⚠️ This change was pushed to Vercel directly but **not yet committed to git** — run `git add index.html && git commit && git push origin main` to keep the repo in sync with live.

---

## 1. Live links

| What | URL |
|------|-----|
| **Live site** | https://cheque-book-racing.vercel.app |
| GitHub repo | https://github.com/debruynpw-pixel/cheque-book-racing (branch `main`) |
| Vercel project | `cheque-book-racing` (team **2linket**, account debruynpw-pixel) |

**Local file:** `C:\Users\pwdeb\Desktop\ChequeBookRacing\index.html`

---

## 2. What it is

A **single-file website** — everything (HTML + CSS + JS) lives in `index.html`. No build step, no framework. Open the file or host it anywhere static.

**Contact / leads:** No CRM. Every enquiry goes straight to Billy's **WhatsApp: 084 609 2023** (international `27846092023`).

---

## 3. Brand / theme

- **Colours:** deep purple (`#120a20` / `#1a0f2e` / `#341c5c`), violet glow (`#7b3fe4` / `#9d5cff`), gold (`#f4b724`), cream text (`#f5f2ec`). Checkered-flag accents throughout.
- **Fonts (Google):** Anton (headlines), Rajdhani (labels/techno), Inter (body).
- **Logo:** `logo.jpg` (round helmet badge) in nav + footer. Nav wordmark ("CHEQUEBOOK RACING") is **CSS text**, not an image — see §0. `wordmark.jpg` (white-bg image) stays in folder but is not used in the header.

---

## 4. Sections (top to bottom)

1. **Nav** — badge logo + wordmark, links, Get a Quote button.
2. **Hero** — headline + **bike image slider** (main image + Left / Front / Right thumbnails, click to swap). Bikes are AI-generated purple/gold BMW S1000RR in the Cheque Book livery.
3. **Marquee** — scrolling service strip.
4. **Services** — 12 service cards.
5. **Our Work (Build Journey)** — per-bike **scroll-through stage slideshow** (arrows + swipe + dots). Each build = a sequence of upgrade stages (mags → strip → respray → done). Edit the `builds` array in `<script>`; set each stage's `img` to a filename (empty = "Photo coming soon" placeholder). **Currently 1 demo build, all placeholders** — needs Billy's real stage photos.
6. **Get a Quote** — the guided flow (see below).
7. **Merch** — teaser band → WhatsApp.
8. **Footer / Contact** — WhatsApp, phone, area.
9. Floating WhatsApp button (bottom-right).

---

## 5. The quote flow (important)

3 steps → WhatsApp:
1. **Pick a category:** Service / Fault Finding / Respray / Tuning / Appearance.
2. **Category-specific questions** (bike model, colour idea, symptom, etc.).
3. **Your details** — name, area, **"When suits you?"** = ASAP / This week / 📅 Pick a date (compact calendar), optional notes.
4. **Send to WhatsApp** → opens Billy's chat with everything pre-filled. He replies with a price.

To change the questions: edit the `flow` object in the `<script>` in `index.html`.
To change the WhatsApp number: find-and-replace `27846092023` across `index.html`.

---

## 6. Images / assets

**Used by the live site** (committed to git):
- `index.html`, `logo.jpg`, `wordmark.jpg`
- `flagship-left-gold.png`, `flagship-front.png`, `flagship-right-gold.png` (hero slider — left/front/right)

**Local only, NOT deployed** (in `.gitignore` — kept for reuse):
- `bike-turntable.mp4`, `bike-orbit*.mp4` — scrapped scroll-video hero (local `file://` blocks video scrubbing in Chrome; static image used instead)
- `flagship-banner.png` — bike with "CHEQUE BOOK RACING" banner backdrop (nice, currently unused)
- `test-purple-side.png` — configurator base
- `flagship-left.png` / `flagship-right.png` — old black/white checker versions (superseded by gold)

**Source bike photos** (Billy's BMW S1000RR): `C:\Users\pwdeb\Desktop\Chequebook Racing\Puen_Gun.jpg` (side), `2025 bmw s1000 RR face.jpg` (front).

**Job photos for before/after** (not yet used): 6× `WhatsApp Image 2026-07-06...jpeg` in `C:\Users\pwdeb\Desktop\Chequebook Racing\`.

Images generated with **Higgsfield** (Nano Banana Pro for image edits, Seedance for video). CLI = `hf`. Auth via `hf auth login`; workspace `23df8b2e-29b2-4293-8da0-83de09f74aac`.

---

## 7. How to edit & redeploy

**Edit:** change `index.html` (and/or swap images in the folder, keeping the same filenames).

**Preview locally:** open `index.html` in a browser. (For anything video-based use a local server, not `file://`.)

**Deploy changes:**
```bash
cd "C:\Users\pwdeb\Desktop\ChequeBookRacing"
git add index.html <any-new-images>
git commit -m "your message"
git push origin main
vercel --prod --yes
```
Live URL stays https://cheque-book-racing.vercel.app.

---

## 8. Outstanding / next steps

1. **"Design Your Ride" configurator** — colour swatch-swap (purple/gold/black/red/etc.) of the bike. Base image ready (`test-purple-side.png`); need to batch the other colour variants and wire a swatch section. Decisions already locked: pre-generated swatches, toggles = paint colour / finish / livery / wheels.
2. **Build Journey slideshow** — replace placeholder stages with Billy's real photos. Drop photos in the folder, set each stage's `img` in the `builds` array. **Tip for Billy:** shoot each stage from the *same angle* so the slideshow flows cleanly. (The 6 files in `Chequebook Racing` folder are flyers/stickers, NOT bike-stage photos — don't use them here.)
3. Optional: add Billy's real social links, business hours, address/map.

---

## 9. Gotchas

- **WhatsApp number** must be in international format in links: `27846092023` (not `0846092023`).
- **No video on `file://`** — Chrome blocks local video scrubbing; that's why the hero is a static image + slider.
- **Single file** — keep it that way for easy hosting/handover; don't split into multiple files unless you switch to a proper host/build.
- Commit only the images the site actually uses; the big scrapped media is git-ignored on purpose.

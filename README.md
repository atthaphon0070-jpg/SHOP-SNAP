# SHOP SNAP — Interactive Presentation (20-month final incubation report)

**SHOP SNAP (ComuShoping) · รายงานผลการบ่มเพาะ รอบ 20 เดือน (ปิดโครงการ)**
ผู้ประกอบการระดับ Pre-incubation · UBI มหาวิทยาลัยราชภัฏมหาสารคาม

An 18-slide interactive HTML presentation built around the idea *“ซื้อของดี ได้รู้จักคนทำ”* (Buy good things, know who made them).

- **One self-contained file:** `index.html`. The fonts (IBM Plex Sans Thai and Manrope, SIL OFL), every illustration, the Snappy mascot, and the QR codes are built in.
- **No network needed:** the presentation runs offline. The only external links are the clickable `https://braincospace.com/shop` links.
- **Size:** about 400 KB.

## Open and present

1. Open `index.html` in Chrome, Edge, or Safari. Double-clicking the file works.
2. Press **F** for full screen. The layout is designed for 16:9 at 1920×1080 and scales to any screen.

| Action | Keys / input |
|---|---|
| Next slide | → · ↓ · Space · PageDown · mouse wheel down · swipe left/up · the **›** button · the right edge zone of the screen |
| Previous slide | ← · ↑ · Shift+Space · PageUp · mouse wheel up · swipe right/down · the **‹** button · the left edge zone |
| First / last slide | Home / End |
| Speaker notes (Thai) | **N**. A panel opens on the right and the slide shrinks so it stays fully visible. It includes a timer. |
| Overview of all 18 slides | **O**. Click a slide, or use the arrow keys and Enter. Esc closes it. |
| Full screen | **F** |
| Reduce motion | **M**. This toggles reduced motion. The system `prefers-reduced-motion` setting is followed automatically. |
| Keyboard help | **?** |
| Jump to a slide | `index.html#8` |

- **Wheel and trackpad:** one gesture moves exactly one slide. Trackpad momentum is absorbed, so it does not skip slides.
- **Clicks:** clicks on buttons, links, QR codes, feature tags (slide 8), and the before/after slider (slide 6) never change the slide.
- **Navigation bar:** it hides itself after about 3 seconds without mouse movement. Move the mouse to bring it back.
- **Printing:** Print / Save as PDF produces 18 pages at 1920×1080, each showing a slide in its final state.

## Before presenting: fill in the real team data

Some information was not in the source document, so the slides show clear **“รอยืนยัน” (pending)** placeholders instead of invented data. Edit the `window.SHOPSNAP_CONFIG` block near the top of `index.html`:

| Slide | Setting | What it does |
|---|---|---|
| 02 | `entrepreneurs[0..1].name / .photo` | Real names and photos of the two entrepreneurs |
| 09 | `dataStatus.*` | `'pending'`, `'real'` or `'demo'` for each item. The source left these unconfirmed. |
| 13 | `revenue` | `null` shows the placeholder. `'none'` shows **ยังไม่มีรายได้** (no revenue yet). Any other text is shown exactly as typed. |
| 17 | `extraActivity` / `hideExtraActivity` | The optional 4th activity card. Add one only after it is confirmed, or hide the card. |
| 01, 05, 06, 08, 11, 17 | `photos.*` | Real screenshots and photos: homepage, artisan photo, old and new website, 5 prototype screens, course cover, activity photos |

**Photos:** put image files in `assets/img/` and use relative paths, for example `'assets/img/member1.jpg'`. A real photo replaces the illustration and its “ภาพประกอบ / ภาพจำลอง” label. If a file is missing, the slide keeps the illustration, so nothing appears broken. In that case the browser console shows a warning about the missing file.

**QR codes (slides 8 and 15):** these are built into the page as SVG and encode exactly `https://braincospace.com/shop`. Both were checked by decoding them from rendered screenshots. Whether the website itself is online has **not** been verified. Check it before the presentation.

## Content integrity notes

- **Illustrations:** the woven-mat artwork (slide 5), the before/after website mock-ups (slide 6), the prototype screens (slide 8), and the course-book cover (slide 11) are clearly labelled as illustrations or mock-ups. No real people, producers, reviews, prices, or sales figures are invented.
- **Revenue (slide 13):** no figure is filled in automatically.
- **Revenue channels (slide 10):** they are labelled as *proposed* channels, not revenue that already exists.
- **Course outputs (slide 12):** they are labelled as *intended* course outputs.
- **Comparison (slide 7):** it is labelled as the team's positioning view.
- **Speaker roles:** the suggested split (ผู้ดูแลระบบ: slides 6–9 · ผู้ดูแลการตลาด: slides 5 and 10–14) and the prepared committee Q&A appear only in the speaker notes.

## What was tested

These checks were run in headless Chromium:

- **Slide count:** 18 slides.
- **Wheel and trackpad:** one trackpad flick with decaying momentum moves exactly one slide. Single notches up and down work.
- **Keys:** ←/→/Space/PageUp/PageDown/Home/End.
- **Buttons:** the next/prev buttons and the edge zones. Clicking the slide body does not navigate.
- **Speaker notes:** they follow the current slide. Scroll keys and the wheel inside the notes do not change the slide. Esc closes them.
- **Overview:** shows 18 thumbnails. Keyboard and click selection both work.
- **Animations when going back:** entrance animations replay correctly when navigating backwards.
- **Links and printing:** `#n` deep links work, and printing produces exactly 18 PDF pages.
- **Reduced motion:** the reduced-motion mode shows the final state of each slide.
- **Phone width:** no horizontal overflow.
- **QR codes:** both decode to the correct URL.
- **Console:** no errors or warnings, apart from the expected warning when a configured photo file is missing.

Browsers other than Chromium, and real fullscreen on a projector, were not tested.

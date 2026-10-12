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

## Files

- `index.html` — the interactive presentation (self-contained, works offline).
- `SHOP-SNAP-Presentation.pdf` — static 18-page PDF (1920×1080 per page, each slide in its final state) for sharing or printing. Speaker notes are not included.

## Content

- **Slide 02:** entrepreneurs นายวชิรเมธี ภูกิ่งพลอย and นายภานุวัฒน์ พิชัยเชิด, with their photos embedded in the file.
- **Slide 09:** the implemented part is the website structure and the five prototype features; sample data in the prototype is described as being for testing the positioning, not real sales data.
- **Slide 13:** summarises months 15–20 (new positioning, prototype website, 4 revenue channels). No revenue figure is shown.
- **Slide 17:** three activities (BMC ตีให้แตก · Startup Thailand League 2025 · SET e-Learning) shown with illustrations.
- **QR codes (slides 8 and 15):** encode exactly `https://braincospace.com/shop`.

## Optional edits

The `window.SHOPSNAP_CONFIG` block near the top of `index.html` has two optional settings:

- `revenue` — `null` (default) shows no revenue box on slide 13. Text such as `'12,345 บาท'` adds a TOTAL line showing that exact text; `'none'` shows “ยังไม่มีรายได้”.
- `photos.*` — optional real screenshots/photos for slides 1, 5, 6, 8 and 11 (paths such as `'assets/img/homepage.png'`). A missing file keeps the illustration.

If you edit `index.html`, re-export the PDF from Chrome: Print → Save as PDF, background graphics on.

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
- **Console:** no errors or warnings.
- **PDF:** 18 pages; both QR codes in the PDF decode to the correct URL.

Browsers other than Chromium, and real fullscreen on a projector, were not tested.

---
name: betheme-cinematic-scroll-heroes
description: Build, troubleshoot, and optimize cinematic scroll hero sections in WordPress BeTheme/BeBuilder. Use when working on BeTheme Global Sections, BeBuilder layouts, parallax heroes, sprite sheet or JPG/WebP frame sequence scroll effects, overlays, shape dividers, mobile fallbacks, performance, max_input_vars save issues, or safe Code element snippets.
---

# BeTheme Cinematic Scroll Heroes

Use this skill to help build, troubleshoot, and optimize cinematic scroll hero sections in WordPress BeTheme/BeBuilder. Prefer native BeBuilder controls first, then add targeted Code elements only when the motion or interaction cannot be built safely with native tools.

## Core Workflow

1. Start with a BeTheme Global Section.
2. Set the hero section to full-screen or `100vh`.
3. Choose the simplest media layer that achieves the effect: static WebP, background video, parallax image, sprite sheet, or JPG/WebP frame sequence.
4. Add overlay/color grade and Shape Divider for readability and transition.
5. Keep foreground copy editable in BeBuilder with Fancy Heading, text, and Button elements.
6. Use Global Styles, Presets, Templates, and Global Sections for repeatability.
7. Test desktop, mobile, performance, and BeBuilder save behavior before publishing.

## BeTheme Rules

- Inspect live files in `wp-content/themes/betheme` before code-level work in a real WordPress install.
- Remember that BeBuilder content may be serialized and shortcode-based.
- Avoid hand-editing serialized builder data unless the structure is fully understood.
- Use the visual builder for layout; use custom code only for sprite sheets, scroll sequences, targeted JavaScript, or advanced interactions.
- If BeBuilder pages, Theme Options, or large layouts refuse to save, recommend raising PHP `max_input_vars` to `10000` or higher.

## Cinematic Hero Principles

- Use the formula: depth + motion + restraint = cinematic.
- Keep motion layers meaningful; 2-4 moving or layered elements is usually enough.
- Use absolute-positioned Wraps for atmospheric layers such as fog, dust, branches, particles, light leaks, or texture.
- Use classes such as `layer-slow`, `layer-medium`, `layer-fast`, `hero-foreground`, and `hero-atmosphere` when custom styling is needed.
- Prefer WebP and CDN-hosted heavy assets.
- On mobile, prefer a static WebP fallback, fewer layers, reduced animation, and no large scroll sequence unless highly optimized.

## BeBuilder Elements To Prefer

- Section, Wrap, and Column for structure.
- Section background image/video, parallax background, overlay, filters, Shape Dividers, entrance animations, and responsive controls before custom code.
- Fancy Heading or Heading for hero text; keep one clear H1 per page.
- Button for primary CTA.
- Query Loops, Photo Boxes, Icon Boxes, or Feature Boxes for supporting sections below the hero.
- Code element only for advanced motion that native BeBuilder cannot do cleanly.

## Global Section Build Checklist

Use this when building a reusable cinematic scroll hero in BeTheme.

- Create a new Global Section.
- Set section height to full-screen or `100vh`.
- Name the section clearly, such as `Global Hero - Cinematic Sprite`.
- Set responsive behavior before adding complex layers.
- Choose one background layer: static WebP image, BeTheme video background, JPG/WebP frame sequence, or sprite sheet.
- Add atmosphere only if it improves the section: fog, dust, branches, light leak, texture, or slow parallax accent.
- Keep total moving layers to 2-4.
- Add a dark or gradient overlay for readability.
- Add Shape Divider at bottom for transition.
- Test text contrast on desktop and mobile.
- Use Fancy Heading, optional paragraph, and Button/CTA.
- Keep text editable in BeBuilder, not baked into the image.
- Save as Global Section.
- Apply Global Styles and Presets.
- Drop the section into the target page.
- Test performance and mobile.

## Performance Checklist

- Use WebP for images and sprite sheets.
- Use a CDN for large background media.
- Keep sprite sheets as small as practical.
- Avoid 4K assets unless truly necessary.
- Compress before uploading to WordPress.
- Use 2-4 motion layers max.
- Avoid multiple heavy scroll listeners.
- Use `requestAnimationFrame` for scroll-driven effects.
- Use passive scroll listeners.
- Disable complex effects on mobile when needed.
- Increase `max_input_vars` to `10000+` for large BeBuilder pages.
- Disable unused BeTheme features.
- Limit plugins.
- Enable caching.
- Test after adding each major visual effect.
- Check GTmetrix, Query Monitor, Chrome DevTools, Lighthouse, and a real phone on cellular.

## Red Flags

- Page builder refuses to save.
- Hero stutters while scrolling.
- Mobile hero loads blank or late.
- Background sequence uses dozens of uncompressed JPGs.
- Text is part of the image instead of editable foreground content.

## Recipes

### Fast Native Hero

Use native BeBuilder only.

1. Create a Global Section.
2. Set height to `100vh`.
3. Add WebP background.
4. Add Overlay.
5. Add Shape Divider.
6. Add Fancy Heading and Button.
7. Save as Global Section.

### Sprite Sheet Hero

Use when you want video-like scroll motion.

1. Export video frames.
2. Combine into one horizontal WebP sprite sheet.
3. Upload to CDN or Media Library.
4. Add Code element to full-screen Global Section.
5. Paste sprite-sheet code.
6. Add Overlay + Shape Divider.
7. Add foreground Fancy Heading + Button.
8. Save and reuse.

### JPG/WebP Sequence Hero

Use for prototypes or when sprite sheet is not ready.

1. Export numbered frames.
2. Compress frames.
3. Upload to CDN or Media Library.
4. Use Media Carousel or scroll-driven Code element.
5. Add overlay and foreground content.
6. Test mobile carefully.

### BeParallax-Inspired Rebuild

1. Import a BeParallax section into BeBuilder.
2. Open Layer Navigator.
3. Identify the Section, Wraps, Columns, Code elements, and background settings.
4. Duplicate the section.
5. Replace media.
6. Replace copy.
7. Convert repeated design settings into Presets.
8. Save the final version as a Global Section.

## BeParallax Demo Guidance

Use the BeParallax demo as a learning reference. Import full demos only on staging. Safer workflow: import individual pre-built sections inside BeBuilder, open Layer Navigator/Page Navigator, duplicate the section, replace media and copy, convert repeatable settings into Presets, then save the result as a Global Section.

Live preview reference:

```text
https://themes.muffingroup.com/be/parallax/

Sprite Sheet Code Element Example
Paste this into a BeBuilder Code element inside a full-screen Global Section. Replace SPRITE_URL, MOBILE_FALLBACK_IMAGE.webp, and totalFrames.
<div class="bt-cinematic-sprite-hero" id="bt-cinematic-sprite-hero">
  <div class="bt-cinematic-sprite" id="bt-cinematic-sprite"></div>
  <div class="bt-cinematic-overlay"></div>
</div>

<style>
  .bt-cinematic-sprite-hero {
    width: 100%;
    height: 100vh;
    overflow: hidden;
    position: relative;
    isolation: isolate;
  }

  .bt-cinematic-sprite {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    background-size: cover;
    background-repeat: no-repeat;
    background-position: 0 0;
    z-index: 1;
  }

  .bt-cinematic-overlay {
    position: absolute;
    inset: 0;
    background: linear-gradient(180deg, rgba(0, 0, 0, .45), rgba(0, 0, 0, .2));
    z-index: 2;
    pointer-events: none;
  }

  @media (max-width: 767px) {
    .bt-cinematic-sprite-hero {
      height: 75vh;
      background-image: url('MOBILE_FALLBACK_IMAGE.webp');
      background-size: cover;
      background-position: center;
    }

    .bt-cinematic-sprite {
      display: none;
    }
  }
</style>

<script>
(function () {
  const spriteUrl = 'SPRITE_URL.webp';
  const totalFrames = 60;
  const scrollDistanceMultiplier = 1.8;

  const container = document.getElementById('bt-cinematic-sprite-hero');
  const sprite = document.getElementById('bt-cinematic-sprite');

  if (!container || !sprite) return;

  sprite.style.backgroundImage = `url('${spriteUrl}')`;

  let ticking = false;

  function updateSprite() {
    const rect = container.getBoundingClientRect();
    const viewportHeight = window.innerHeight || document.documentElement.clientHeight;
    const start = viewportHeight;
    const end = -container.offsetHeight * scrollDistanceMultiplier;
    const progress = Math.min(Math.max((start - rect.top) / (start - end), 0), 1);
    const currentFrame = Math.floor(progress * (totalFrames - 1));
    const frameWidthPercent = 100 / totalFrames;

    sprite.style.backgroundPositionX = -(currentFrame * frameWidthPercent) + '%';
    ticking = false;
  }

  function onScroll() {
    if (!ticking) {
      window.requestAnimationFrame(updateSprite);
      ticking = true;
    }
  }

  window.addEventListener('scroll', onScroll, { passive: true });
  window.addEventListener('resize', onScroll);
  updateSprite();
})();
</script>
JPG/WebP Frame Sequence Code Element Example
Use this when a sprite sheet is not ready. Replace frameBaseUrl, frameCount, and fileExtension.
<div class="bt-frame-sequence-hero" id="bt-frame-sequence-hero">
  <img class="bt-frame-sequence-img" id="bt-frame-sequence-img" alt="Cinematic hero frame" />
  <div class="bt-frame-sequence-overlay"></div>
</div>

<style>
  .bt-frame-sequence-hero {
    position: relative;
    width: 100%;
    height: 100vh;
    overflow: hidden;
    background: #000;
    isolation: isolate;
  }

  .bt-frame-sequence-img {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    z-index: 1;
  }

  .bt-frame-sequence-overlay {
    position: absolute;
    inset: 0;
    background: rgba(0, 0, 0, .35);
    z-index: 2;
    pointer-events: none;
  }

  @media (max-width: 767px) {
    .bt-frame-sequence-hero {
      height: 75vh;
    }
  }
</style>

<script>
(function () {
  const frameBaseUrl = 'https://your-site.com/wp-content/uploads/2026/hero-frame-';
  const frameCount = 60;
  const fileExtension = 'webp';
  const padLength = 4;

  const container = document.getElementById('bt-frame-sequence-hero');
  const img = document.getElementById('bt-frame-sequence-img');

  if (!container || !img) return;

  function frameUrl(index) {
    const number = String(index + 1).padStart(padLength, '0');
    return `${frameBaseUrl}${number}.${fileExtension}`;
  }

  function preloadFrames() {
    for (let i = 0; i < frameCount; i++) {
      const preload = new Image();
      preload.src = frameUrl(i);
    }
  }

  let ticking = false;

  function updateFrame() {
    const rect = container.getBoundingClientRect();
    const viewportHeight = window.innerHeight || document.documentElement.clientHeight;
    const progress = Math.min(Math.max((viewportHeight - rect.top) / (viewportHeight + container.offsetHeight), 0), 1);
    const currentFrame = Math.floor(progress * (frameCount - 1));

    img.src = frameUrl(currentFrame);
    ticking = false;
  }

  function onScroll() {
    if (!ticking) {
      window.requestAnimationFrame(updateFrame);
      ticking = true;
    }
  }

  img.src = frameUrl(0);
  preloadFrames();
  window.addEventListener('scroll', onScroll, { passive: true });
  window.addEventListener('resize', onScroll);
  updateFrame();
})();
</script>
Assistant Operating Instructions
When helping a user build a BeTheme cinematic scroll hero:

Start with native BeBuilder elements.
Recommend a Global Section workflow.
Use performance-first language: WebP, CDN, compression, caching, and reduced mobile motion.
Introduce Code elements only when native BeBuilder cannot accomplish the desired motion.
Always mention mobile fallback for heavy visual effects.
Mention max_input_vars when the page is complex or BeBuilder saving is unreliable.
Prefer reusable sections, presets, and global styles over one-off custom work.
Use Layer Navigator for diagnosing layout problems.



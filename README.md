# BeTheme Cinematic Scroll Heroes – Complete Mastery Skill  
**For Claude (Projects / Knowledge Base) + Novamira Pro Skills**

**Version:** 1.0 (June 2026)  
**Author:** Compiled by Grok for JudahFlix  
**Purpose:** Give Claude (or Novamira) deep, production-ready knowledge of BeTheme’s BeBuilder so it can instantly design, dissect, and optimize cinematic scroll heroes using native elements + safe custom code.

## How to Use This Skill

### In Claude
1. Create a new **Claude Project** (or use an existing one).
2. Upload this file as **Knowledge**.
3. In the project instructions, add:  
   > “You are an expert BeTheme cinematic hero specialist. Always reference the BeTheme Cinematic Scroll Heroes Mastery Skill when helping with BeBuilder, parallax, video alternatives, or sprite sheets.”

### In Novamira Pro
- Create a new **Skill** → paste the entire content (or upload as `BeTheme-Cinematic-Hero-Skill.md`).

### In GitHub
1. Create a new repository (example name: `betheme-cinematic-hero-skill`).
2. Add this file as `README.md` or `betheme-cinematic-hero-skill.md`.
3. (Optional) Add a simple `LICENSE` (MIT) and a short `README` linking to this file.

---

## Table of Contents
1. Core BeTheme Architecture & Gotchas  
2. Mastering Important BeBuilder Elements (Visual + Custom Code)  
3. Cinematic Scroll Hero Principles & Performance Rules  
4. Importing & Exploring the BeParallax Demo  
5. Exact Dissection of BeParallax Cinematic Sections  
6. JPG Frame Sequences (Video Alternative for Speed)  
7. Sprite Sheet Optimization (Ultimate Performance Method)  
8. Ready-to-Use Recipes & Pro Workflow  

---

### 1. Core BeTheme Architecture & Gotchas
- BeTheme stores data in serialized arrays and relies heavily on shortcodes.  
- Always let the AI inspect live files in `wp-content/themes/betheme` and the database.  
- **Critical fix**: If pages or Theme Options won’t save → increase `max_input_vars` to 10,000+ (via `.htaccess` or host panel).  
- Use **Global Styles**, **Global Sections**, **Templates**, and **Presets** for consistency and speed.  
- Performance: Disable unused features, use WebP, limit plugins, enable caching.

### 2. Mastering Important BeBuilder Elements (Visual + Custom Code)
- **Sections / Wraps / Columns**: Foundation. Use Absolute positioning for layered parallax.  
- **Fancy Heading / Heading**: SEO-critical; use dynamic data tags.  
- **Icon Box / Feature Box / Photo Box**: Workhorses for floating accents.  
- **Button / CTA**: Hover animations + scroll-to-section.  
- **Accordion / Toggle / Tabs**: Interactive content blocks.  
- **Slider / Media Carousel**: Easy frame playback.  
- **Code Element**: Secret weapon for custom JS/CSS, sprite sheets, scroll-driven sequences.  
- **Query Loops**: Dynamic content without plugins.  
- **Inline shortcodes**: `[highlight]`, `[icon]`, `[button]` inside any text.  

**Pro workflow**: Build 90% visually → drop Code element for advanced motion → save as Global Section.

### 3. Cinematic Scroll Hero Principles & Performance Rules
- Depth + Motion + Restraint (2–4 layers max).  
- Native tools: Section background (video/image/parallax), Overlay + filters, Shape Dividers, Entrance animations.  
- Multi-layer parallax via absolute Wraps + stellar.js (BeTheme’s built-in).  
- Mobile fallback: Static image + disable heavy effects.  
- Always test with GTmetrix / Query Monitor.

### 4. Importing & Exploring the BeParallax Demo
- Live preview: https://themes.muffingroup.com/be/parallax/  
- **Full demo import** (staging only) via Appearance → BeTheme Pre-Built Websites.  
- **Recommended**: Import individual Pre-built Sections (Hero / Portfolio categories) directly inside BeBuilder.  
- Use Layer / Page Navigator to instantly see structure.

### 5. Exact Dissection of BeParallax Cinematic Sections

#### Hero Section (“Cinematic Opening”)
- Section: 100vh, parallax image or video background, dark overlay, bottom Shape Divider.  
- Inside: Centered Wrap → Fancy Heading + Button.  
- Absolute Wrap for floating layers (fog, particles) with classes `layer-slow` / `layer-medium`.

#### Services / Features Section
- Parallax background + absolute decorative layers + Icon Boxes with staggered entrance animations.

#### Portfolio Showcase Section
- Query Loop or Photo Boxes with individual parallax transforms on scroll.

#### Transition / Story Section
- Video/parallax background + opposing Shape Dividers for film-wipe effect.

**Replication tip**: Import → Duplicate → Replace media → Save as Global Section.

### 6. JPG Frame Sequences (Video Alternative for Speed)
**Method 1 – Simple Autoplay Slider**  
- Drag Media Carousel / Slider → add numbered JPGs → set 0ms transition + autoplay.

**Method 2 – Scroll-Driven Sequence (Code Element)**  
(Full code from earlier conversation – use the numbered JPG version when sprite sheet is not yet ready.)

### 7. Sprite Sheet Optimization (Ultimate Performance Method)
**Why it wins**: 1 HTTP request instead of 30–60 frames.

**Step-by-step**:
1. Create horizontal sprite sheet (WebP preferred) with tools like spritesheetgenerator.online or ffmpeg.
2. Upload to Media Library.
3. In hero Section → Absolute Wrap → Code Element → paste the sprite-sheet JS/CSS below.

```html
<div id="sprite-container" style="width:100%; height:100vh; overflow:hidden; position:relative;">
  <div id="sprite" style="width:100%; height:100%; background-size:cover; background-repeat:no-repeat; background-position:0 0;"></div>
</div>

<script>
  const spriteUrl = 'https://your-site.com/wp-content/uploads/YEAR/cinematic-sprite.webp';
  const totalFrames = 60;
  const frameWidthPercent = 100 / totalFrames;
  const spriteElement = document.getElementById('sprite');
  spriteElement.style.backgroundImage = `url('${spriteUrl}')`;

  function updateSpriteOnScroll() {
    const scrollY = window.scrollY;
    const heroHeight = document.getElementById('sprite-container').offsetHeight || window.innerHeight;
    const progress = Math.min(Math.max(scrollY / (heroHeight * 1.8), 0), 1);
    const currentFrame = Math.floor(progress * (totalFrames - 1));
    spriteElement.style.backgroundPositionX = -(currentFrame * frameWidthPercent) + '%';
  }

  window.addEventListener('scroll', updateSpriteOnScroll);
  // Optional autoplay: uncomment loopPlayback function from previous guides
</script>

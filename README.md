name: betheme-cinematic-scroll-heroes
description: Build, troubleshoot, and optimize cinematic scroll hero sections in WordPress BeTheme/BeBuilder. Use when working on BeTheme Global Sections, BeBuilder layouts, parallax heroes, sprite sheet or JPG/WebP frame sequence scroll effects, overlays, shape dividers, mobile fallbacks, performance, max_input_vars save issues, or safe Code element snippets.
BeTheme Cinematic Scroll Heroes
Use this skill to help build, troubleshoot, and optimize cinematic scroll hero sections in WordPress BeTheme/BeBuilder. Prefer native BeBuilder controls first, then add targeted Code elements only when the motion or interaction cannot be built safely with native tools.

Core Workflow
Start with a BeTheme Global Section.
Set the hero section to full-screen or 100vh.
Choose the simplest media layer that achieves the effect: static WebP, background video, parallax image, sprite sheet, or JPG/WebP frame sequence.
Add overlay/color grade and Shape Divider for readability and transition.
Keep foreground copy editable in BeBuilder with Fancy Heading, text, and Button elements.
Use Global Styles, Presets, Templates, and Global Sections for repeatability.
Test desktop, mobile, performance, and BeBuilder save behavior before publishing.
BeTheme Rules
Inspect live files in wp-content/themes/betheme before code-level work in a real WordPress install.
Remember that BeBuilder content may be serialized and shortcode-based.
Avoid hand-editing serialized builder data unless the structure is fully understood.
Use the visual builder for layout; use custom code only for sprite sheets, scroll sequences, targeted JavaScript, or advanced interactions.
If BeBuilder pages, Theme Options, or large layouts refuse to save, recommend raising PHP max_input_vars to 10000 or higher.
Cinematic Hero Principles
Use the formula: depth + motion + restraint = cinematic.
Keep motion layers meaningful; 2-4 moving or layered elements is usually enough.
Use absolute-positioned Wraps for atmospheric layers such as fog, dust, branches, particles, light leaks, or texture.
Use classes such as layer-slow, layer-medium, layer-fast, hero-foreground, and hero-atmosphere when custom styling is needed.
Prefer WebP and CDN-hosted heavy assets.
On mobile, prefer a static WebP fallback, fewer layers, reduced animation, and no large scroll sequence unless highly optimized.
BeBuilder Elements To Prefer
Section, Wrap, and Column for structure.
Section background image/video, parallax background, overlay, filters, Shape Dividers, entrance animations, and responsive controls before custom code.
Fancy Heading or Heading for hero text; keep one clear H1 per page.
Button for primary CTA.
Query Loops, Photo Boxes, Icon Boxes, or Feature Boxes for supporting sections below the hero.
Code element only for advanced motion that native BeBuilder cannot do cleanly.
Reference Files
Load these only when relevant:

references/global-section-build-checklist.md: use before or during a reusable Global Section build.
references/performance-checklist.md: use when checking speed, mobile behavior, asset choices, scroll jank, or save issues.
references/pro-workflow.md: use when choosing between native, sprite sheet, JPG/WebP sequence, or BeParallax-inspired recipes.
references/sprite-sheet-hero.html: use when the user needs a BeBuilder Code element snippet for scroll-driven sprite sheet playback.
references/jpg-sequence-scroll-hero.html: use when the user needs a BeBuilder Code element snippet for scroll-driven numbered image frames.
BeParallax Demo Guidance
Use the BeParallax demo as a learning reference. Import full demos only on staging. Safer workflow: import individual pre-built sections inside BeBuilder, open Layer Navigator/Page Navigator, duplicate the section, replace media and copy, convert repeatable settings into Presets, then save the result as a Global Section.

Live preview reference:

https://themes.muffingroup.com/be/parallax/
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

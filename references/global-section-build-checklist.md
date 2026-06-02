# Global Section Build Checklist

Use this when building a reusable cinematic scroll hero in BeTheme.

## Setup

- Create a new Global Section.
- Set section height to full-screen or `100vh`.
- Name the section clearly, such as `Global Hero - Cinematic Sprite`.
- Set responsive behavior before adding complex layers.

## Background Layer

Choose one:

- Static WebP image.
- BeTheme video background.
- JPG/WebP frame sequence.
- Sprite sheet.

## Atmosphere Layer

Add only if it improves the section:

- Fog.
- Dust.
- Branches.
- Light leak.
- Texture.
- Slow parallax accent.

Keep total moving layers to 2-4.

## Overlay And Shape Divider

- Add a dark or gradient overlay for readability.
- Add Shape Divider at bottom for transition.
- Test text contrast on desktop and mobile.

## Foreground Content

- Fancy Heading.
- Optional paragraph.
- Button/CTA.
- Keep text editable in BeBuilder, not baked into the image.

## Save And Reuse

- Save as Global Section.
- Apply Global Styles and Presets.
- Drop the section into the target page.
- Test performance and mobile.

## Final Checks

- WebP assets.
- CDN for large files.
- `max_input_vars` set to `10000+` if saving issues appear.
- GTmetrix check.
- Query Monitor check.
- Real mobile test.
- Layer Navigator structure is clean.

# BeTheme Cinematic Hero Performance Checklist

## Asset Rules

- Use WebP for images and sprite sheets.
- Use a CDN for large background media.
- Keep sprite sheets as small as practical.
- Avoid 4K assets unless truly necessary.
- Compress before uploading to WordPress.

## Motion Rules

- Use 2-4 layers max.
- Avoid multiple heavy scroll listeners.
- Use `requestAnimationFrame` for scroll-driven effects.
- Use passive scroll listeners.
- Disable complex effects on mobile when needed.

## BeTheme / WordPress Rules

- Increase `max_input_vars` to `10000+` for large BeBuilder pages.
- Disable unused BeTheme features.
- Limit plugins.
- Enable caching.
- Test after adding each major visual effect.

## Testing Stack

- GTmetrix.
- Query Monitor.
- Chrome DevTools Performance tab.
- Lighthouse.
- Real phone on cellular connection.

## Red Flags

- Page builder refuses to save.
- Hero stutters while scrolling.
- Mobile hero loads blank or late.
- Background sequence uses dozens of uncompressed JPGs.
- Text is part of the image instead of editable foreground content.

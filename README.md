# Memories Invitation Template

This first iteration is a reusable one-page invitation website made for weddings, engagements, birthdays, Valentine's Day pages, and similar special occasions.

Open `index.html` in a browser to preview it.

## Where To Edit

All of the client-facing content lives in `site-config.js`.

- Change the main couple or celebrant names in `event.coupleNames`.
- Change the main title in `event.heroTitle`.
- Change the event type label in `event.invitationLabel`.
- Change the full date and time in `event.dateTime`.
- Change the venue name, address, description, and map link in:
  `event.venueName`, `event.venueAddress`, `event.venueDescription`, `event.mapsUrl`.
- Change all editable text blocks in the `copy` object.
- Change the timeline cards in the `schedule` array.
- Change the RSVP deadline and endpoint in the `rsvp` object.

## One-Place Name Editing

The template is wired so the names across the site come from one main field:

- `event.coupleNames`

Example:

```js
coupleNames: "Adam Hassan & Farah El Said"
```

The template automatically derives the short display version like `Adam & Farah` for other sections.

## Colors

Edit the palette in `theme.colors` inside `site-config.js`.

Main keys:

- `background`
- `backgroundAlt`
- `surface`
- `surfaceStrong`
- `ink`
- `inkSoft`
- `accent`
- `accentDeep`
- `accentSoft`
- `line`
- `shadow`

These values are mapped into CSS variables automatically by `script.js`, so you usually do not need to edit `styles.css` just to change colors.

## Fonts

Edit the font assignments in `theme.fonts` inside `site-config.js`.

- `heading`
- `body`
- `accent`

The current template loads these font families in `index.html`:

- `Fraunces`
- `Cormorant Garamond`
- `Petit Formal Script`

If you want a completely different web font, update the Google Fonts `<link>` in `index.html` and then point the matching font name in `theme.fonts`.

## Images

Image paths are also controlled from `site-config.js`.

- `media.partnerOnePhoto`
- `media.partnerTwoPhoto`
- `media.venuePhoto`
- `media.memoryGallery`

Current placeholder assets live in:

- `assets/images/portrait-one.svg`
- `assets/images/portrait-two.svg`
- `assets/images/venue-placeholder.svg`
- `assets/images/memory-one.svg`
- `assets/images/memory-two.svg`
- `assets/images/memory-three.svg`

You can replace those SVG files with real `.jpg`, `.png`, or `.webp` files and then update the file paths in `site-config.js`.

## Audio

To add the song or voice note in the message section:

1. Put your audio file inside `assets/audio/`
2. Set `media.audioSrc` in `site-config.js`

Example:

```js
audioSrc: "assets/audio/our-song.mp3"
```

## RSVP Form

The modal form already works visually.

- If `rsvp.endpoint` is empty, submissions are saved only in the browser `localStorage` for preview/demo purposes.
- If you connect a real form service or backend endpoint, place its URL in `rsvp.endpoint`.

Example:

```js
endpoint: "https://your-api-or-form-service.example/rsvp"
```

## Fixed Template Design

The decorative, non-client-edit parts are mostly in:

- `styles.css`
- `index.html`
- `assets/images/decor-rings.svg`
- `assets/images/decor-bouquet.svg`

That keeps the core visual style stable while making the occasion-specific content easy to swap.

## Files Overview

- `index.html`: Page structure
- `styles.css`: Template styling and responsiveness
- `site-config.js`: Main editable content, colors, fonts, links, images
- `script.js`: Dynamic rendering, RSVP modal behavior, audio behavior

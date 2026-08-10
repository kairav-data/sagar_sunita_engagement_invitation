# Sagar & Sunita — Engagement Invitation

A single-file, offline-capable digital invitation. Open `index.html` in any browser.

## How to personalise

Everything editable lives in one `CONFIG` block near the top of the `<script>` in `index.html`.

| What | Where |
|---|---|
| Names, date/time, venue | `CONFIG.groom`, `CONFIG.bride`, `CONFIG.startISO`, `CONFIG.endISO`, `CONFIG.venueName`, `CONFIG.venueAddress` |
| RSVP WhatsApp number | `CONFIG.rsvpWhatsApp` — country code, no `+` or spaces |
| Contact numbers | `CONFIG.phones` |
| UPI / shagun ID | `CONFIG.upi` |
| **Family names** | `CONFIG.families` — **currently placeholder names, please replace** |
| Photos | `CONFIG.portraits` and `CONFIG.gallery` |
| Music | `CONFIG.music` |

### Adding photos

Create a `photos/` folder next to `index.html`, then point to the files:

```js
portraits: { groom: 'photos/sagar.jpg', bride: 'photos/sunita.jpg' },
gallery: [
  { src:'photos/1.jpg', caption:'The day we met' },
  ...
]
```

Any entry left as `''` keeps the gold-framed placeholder. Portrait crops are 3:4.

### Music

Leave `CONFIG.music` empty and the page synthesises a live tanpura drone + plucked sitar phrase
(raga Yaman) with the Web Audio API — no audio file, no bandwidth. To use your own track instead:

```js
music: 'audio/song.mp3'
```

Music starts when the guest taps the seal (a user gesture, so browsers allow it) and can be muted
from the ♪ button in the floating bar.

## Sharing it

The card is fully self-contained — the only network calls are Google Fonts and the embedded map,
and it degrades gracefully without them.

- **WhatsApp / email:** host `index.html` (plus `photos/`) anywhere static — GitHub Pages, Netlify
  Drop, Cloudflare Pages — and share the URL. The Share button and `og:` tags then work properly.
- **Offline:** the file also works straight from disk, but `Copy Link` will copy a `file://` path.

## Features

Cinematic seal-opening intro · falling lotus petals · Ganesh invocation & shloka · couple intro ·
live countdown · order of the day · venue with directions + embedded map · photo gallery with
lightbox · family details · gift/shagun note with copyable UPI · RSVP that composes a formatted
WhatsApp message · Add to Calendar (.ics download + Google Calendar) · native share sheet with
WhatsApp/email/SMS/copy fallback · full reduced-motion and no-JS fallbacks.

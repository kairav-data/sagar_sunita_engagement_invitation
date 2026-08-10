# Sagar & Sunita — Engagement Invitation

A single-file digital invitation. Open `index.html` in any browser, or host it anywhere static.

## How to personalise

Everything editable lives in one `CONFIG` block near the top of the `<script>` in `index.html`.

| What | Where |
|---|---|
| Names | `CONFIG.groom`, `CONFIG.bride` |
| Date & time | `CONFIG.startISO`, `CONFIG.endISO` (IST) |
| Venue | `CONFIG.venueName`, `CONFIG.venueAddress` |
| RSVP WhatsApp number | `CONFIG.rsvpWhatsApp` — country code, no `+` or spaces |
| Contact numbers | `CONFIG.phones` |
| Ganesh painting | `CONFIG.ganeshImage` |
| Music | `CONFIG.music` |

Longer prose — the personal invitation letter, the couple bios and the order of the day — is
written directly in the HTML and is easy to find by searching for the heading text.

## Sections

Opening screen → Ganesh invocation & shloka → personal invitation → the couple →
countdown → order of the day → venue & directions → RSVP → share.

## Music

Leave `CONFIG.music` empty and the page synthesises a live tanpura drone and plucked sitar
phrase (raga Yaman) with the Web Audio API — no audio file, no bandwidth. To use your own
track instead:

```js
music: 'audio/song.mp3'
```

Music starts when the guest taps the seal (a user gesture, so browsers allow it) and can be
muted from the ♪ button in the floating bar.

## The Ganesh image

`CONFIG.ganeshImage` points at `Lord_Ganesha__India-removebg-preview.png`, a transparent
cutout shown floating on the ivory paper with a rotating gold mandala behind it. If the file
is missing or renamed, the page silently falls back to a gold line-art crest — it will never
show a broken image.

## Hosting

Currently deployed on Vercel. Any static host works — the only external requests are Google
Fonts and the embedded map, and the page degrades gracefully without either.

Sharing only works properly once hosted: on a `file://` path there is no link to send, and the
share sheet says so rather than handing out a dead local path.

## Accessibility & fallbacks

Respects `prefers-reduced-motion`, works without JavaScript (the opening screen is skipped),
keyboard navigable throughout, and every icon scales correctly at any size.

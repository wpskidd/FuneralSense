# Obituary Resource Page — Deploy Notes

The public home for two free, ungated obituary-writing resources:

- the Obituary AI Interviewer Prompt in `index.html`;
- the traditional `Obituary-Instructions.pdf` for people who prefer paper or a regular word processor.

Deployment status checked 2026-10-05: **the page and PDF URLs both return GitHub Pages 404**. These files are staged locally; do not promise either link until deployment and functional tests pass. See `../../RAW/2026-10-05-launch-verification.md`.

Intended public home: `https://wpskidd.github.io/funeral-sense/obituary/`  
Host: GitHub Pages in `wpskidd/wpskidd.github.io` (D-037).  
Access policy: free and ungated (D-031).

## Deployment path

Publish both files to this directory on the `main` branch:

`funeral-sense/obituary/`

The page uses only relative links, so the printable opens at:

`https://wpskidd.github.io/funeral-sense/obituary/Obituary-Instructions.pdf`

## Video links still to add

Search `index.html` for `REPLACE-`:

| Placeholder | Replace with |
|---|---|
| `REPLACE-WITH-OB-001-URL` | The YouTube URL for OB-001, once published |
| `REPLACE-WITH-OB-002-URL` | The YouTube URL for OB-002, once published |

Both video cards remain in a non-clickable “coming soon” state until the videos are public. When a video goes live, delete its `<div class="soon">` block and un-comment the corresponding `<a class="card">` block.

## Rebuild the printable

The supplied 2011 document is preserved at `RAW/2011-obituary-instructions-source.pdf`. The current printable is generated from:

`scripts/generate_obituary_instructions_pdf.py`

Run it with the bundled workspace Python runtime, then render both pages and inspect them before deployment. The rebuilt PDF is deliberately privacy-aware, location-neutral, low-ink, and styled to the Funeral Sense channel.

## Test before a video links here

- [ ] Copy button works on Bill's phone in Safari and Chrome.
- [ ] Page remains readable with JavaScript disabled; the full prompt is selectable.
- [ ] Printable PDF opens and downloads on phone and desktop.
- [ ] Pasted prompt runs correctly in at least two AI assistants.
- [ ] Run `topics/01_obituaries/testing/AI-INTERVIEWER-FICTIONAL-TEST-SET.md`; record scores and resolve every critical failure.
- [ ] Page is readable one-handed on a phone at default text size.
- [ ] Dark mode and print preview remain clean.

## Deliberate constraints — preserve these

- **No tracking of any kind.** No analytics, pixels, cookies, or CDN assets.
- **No email capture, account, install, or sign-in** (D-031).
- **No affiliate link or consultation CTA.** This is at-need obituary help.
- **Works without JavaScript.** Someone under time pressure on an older phone can still use both resources.
- **No funeral imagery and no AI/robot imagery.**

## Keeping the prompt in sync

The canonical prompt is `outputs/OBITUARY-AI-INTERVIEWER-PROMPT.md`. The text in its fenced `text` block and the `<pre>` block in `index.html` must stay character-for-character identical.

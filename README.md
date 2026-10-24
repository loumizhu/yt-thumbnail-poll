# YouTube Thumbnail Polling System (Discord Webhook)

A YouTube-home-feed lookalike for split-testing thumbnails with people you know before publishing. Sister tool of [`../title_tester_poll`](../title_tester_poll/README.md).

Every card shows the **same title, channel, views and duration**. Only the thumbnail changes, so a vote measures the thumbnail and nothing else. The order is shuffled for each visitor.

---

## What you get in Discord

Each click sends an embed with:
- The thumbnail picked (ID + label, plus the image itself once the page is hosted on http/https)
- Voter name (from `?voter=Name`)
- Decision speed (seconds from feed load to click)
- Grid position it was in, and the full order shown (to spot position bias)
- Device (mobile / desktop)

After voting, the person can optionally type **why** they clicked. That comes through as a second Discord message.

Uses the same Discord webhook as the title poll (base64 in `index.html`). Override per link with `?wh=<url-or-base64>`.

---

## Editing the test

All config sits at the top of the `<script>` in `index.html`:

```javascript
const VIDEO_TITLE  = "They Made Millions as Children. Their Parents Stole Every Cent.";
const CHANNEL_NAME = "Hollywood Echoes";
const VIEWS = "184K views", AGE = "3 days ago", DURATION = "23:14";

const THUMBNAILS = [
  { id: "V15", label: "...", src: "thumbnails/Version_15_....webp" },
  ...
];
```

To test new thumbnails, drop 1280×720 WebP/JPG files into `thumbnails/` and update the `THUMBNAILS` list.

---

## Run / deploy

- **Local:** `python -m http.server 8765` in this folder → open `http://127.0.0.1:8765/?voter=Me`.
- **GitHub Pages:** push this folder (with `thumbnails/`) to a repo → Settings → Pages → Deploy from `main` / root.
  Share `https://<user>.github.io/<repo>/?voter=Mike`.

Mobile layout follows the YouTube app (full-width cards, no sidebar). Most friends will open the link on a phone.

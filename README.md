# YouTube Thumbnail Polling System (Discord Webhook)

A YouTube-home-feed lookalike for split-testing thumbnails with people you know before publishing. Sister tool of [`../title_tester_poll`](../title_tester_poll/README.md).

Every card shows the **same title, channel, views and duration**. Only the thumbnail changes, so a vote measures the thumbnail and nothing else. The order is shuffled randomly for each visitor.

---

## Active Test: Child Stars Who Became Monsters Behind the Facade

- **Video Title:** The Child Stars Who Became Monsters Behind the Facade
- **Channel Name:** Hollywood Echoes
- **Duration Badge:** 20:17
- **Live URLs:**
  - `https://loumizhu.github.io/yt-thumbnail-poll/`
  - `https://loumizhu.github.io/yt-thumbnail-poll/child-stars/`
  - Share link format: `https://loumizhu.github.io/yt-thumbnail-poll/?voter=YourName`

### Candidate Thumbnails Under Test:
1. **`V01`** — *De Niro Warned Him · Lillo Brancato Thug* (`Version_01_DeNiro_Warned_Him_Brancato_Thug`)
2. **`V04`** — *Disney Dumped Him · Bobby Driscoll Peter Pan* (`Version_04_Bobby_Driscoll_Disney_Dumped_Him`)
3. **`V07`** — *Death Row · Skylar Deleon Power Rangers* (`Version_07_Skylar_Deleon_Death_Row`)
4. **`V05`** — *Four Pillars Behind The Facade · Multi-Cast* (`Version_05_Four_Pillars_Behind_The_Facade`)

---

## What you get in Discord

Each click sends an embed with:
- The thumbnail picked (ID + label, plus the full image preview rendered in Discord)
- Voter name (from `?voter=Name` or `?name=Name`)
- Decision speed (seconds from feed load to click)
- Grid position it was in, and the full presentation sequence (to spot position bias)
- Device (Mobile / Desktop)

After voting, the voter can optionally submit **why** they clicked. That comes through as a second Discord message with their feedback.

Uses the channel's Discord webhook (base64 encoded in `index.html`). Can be overridden per link with `?wh=<url-or-base64>`.

---

## Archived Tests

- [`video-02/`](./video-02/): *They Made Millions as Children. Their Parents Stole Every Cent.* (`https://loumizhu.github.io/yt-thumbnail-poll/video-02/`)

# Sports Feed — Sports Streaming Calendar

A single-file web app for tracking where to watch every major sport. No installs, no dependencies — just open `index.html` in any browser.

**Live site:** https://griffinbrettschneider.github.io/sports-feed

---

## What It Does

**3 pages:**

1. **Seasons** — Year-at-a-glance 12-month timeline bar showing when each sport is in season, plus season cards with streaming platforms and on/off season status
2. **Calendar** — Every game/event organized by sport. Toggle between 2025-26 (current) and 2024-25 (archive). Filter by sport, platform, month, or search
3. **By Platform** — Pick a streaming service (Netflix, Peacock, ESPN Unlimited, etc.) and see every sport and event available on it

---

## Sports Covered

| Sport | Coverage |
|---|---|
| NFL | Every TNF/SNF/MNF game, Thanksgiving, Christmas, playoffs, Super Bowl |
| NBA | Every Opening Night, NBA Cup, Christmas, All-Star, Play-In, Playoffs, Finals |
| MLB | Opening Day, Friday Night Baseball, Saturday Leadoff, Sunday Night Baseball, postseason |
| Premier League | All 38 gameweeks |
| UFC | All numbered PPVs |
| WWE | All PLEs (Premium Live Events) |
| NHL | Key games, Winter Classic, Stadium Series, Playoffs, Cup Final |
| MLS | Season + Cup Final |
| Champions League | League phase through Final |
| Europa League | Through Final |
| La Liga | Season + El Clásico |
| Bundesliga | Season + Der Klassiker |
| Serie A | Season bookends |
| Men's/Women's CBB | March Madness through Championship |
| Winter Olympics | 2026 Milan-Cortina (Feb 6–22, 2026) |

---

## Streaming Platforms Tracked

Amazon Prime Video · Apple TV · ESPN Unlimited · FOX One · Max · Netflix · Paramount+ · Peacock · YouTube TV (NFL Sunday Ticket)

---

## Seasons

- **2025-26** — current default view
- **2024-25** — full archive accessible via Season dropdown on the Calendar page

---

## Tech

- Pure HTML/CSS/JavaScript — zero dependencies, zero build step
- Single file: `index.html`
- Dark mode toggle built in
- Fully responsive (mobile-friendly)

---

## How to Update

1. Edit `index.html` locally
2. Commit and push:
```bash
cd /Users/griffinbrettschneider/Documents/GitHub/sports-feed
git add index.html
git commit -m "your update message"
git push
```
GitHub Pages auto-deploys within ~1 minute.

---

## Development Notes

- `SEASONS` array → drives timeline bars and season cards (Page 1)
- `EVENTS` array → drives calendar and platform lookup (Pages 2 & 3)
- `ARCHIVE_CUTOFF = '2025-08-01'` — events before this date = 2024-25 archive
- `conf: false` on any event/platform adds a ⚠ "verify" warning flag
- Sport colors defined in `SC` object at top of script
- `renderTimeline()` — 12-month cyclical view, deduped to one row per sport
- `renderSeasons()` — deduped to most recent season per sport

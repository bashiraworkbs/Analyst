# ⚔️ Bashira — Brawl Stars Analytics Dashboard

A single-file HTML analytics dashboard for competitive Brawl Stars, powered by live Google Sheets data.

![HTML](https://img.shields.io/badge/HTML-Single%20File-orange) ![JS](https://img.shields.io/badge/JavaScript-Vanilla-yellow) ![Chart.js](https://img.shields.io/badge/Chart.js-4.4-blue)

## Features

- **📡 Live Google Sheets sync** — Fetches match data automatically via JSONP (no server needed)
- **📊 Overview** — Win rate, best brawler/map/team/player, WR timeline, WR by mode
- **🏆 Meta Rankings** — Brawler tier list sorted by pick rate with best map per brawler
- **🎯 Brawler Stats** — Detailed per-brawler view: WR by mode/map, synergies, counters, best/worst matchups
- **🛡️ Team Stats** — Team WR (set-based), roster, form, scrim history, mode/map breakdown
- **🔥 Head-to-Head** — Heatmap of brawler vs brawler win rates
- **📋 Match Log** — Sortable match history with streaks
- **⚡ Draft Help** — Counter pick suggestions + full draft simulator with bot AI
- **🗺️ Map Stats** — Per-map analytics with brawler images from Brawlify CDN
- **📥 Import** — Manual CSV/JSON import support
- **📅 Date Filters** — 7J / 14J / 30J / 60J / 90J / ALL — works across every page

## Setup

### 1. Prepare your Google Sheet

Your sheet needs these columns (first row = headers):

| Column | Description |
|--------|-------------|
| `date` | Match date |
| `mode` | Game mode (Gem Grab, Brawl Ball, etc.) |
| `map` | Map name |
| `result_team1` | "victory" or "defeat" |
| `team1_name` | Your team name |
| `team2_name` | Enemy team name |
| `team1_player1_brawler` | Brawler picked by player 1 |
| `team1_player1_name` | Player 1 name |
| ... | (same pattern for players 2-3 and team2) |
| `set_score` | Set score like "2-1" |
| `set_id` | Unique set identifier |
| `set_game_number` | Game number within the set |
| `average_tier_team1` | Team tier (S/A/B/C) |
| `average_region_team1` | Region (EMEA/NORTHAMERICA/etc.) |

### 2. Share your sheet

Go to **Share → General access → Anyone with the link → Viewer**

### 3. Update the sheet ID

In `index.html`, find this line and replace with your sheet ID:

```js
var GS_SHEET_ID = "YOUR_SHEET_ID_HERE";
```

The sheet ID is the long string in your Google Sheets URL:
```
https://docs.google.com/spreadsheets/d/THIS_IS_YOUR_SHEET_ID/edit
```

### 4. Open locally

Just open `index.html` in your browser. No server needed.

### 5. Host on GitHub Pages (optional)

1. Push to a GitHub repo
2. Go to **Settings → Pages → Source: main branch**
3. Your dashboard will be live at `https://yourusername.github.io/repo-name/`

## Tech

- **Zero dependencies server-side** — everything runs client-side
- **Chart.js** for graphs
- **Brawlify CDN** for brawler/map images
- **Google Visualization API** (JSONP) for fetching sheet data — bypasses CORS

## License

MIT

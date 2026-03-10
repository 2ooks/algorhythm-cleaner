# 🎵 Algorhythm Cleaner

**Clean your Spotify algorithm of kids' music — in one click.** If you're a parent whose Spotify recommendations have been taken over by Cocomelon, Frozen, and Baby Shark, this tool scans your playlists, liked songs, and recent history, identifies kids' music using ~120 artist and track name patterns, and creates a private playlist you can exclude from your Taste Profile — instantly fixing your recommendations.

## Prerequisites

1. Go to [developer.spotify.com/dashboard](https://developer.spotify.com/dashboard)
2. Click **Create App**
3. Set the **Redirect URI** to your GitHub Pages URL (e.g. `https://yourusername.github.io/algorhythm-cleaner/`)
4. Select **Web API** under APIs used
5. Copy the **Client ID**

## Setup

If you're hosting this yourself via GitHub Pages:

1. Fork this repo
2. Enable GitHub Pages in **Settings → Pages** (deploy from main branch, root)
3. In your Spotify Developer App, add your Pages URL as a Redirect URI
4. Visit your Pages URL and paste in your Client ID

## Usage

1. **Paste your Client ID** and click Connect
2. **Authorize** the app when Spotify prompts you
3. **Scan** — the app checks all your playlists, liked songs, and recently played tracks
4. **Review** — uncheck any false positives (songs matched by pattern that you actually want)
5. **Create Playlist** — generates a private playlist called "Kids Music — Exclude Me"
6. **Exclude from Taste Profile** — open the playlist in Spotify, tap ⋯ → "Exclude from your Taste Profile"

Your recommendations will start improving within a few days.

## Adding More Patterns

The matching patterns are defined at the top of `index.html` in three arrays:

- **`KIDS_ARTISTS`** — artist name substrings (e.g. `'cocomelon'`, `'kidz bop'`)
- **`KIDS_TRACK_PATTERNS`** — track name substrings (e.g. `'baby shark'`, `'let it go'`)
- **`DISNEY_ALBUM_PATTERNS`** — album name keywords that trigger track-level matching

All matching is case-insensitive. To add a new pattern, just append a string to the relevant array.

## Privacy

- **No backend** — runs entirely in your browser
- **No data stored** — no localStorage, no cookies, no analytics
- **Session only** — your Client ID and PKCE verifier are stored in `sessionStorage` (cleared when you close the tab)
- **Open source** — read the code yourself, it's one file

## License

[MIT](LICENSE)

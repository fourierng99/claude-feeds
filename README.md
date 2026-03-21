# Claude Feeds — RSS Reader

A fast, modern, single-file RSS feed reader. No build tools, no dependencies, no server required — just open `index.html` in a browser.

## Features

- **8 pre-configured news sources** across world news, tech, science, and more
- **Instant search/filter** — type to filter articles by keyword in real time (Ctrl+K to focus)
- **Dark / light theme** — toggle in the sidebar footer, preference is saved
- **Skeleton loading** — placeholder cards while content loads
- **5-minute cache** — revisiting a source won't re-fetch until the cache expires
- **Refresh button** — force-reload any feed at any time
- **Responsive** — works on mobile, tablet, and desktop
- **Keyboard shortcuts** — `Ctrl+K` focus search, `Escape` clear search or close mobile sidebar

## Sources

| Name | Category |
|---|---|
| BBC News | World |
| Reuters | World |
| The Guardian | World |
| Al Jazeera | World |
| TechCrunch | Tech |
| Hacker News | Tech |
| NASA | Science |
| NPR News | News |

## How to Use

1. Open `index.html` in any modern browser (Chrome, Firefox, Edge, Safari).
2. Click a source in the left sidebar to load its feed. BBC News loads by default.
3. Use the search box (top right) to filter articles by keyword.
4. Click **Read article** on any card to open the full article in a new tab.
5. Click the refresh button (circular arrow) or press the same source button again to reload.
6. Toggle dark mode with the switch at the bottom of the sidebar.

## Technical Notes

- Uses the [rss2json API](https://rss2json.com/) as a CORS proxy to convert RSS/Atom feeds to JSON.
- No API key is needed for basic usage (free tier: 10,000 requests/day).
- All data fetching is client-side; no backend or server is involved.
- The app is a single self-contained HTML file — CSS and JavaScript are embedded inline.

## Customising Sources

To add or change sources, edit the `SOURCES` array at the top of the `<script>` block in `index.html`:

```js
const SOURCES = [
  {
    id: 'myblog',          // unique identifier
    name: 'My Blog',       // display name
    category: 'Personal',  // shown in sidebar
    url: 'https://example.com/rss.xml',  // RSS feed URL
    iconBg: '#e74c3c',     // icon background colour (hex)
    iconText: 'MB',        // short text for the icon (2-4 chars)
  },
  // ...
];
```

Change `DEFAULT_SOURCE` to the `id` of whichever source you want to load on startup.

## Browser Support

Works in all evergreen browsers (Chrome 80+, Firefox 75+, Edge 80+, Safari 13+).

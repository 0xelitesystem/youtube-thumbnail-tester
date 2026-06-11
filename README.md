# youtube-thumbnail-tester

Preview a thumbnail and title across the YouTube placements that actually matter: search results, home feed, mobile feed, sidebar, notifications, channel page. Light and dark side-by-side. Browser only.

**Live demo:** https://0xelitesystem.github.io/youtube-thumbnail-tester/

## Use

Open [`index.html`](./index.html). Upload a thumbnail (1280x720 recommended). Type your title and channel name. The page renders six placement previews in both light and dark themes.

The tool also runs a few automated checks: title length, aspect ratio, resolution, all-caps, exclamation count.

## Why

Thumbnails get evaluated at a dozen different sizes. A thumb that pops at 1280x720 in your editor can be unreadable at 88px in a notification, or invisible against the dark sidebar background. Most creators only test one preview, then publish and find out the hard way.

This shows you all the relevant placements at once, in both themes, before you publish.

## What it tests

- Search result card (desktop, ~240px thumbnail)
- Home feed card (desktop)
- Mobile feed card (full width)
- Sidebar / Up Next card (~168px)
- Notification / End screen (88px - smallest readable size)
- Channel page grid

Each placement renders in both light and dark themes since YouTube users are split roughly half-and-half.

## What it doesn't do

- Doesn't connect to YouTube. No API, no upload, no analytics.
- Doesn't predict CTR. No tool can do that reliably.
- Doesn't generate thumbnails. Bring your own.
- Doesn't show the thumbnail behind the play button overlay (a real placement). Approximate visual only.
- Doesn't simulate Shorts placement. Shorts have their own format requirements.

## Privacy

The thumbnail file is read with FileReader and rendered in your browser. No upload. No network requests. Verify by opening DevTools and watching the network tab; nothing leaves the page.

## Running locally

```
git clone https://github.com/0xelitesystem/youtube-thumbnail-tester
cd youtube-thumbnail-tester
```

Open `index.html` in a browser. Or:

```
python -m http.server 8000
```

Then visit `http://localhost:8000`.

## Contribute

PRs welcome:

- Additional placements (Shorts feed, search-with-filter, watch page below player)
- Better automated checks (text contrast against typical YouTube backgrounds, face detection for thumbnail "rule of thirds")
- Localization (title length warnings vary by language)

Don't add: analytics, external scripts, npm dependencies. Single file by design.

## Build

No build. Single HTML file.

## License

MIT.

## Related

- [youtube-title-ab-tester](https://github.com/0xelitesystem/youtube-title-ab-tester) - compare title variants side-by-side
- [youtube-chapter-marker-builder](https://github.com/0xelitesystem/youtube-chapter-marker-builder) - validate and format chapter timestamps
- [youtube-creator-checklist](https://github.com/0xelitesystem/youtube-creator-checklist) - pre-publish checklists

# Lost Hiker Coffee Roasters

Website for Lost Hiker Coffee Roasters, Sayward, BC.

Built with [Astro](https://astro.build) · Hosted on [Netlify](https://netlify.com)

---

## For Jordan & Leah: How to update the website

You only ever need to edit two files to keep the site current. Everything else stays the same.

### Updating coffees → `src/data/roasts.json`

Each coffee is one entry in the list. Here's what each field means:

- `name` — the coffee name (e.g. "Alpine")
- `roast` — the roast description shown on the card (e.g. "Light Roast")
- `roastLevel` — a number from 1–5 controlling the dot indicator (1 = lightest, 5 = darkest)
- `origin` — the country or region (e.g. "Colombia")
- `description` — the tasting notes / description paragraph
- `image` — the filename of the coffee's image (must be uploaded to `public/images/`)
- `available` — `true` if in stock, `false` if not (shows "Currently unavailable")

To **add** a coffee: copy an existing entry, paste it at the end of the list (before the `]`), and edit the fields. Don't forget the comma between entries.

To **remove** a coffee: delete the whole `{ ... }` block for that coffee, including the comma before it.

To **mark as out of stock**: change `"available": true` to `"available": false`.

### Updating sourcing → `src/data/origins.json`

Each origin (farm/region) is one entry. Fields:

- `country` / `region` / `farm` — displayed as the origin name and subtitle
- `image` — filename of the farm/region photo
- `description` — overview of the growing region
- `farmStory` — the specific farm or producer story
- `procuredVia` / `procuredViaUrl` — importer name and link
- `roastsUsedIn` — list of coffee names that use this origin (e.g. `["Alpine", "Field of Dreams"]`)
- `altitude` / `process` / `variety` — shown in the detail panel

### How to edit on GitHub

1. Go to [github.com](https://github.com) and open the `lost-hiker-coffee` repository
2. Navigate to `src/data/roasts.json` (or `origins.json`)
3. Click the pencil icon (Edit this file)
4. Make your changes
5. Click **Commit changes** at the bottom — Netlify will automatically rebuild and publish the site within ~2 minutes

### Adding a new photo

Upload the image file to `public/images/` in the repository (drag and drop works in GitHub), then reference it as `/images/yourfilename.jpg` in the JSON file.

---

## Developer notes

```bash
# Install dependencies
npm install

# Start local dev server
npm run dev

# Build for production
npm run build
```

Netlify builds automatically on every push to `main`. Build command: `npm run build`, publish directory: `dist`.

The contact form uses Netlify Forms (free tier: 100 submissions/month). No backend needed.

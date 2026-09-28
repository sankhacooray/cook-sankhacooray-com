# cook

Sankha Cooray's simple food blog — cooking experiments: healthy, tasty meals
built from basic building blocks that are easy to prep.

Deployed at **[cook.sankhacooray.com](https://cook.sankhacooray.com)** via a
Cloudflare Worker (static assets only).

## Files

| Path | Purpose |
|------|---------|
| `public/index.html` | Single-file site, CSS + render JS inline |
| `public/data/posts.json` | Cooking experiments (`{version, items: [...]}`) |
| `public/data/places.json` | "Places I recommend" list (empty for now) |
| `public/images/` | Post images (`dummy-*.svg` are placeholders) |
| `wrangler.toml` | Worker config + `cook.sankhacooray.com` custom domain |

## Content format

`posts.json` item:

```json
{ "id": "slug", "date": "YYYY-MM-DD", "title": "...", "summary": "...",
  "image": "images/x.jpg", "prepMinutes": 15, "tags": ["..."], "dummy": false }
```

Any item with `"dummy": true` gets a "dummy image" tag, and the page shows a
"real food coming soon" notice. Delete the sample items once real posts exist.

`places.json` item: `{ "name": "...", "area": "...", "why": "..." }`.

A future feed service only needs to write these two JSON files (or the page
can be pointed at an API returning the same shape).

## Deploy

```
CLOUDFLARE_ACCOUNT_ID=9a1da48a0f61e7cebcba39517856d87e npx wrangler deploy
```

The current API tokens have Workers permissions but not Pages, which is why this
is a Worker rather than a Pages project.

## Next steps

- [ ] Replace sample posts + dummy images with real food
- [ ] Add recommended places
- [ ] Connect the image/article feed service
- [ ] Raster icons + OG image; add `cook` to the shared footer network list

# The Studio Archive — public view-only edition

A static palette and catalog from SkyPi Studio’s art practice. Artwork entries describe the work and display color palettes; this edition does not include the original artwork photographs. The supply catalog presents materials and colors for browsing. It is separate from Portfolio’s private archive.

[Open the public edition on GitHub Pages](https://skypie99.github.io/studio-archive/).

## Source and snapshot

The page, catalog data, styles, and browser behavior are contained in [index.html](index.html). This README describes the public source inspected on September 26, 2026 at commit [`831c0aa53574aa539d06caac5adeae0bca966c0e`](https://github.com/Skypie99/studio-archive/tree/831c0aa53574aa539d06caac5adeae0bca966c0e). That is a dated source observation, not a claim about when the archive was first published or when the underlying artworks were made.

No build tools, account, or backend are required to inspect this static edition. From the repository directory, serve it locally with Python 3:

```bash
python3 -m http.server 8000 --bind 127.0.0.1
```

Then open [the local preview](http://127.0.0.1:8000/). Stop the server with Ctrl-C.

## Public URL status

The GitHub Pages URL above returned HTTP 200 on September 26, 2026 with certificate verification enabled. The custom archive domain advertised in existing repository metadata failed TLS hostname verification on that date. Use the Pages link while the owner resolves the domain and chooses the canonical URL. Hosting, DNS, search metadata, and repository description are unchanged by this documentation patch.

## Content and reuse

Viewing this public edition does not establish permission to reuse its code, artwork, palette data, text, or assets. This repository currently supplies no reuse license. Sky must decide code and creative-content rights separately; this README does not invent license terms.

# Career Launch — static pages

This repo is the source of truth for two pages on the Career Launch platform:

| File in this repo           | Live page                                         |
| --------------------------- | ------------------------------------------------- |
| `index.html` (+ root PNGs)  | **https://careerlaunch.myblueprint.ca/partners**     |
| `associations/index.html`   | **https://careerlaunch.myblueprint.ca/associations** |

## How it works

1. Update the page's `index.html` (and any images next to it) in this repo —
   uploading through the GitHub website works fine.
2. On every push, a GitHub Action automatically tells the Career Launch
   platform to pull the new content and deploy it.
3. The live page updates about 2 minutes later.

There is nothing else to do. No builds, no deploys, no other repos to touch.
If the automatic trigger is ever unavailable, the platform also syncs this
repo once a day as a fallback.

A new page needs a one-time setup on the platform side (a new folder here
won't go live on its own) — ask Alasdair.

## Notes for editing

- Keep each page self-contained: inline CSS/JS and embed images as data URIs.
  Relative image references like `src="logo.png"` also work — the sync
  rewrites them to the right path. Put a page's images in the same folder as
  its `index.html`.
- Keep the `noindex` meta tag and canonical link at the top of each page. They
  keep the GitHub Pages copy out of search; the platform strips the `noindex`
  so the careerlaunch.myblueprint.ca copy is the one that gets indexed.
- External scripts/styles/fonts must be allowed by the platform's Content
  Security Policy. Currently allowed: Google Fonts and Adobe Fonts (Typekit).
  If you add anything loaded from a new domain and it doesn't show up on the
  live page, that's usually why — flag it to Alasdair. (Plain links to other
  sites, like the booking link, are fine.)

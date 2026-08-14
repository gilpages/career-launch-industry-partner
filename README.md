# Career Launch — Industry Partners page

This repo is the source of truth for the partners page at
**https://careerlaunch.myblueprint.ca/partners**.

## How it works

1. Update `index.html` (and any images) in this repo — uploading through the
   GitHub website works fine.
2. On every push, a GitHub Action automatically tells the Career Launch
   platform to pull the new content and deploy it.
3. The live page updates about 2 minutes later.

There is nothing else to do. No builds, no deploys, no other repos to touch.
If the automatic trigger is ever unavailable, the platform also syncs this
repo once a day as a fallback.

## Notes for editing

- Keep the page self-contained: inline CSS/JS and embed images as data URIs
  (the current page already does this). Relative image references like
  `src="logo.png"` also work — the sync rewrites them to the right path.
- External scripts/styles/fonts must be allowed by the platform's Content
  Security Policy. Currently allowed: Google Fonts and Adobe Fonts (Typekit).
  If you add anything loaded from a new domain and it doesn't show up on the
  live page, that's usually why — flag it to Alasdair.

# HWC public/legal website

Static site (no build step) for HWC's public/legal pages: About, Privacy, Terms,
Contact, plus `/app-ads.txt` (AdMob seller authorization for the HWC app).
Deployed to Cloudflare Pages under the HWC Cloudflare account.

Live: https://hwc-wellness.pages.dev

> **Not** `hwc.pages.dev` -- that subdomain belongs to an unrelated third party
> (verified live); this project's Cloudflare Pages name is `hwc-wellness`.

## app-ads.txt

`/app-ads.txt` must contain exactly the AdMob seller line (no extra whitespace
or HTML) and be served as plain text from the site root:

```
google.com, pub-1918372113970166, DIRECT, f08c47fec0942fa0
```

Note Cloudflare Pages serves the home page (HTTP 200, `text/html`) for unknown
paths, so a bare "200" is not proof the file exists -- check the content type
and body, e.g.:

```
curl -sI https://hwc-wellness.pages.dev/app-ads.txt   # content-type: text/plain
curl -s  https://hwc-wellness.pages.dev/app-ads.txt   # the seller line
```

## Deploy

```
npx wrangler pages deploy . --project-name=hwc-wellness
```

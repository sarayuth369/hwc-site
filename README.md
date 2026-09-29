# HWC public/legal website

Static site (no build step) for HWC's public/legal pages: About, Privacy, Terms,
Contact. Deployed to Cloudflare Pages under the HWC Cloudflare account.

Live: https://hwc.pages.dev

## Deploy

```
npx wrangler pages deploy . --project-name=hwc-site --branch=main
```

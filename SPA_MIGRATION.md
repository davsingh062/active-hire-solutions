# Single-page application migration

Target domain: https://activehiresolutions.com/

## Reference application
The supplied ZIP is a React + TypeScript + TanStack Start application. Its home route renders the site's sections as a single long page with anchor navigation.

## Migration checklist
- [ ] Integrate the supplied React application at the repository root and configure Cloudflare Pages to build and serve its generated output.
- [ ] Preserve the current live deployment until the preview deployment passes smoke tests.
- [ ] Keep the public URL at https://activehiresolutions.com/ and map navigation to in-page anchors.
- [ ] Confirm direct visits to the root and all anchor links work on Cloudflare Pages.
- [ ] Replace the sitemap with the canonical SPA URL only after the SPA is deployed.
- [ ] Update robots.txt to reference the production sitemap.
- [ ] In Google Search Console, inspect the canonical home URL, submit the new sitemap, and monitor indexing. Remove old URLs only after verifying redirects or deciding they should return 404/410.
- [ ] Verify title, description, canonical URL, Open Graph tags, mobile layout, contact links, and accessibility.
- [ ] Run build, lint, and tests before merging.

## SEO note
A single-page site should generally have one canonical page URL in its XML sitemap. Section anchors such as /#about are navigation fragments, not separate indexable pages. Do not remove old sitemap URLs from production until the SPA is actually deployed, because the current live website still has separate HTML routes.

## Deployment safety
This work belongs on the spa-migration branch. Do not merge it into main or switch the Cloudflare production build until the app is integrated and validated.

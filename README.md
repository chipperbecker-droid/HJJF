# Hudson, Jones, Jaywork & Fisher Website

This folder contains a complete static website for Hudson, Jones, Jaywork & Fisher, LLC.

## Technical Overview

This is a static HTML/CSS website. It does not require WordPress, a database, a backend server, a package install, or a build process.

The homepage is `index.html`. Shared styling is in `site.css`. Images, logos, favicons, office photos, attorney photos, and practice-area images are in the `assets` folder.

## Folder Structure

The site uses relative links, so the folder structure should remain intact.

Top-level items include:

- `index.html`
- `site.css`
- `.nojekyll`
- `assets/`
- `about/`
- `attorneys/`
- `practice-areas/`
- `contact-us/`
- additional page folders

The contents of this folder are intended to function as the website root.

## Hosting Compatibility

The site is suitable for Cloudflare Pages, GitHub Pages, Netlify, or a standard static web server.

For static hosting platforms, there is no required build output folder separate from the site root. The root of this folder is the deployable site.

GitHub Pages can host this site as-is from the repository root. Cloudflare can be used for DNS, SSL, caching, redirects, and either Cloudflare Pages hosting or proxying another static host.

This project does not include a CMS dashboard. WordPress is optional rather than required: use WordPress only if the firm needs non-technical staff to edit pages, post frequent updates, manage forms, or change SEO fields without editing files.

## Cloudflare Pages Information

Relevant Cloudflare Pages configuration details:

- Site type: Static HTML
- Build required: No
- Build command: None required
- Build output directory: Site root
- Homepage file: `index.html`

## Files To Preserve

The following should be included in the deployed site:

- All `.html` files and page folders
- `site.css`
- `assets/`
- `assets/attorneys/`
- `.nojekyll`, if using GitHub Pages

The following are not required for the live website:

- `.git/`
- `.DS_Store`

## Content Notes

The site includes:

- Homepage
- About page
- Attorney directory and attorney profile pages
- Practice area directory and individual practice area pages
- Dover and Rehoboth office pages
- Contact page
- FAQ and resources page
- Careers page
- Privacy policy
- Sitemap

External links such as Google Maps, Facebook, and official Delaware resource links are intentionally external. Practice-area images are linked to local files in the `assets` folder.

## Maintenance Notes

- Keep the HTML formatted for people to read. Each page is a standalone file, and shared visual rules belong in `site.css`.
- When page copy changes, review the matching description, Open Graph tags, Twitter tags, and JSON-LD block in that page's `<head>` so search and social previews stay accurate.
- Where an image has a WebP version, keep the `<picture>` element: the WebP `<source>` improves load time and the original `<img>` remains the fallback.
- Individual attorney email values are intentionally omitted from attorney bio pages. Use the generic firm email, `info@delawarelaw.com`, for public contact points unless attorney-specific publication preferences change.
- The Careers page should direct submissions to `info@delawarelaw.com`.
- The Real Estate practice-area image uses `assets/real-estate-closing.jpg`. The older `assets/real-estate.jpg` file is retained in the asset folder but should not be used for current Real Estate page/card imagery.
- The old external review platform link has been removed and should not be reintroduced unless the firm approves a new review workflow.
- The homepage includes client feedback/testimonials. Keep the nearby disclaimer in place, and obtain attorney advertising review before adding, removing, or changing testimonial copy.
- Christopher M. Holmon's profile references a Milford office in the biography, but the site has only Dover and Rehoboth office pages. Confirm the intended public office listing with the firm before launch.
- `redirect-map-starter.csv` is based on the 50-URL Yoast sitemap from the old site. Review every low- and medium-confidence row before implementing redirects.

## Launch Requirements

The following items require information or access outside this repository before swapping the live domain:

- Current live-site URL inventory beyond the provided 50-URL Yoast sitemap, ideally from a crawl, WordPress export, or Google Search Console.
- Final approval of `redirect-map-starter.csv`, including whether no-equivalent pages should return `410 Gone`, redirect to a related section, or be rebuilt on the new site.
- Google Analytics 4 or Google Tag Manager container ID, if the firm uses analytics.
- Google Search Console verification method or access to the existing property.
- Call tracking provider scripts or tracking numbers, if the firm uses call tracking.
- DNS/registrar or Cloudflare access, plus confirmation of existing MX/email records so email service is not disturbed.
- Attorney review of attorney roster, titles, office assignments, practice areas, testimonials, disclaimers, and legal FAQ/resource content.

Do not launch without a finalized redirect plan. Missing redirects can create 404 errors for indexed pages, backlinks, bookmarks, and old attorney or practice-area URLs.

## Redirect Map Format

Create the final redirect map before launch using this structure:

```csv
old_url,new_url,status,notes
https://www.delawarelaw.com/old-page/,https://www.delawarelaw.com/new-page/,301,Exact replacement
https://www.delawarelaw.com/old-attorney-page/,https://www.delawarelaw.com/attorneys/,301,No direct replacement
```

For Cloudflare, implement redirects with Bulk Redirects, Redirect Rules, or a Pages `_redirects` file if the final host supports it. For GitHub Pages alone, redirects generally need to be handled at Cloudflare or another edge/proxy layer.

## Tracking Notes

No analytics, tag manager, Search Console verification, call tracking, or advertising pixels are currently installed. Add the approved tracking snippets only after the firm provides the correct IDs and confirms any privacy-policy implications.

Recommended events before launch:

- Clicks on Dover and Rehoboth phone links.
- Clicks on `info@delawarelaw.com`.
- Clicks on contact-page and directions links.
- Optional outbound clicks to external resource links.

## DNS and Cutover Notes

Before cutover, coordinate with the current DNS manager or host:

- Confirm where authoritative DNS is managed.
- Preserve MX, SPF, DKIM, DMARC, and any other mail-related records.
- Decide whether the new site will be served by GitHub Pages, Cloudflare Pages, Netlify, or another static host.
- Configure SSL/HTTPS before or during cutover.
- Lower DNS TTL ahead of launch if possible.
- Keep the old host available briefly for rollback/reference.
- Run a final crawl immediately before and after DNS changes.

## Pre-Deployment Check

Before deploying changes, run a quick static QA pass:

- Confirm local `href` and `src` paths resolve.
- Search for outdated review-platform references, CGI references, and unintended individual attorney email values.
- Spot-check the homepage, attorney pages, practice-area pages, Careers page, and Contact page on desktop and mobile widths.
- Validate `sitemap.xml` and `robots.txt`.
- Validate JSON-LD/schema markup.
- Test mobile navigation and contact calls to action.
- Confirm attorney names, titles, bios, offices, and practice areas with the firm.
- Confirm Dover and Rehoboth addresses, phone numbers, fax numbers, map links, and email.
- Confirm testimonials and FAQ/resource content have attorney advertising/legal review.
- Confirm analytics, Search Console, call tracking, and redirects are installed in the final hosting environment.

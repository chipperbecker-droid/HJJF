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

External links such as Google Maps, Facebook, review links, and official Delaware resource links are intentionally external. Practice-area images are linked to local files in the `assets` folder.

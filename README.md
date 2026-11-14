# InternTrack — LinkedIn preview landing page

Public **preview-only** page for the private InternTrack student project.

- **LinkedIn / GitHub Pages URL:** https://s-ryan-lz3y.github.io/interntrack-linkedin-preview/
- **Actual app:** https://interntrack-6k9.pages.dev/
- **Source of full app:** private repository `s-ryan-lz3y/interntrack` (not included here).

## Why this exists

Some link-sharing services do not display a preview for the Cloudflare Pages URL. This repository hosts a small static public landing page containing Open Graph and Twitter Card metadata. Social crawlers can inspect this landing page; normal visitors are sent to the real InternTrack application. A visible fallback link is also provided.

The Open Graph image is copied from the **existing, public InternTrack social preview** into the GitHub Pages deployment artifact. This repository does **not** contain production application code, credentials, databases, student records, or login forms.

## Deployment

1. In GitHub repository **Settings → Pages → Build and deployment**, select **GitHub Actions** for Source.
2. Run the **Deploy InternTrack LinkedIn preview** action (or push to `main`).
3. Confirm the Pages URL returns a 200 response, serves `/social-preview.png`, and exposes `og:title`, `og:image`, and `og:url` in its static HTML.

The workflow fetches the public PNG from InternTrack at deployment time and verifies it is a PNG before uploading. If the PNG cannot be fetched, deployment fails rather than publishing a broken preview.

After the site is live, inspect it using [LinkedIn Post Inspector](https://www.linkedin.com/post-inspector/) before adding the link to LinkedIn Projects or Featured.

**Privacy:** A public preview page and social image only. No tracking pixels, credentials, or user-submitted information.

# Taiwo Oloni — AI Automation Portfolio

A production-ready React portfolio focused on the business value of AI automation. It includes responsive pages, six detailed services, filterable workflow case studies, deferred video support, accessible galleries, FAQs, a real Netlify consultation form, privacy and thank-you pages, structured SEO data, and automated tests.

## Open Design redesign variant

This design was developed as a separate comparison build and selected for production on 2026-08-03. The earlier blue-and-teal version remains recoverable through Git history and the local `original-design` branch. This variant uses an evidence-backed direction synthesized with Open Design Intelligence from Mastercard, IBM, and Vodafone references: a warm editorial canvas, engineered grid, flat hairline surfaces, minimal corner radius, one decisive coral accent, and diagrammatic automation cues. It adapts general design decisions only and does not copy brand assets or proprietary motifs.

Run each folder on a different local port to compare them side by side:

```bash
# Current deployed design
npm run dev -- --port 4173

# Open Design redesign
npm run dev -- --port 4174
```

## Technology

React, Vite, TypeScript, React Router, Lucide icons, CSS, Vitest, Testing Library, ESLint, Prettier, and Netlify Forms. Content is static and strongly typed; no backend or secrets are required.

## Install and run

```bash
npm install
npm run dev
```

Open the local URL printed by Vite.

## Quality commands

```bash
npm run typecheck
npm run lint
npm test
npm run build
npm run preview
```

The production output is written to `dist/`.

## Content editing

The editable profile, contact placeholders, services, projects, testimonials, and FAQs live in `src/data.ts`. The interfaces at the top of that file describe every project field.

### Add or edit a project

Copy a project object in the `projects` array, give it a unique URL-safe `slug`, and update all content. The card and `/workflows/:slug` case-study route are created automatically. Keep the status honest. Any sample or expected results must remain clearly identified as unverified.

### Add workflow screenshots

Export an n8n or Zapier canvas as PNG or WebP, optimise it, place it in `public/workflows/`, then set each `images[].src`, `alt`, and `caption` value. The gallery lazy-loads images and opens the full image in a keyboard-accessible browser view. Use descriptive alt text.

### Add a video

In a project object, set `video.type` to `youtube`, `loom`, `vimeo`, or `mp4`, then add `video.url`. YouTube watch URLs are converted to privacy-enhanced embeds. Use the provider's embed URL for Loom and Vimeo. Put local MP4 files in `public/videos/` and use a path such as `/videos/demo.mp4`. External videos load only after the visitor selects the demo button. No video produces a polished fallback.

### Profile, social, booking, and contact links

Replace every placeholder in the `profile` object in `src/data.ts`, including email, phone, LinkedIn, GitHub, WhatsApp, and booking URL. Replace `public/headshot-placeholder.svg` with an optimised portrait and update the path if the filename changes.

## SEO

`VITE_SITE_URL`, `public/sitemap.xml`, and `public/robots.txt` are configured for `https://taiwo-oloni-automation.netlify.app`. Update all three if a custom domain is connected. Page metadata and JSON-LD are managed by the `SEO` component in `src/App.tsx`. Add a real social preview image and `og:image` metadata before a public campaign.

## Netlify deployment

1. Push this folder to a GitHub, GitLab, or Bitbucket repository.
2. In Netlify, choose **Add new site → Import an existing project** and select the repository.
3. Netlify reads `netlify.toml`; confirm build command `npm run build` and publish directory `dist`.
4. Add `VITE_SITE_URL` under **Site configuration → Environment variables** with the final site URL.
5. Deploy. The SPA redirect allows direct visits to every case-study route.
6. Replace placeholder URLs in `sitemap.xml` and `robots.txt` once the final domain is known, commit, and redeploy.

### Netlify Forms and notifications

The form already includes `data-netlify`, a hidden `form-name`, a honeypot, validation, a real POST, and `/thank-you` success redirect. After the first production deploy, open **Forms** in Netlify and confirm a `consultation` form appears. Submit one real test. Then open **Project configuration → Notifications → Form submission notifications**, choose email or webhook, select the `consultation` form, and add the desired recipient. Review spam settings and submission retention.

If Netlify does not detect the form, confirm the deployed HTML contains `form-name=consultation`, clear the build cache, and redeploy. If direct URLs return 404, confirm both `netlify.toml` and `public/_redirects` were deployed.

## Privacy and security

Edit `/privacy` copy in `src/App.tsx` to match actual retention, service providers, contact details, and legal requirements. Never add credentials to source. Store future secrets in Netlify environment variables and mirror only key names in `.env.example`. Review the Content Security Policy in `netlify.toml` whenever a new external provider is added.

## Pre-launch replacement checklist

- Taiwo's professional portrait and accurate alt text
- Real email, phone/WhatsApp, LinkedIn, GitHub, and booking URL
- Real n8n/Zapier workflow screenshots and captions
- Demo video URLs or local MP4 files
- Real project context, scope, and only verified results
- Real testimonials only after client approval
- Industry/client descriptions where permission exists
- Final privacy terms and retention period
- Social sharing image and metadata

## Updating dependencies

Run `npm update`, then repeat type checking, linting, tests, and production build. Review major-version release notes before deploying updates.

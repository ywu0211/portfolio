# Personal engineering portfolio

An Astro + TypeScript static portfolio for **ywu0211**. Original CSS illustrations, responsive layouts, semantic HTML, reduced-motion support, print styling, and no client-side framework runtime. A small early script applies the saved System, Light, or Dark preference before rendering. The header selector defaults to System and stores the choice in browser local storage; system appearance changes and changes from another tab are reflected immediately. The about page also has a small print action.

## Run locally

Use a current Node 22 LTS release (22.19+ recommended).

```sh
npm ci
npm run dev
```

Local address: http://localhost:4321. Validate with `npm run check` and `npm run build`. Production output is in `dist/`; `npm run preview` serves it locally.

## Content

- `src/data/profile.ts`: name, public email, GitHub, optional LinkedIn and résumé URL.
- `src/pages/index.astro`: homepage and future third-case-study space.
- `src/pages/work/elements.astro`: Elements overview.
- `src/pages/work/ai-chatbot.astro`: AI chatbot overview, with proposed design considerations clearly labeled.
- `src/pages/about.astro`: professional summary, résumé request, and contact.
- `src/styles/global.css`: shared design tokens, layout, responsive and print styles.

The GitHub handle is used as the display name until a preferred public name is confirmed. A résumé PDF was not supplied: the site has a functional email request rather than a broken download. To add one, place the approved file at `public/resume.pdf` and set `resumeUrl` to `/resume.pdf`.

The supplied brief establishes the areas of ownership. It does not establish project dates, employers, quantitative outcomes, chatbot implementation details, or employment history. None are invented. The chatbot page explicitly distinguishes design considerations from shipped features. Refine it with verified responsibilities and outcomes when available. The original diagrams and fictional conversation contain no proprietary assets.

## GitHub

Suggested repository: `ywu0211/portfolio`. Create an empty repository, then run from this directory:

```sh
git init -b main
git add .
git commit -m "Build Astro engineering portfolio"
git remote add origin https://github.com/ywu0211/portfolio.git
git push -u origin main
```

If the local repository and initial commit already exist, skip those steps. Never overwrite an existing remote; inspect `git remote -v` first. No credentials belong in source files. The included GitHub Actions workflow checks and builds pull requests and pushes to main.

## Vercel

1. Sign in to Vercel and choose Add New → Project.
2. Import `ywu0211/portfolio` after pushing it to GitHub.
3. Use the repository root, Astro preset, `npm run build`, and `dist` output. `vercel.json` supplies these settings. Use a current Node 22 runtime.
4. Deploy. No Vercel adapter, database, or environment secrets are needed for this static site.
5. After the production address is assigned, set `SITE_URL` in Vercel to the full HTTPS origin and redeploy to enable canonical URLs.

See [Astro’s Vercel guide](https://docs.astro.build/en/guides/deploy/vercel/).

## Custom domain later

Add the domain in Vercel Project Settings → Domains, follow the DNS records Vercel supplies, and select the intended primary domain. Set `SITE_URL` to that HTTPS origin and redeploy. Domain availability and pricing have not been checked; no domain has been purchased.

Fonts currently load from Google Fonts with system fallbacks. The layout remains usable without that request. No analytics, trackers, form submission service, or private company links are included.

## Add the third study

Create a new page in `src/pages/work/` using the shared `Layout`, then replace the non-clickable future-study row on the home page with a link. Keep employer-sensitive implementation details out of the public repository.


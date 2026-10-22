# अभ्यासधारा अकॅडमी

A Marathi-only, statically rendered promotional homepage built with Astro, custom CSS, and a small TypeScript enhancement. No database, Firebase configuration, API keys, or application backend is required.

## Develop

Use Node 24 (the tested version is recorded in `.node-version`).

```sh
npm ci
npm run dev
```

The cloud machine restricts writes to the home directory. Use `npm ci --cache /workspace/.npm-cache` there. The npm scripts disable Astro's optional telemetry so its configuration does not require home-directory writes.

```sh
npm run check
npm run build
npm run preview
```

The development server uses port 4321. To use another port, append `-- --port 4322`. Existing cloud tasks are already isolated; use the existing checkout rather than creating a Git worktree.

## Structure

- `src/pages/index.astro`: homepage, Marathi copy, metadata, structured data, and minimal client interactions.
- `src/styles/global.css`: shared tokens, responsive layout, theme colors, typography, and reduced-motion behavior.
- `src/components/`: reusable brand and inline SVG icons.
- `public/`: local fonts and their OFL licenses, favicon, sharing image, sitemap, robots rules, and Cloudflare response headers.

Both Devanagari variable fonts are self-hosted. The site makes no third-party requests on page load. Only the download links navigate to the supplied Google Play listing. The phone illustration and practice calendar are labeled concepts; the sample question is a functional learning example. App feature availability and pricing are directed to the app, without invented ratings or user counts.

## Static deployment

Cloudflare Pages settings:

- Build command: `npm run build`
- Output directory: `dist`
- Node version: `24.19.0`

No adapter, bindings, secrets, or runtime worker is needed. Canonical URLs, the sitemap, and sharing metadata use `https://abhyasdhara.in/`. Deployment and domain configuration remain separate from local validation.

## Validation

The production build and Astro diagnostics were checked. Chromium QA covered widths 320, 360, 390, 430, 768, 1024, and 1440; the answer demo, theme persistence, native navigation/FAQs, reduced motion, and JavaScript-disabled behavior were exercised. See `VALIDATION.md` for the measured results and their limits.

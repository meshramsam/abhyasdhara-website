# Validation record

Production output was tested locally on 21 October 2026 with Chromium 154. These are lab checks, not measurements of a deployed website or real-user performance.

- `npm ci --cache /workspace/.npm-cache`: reproducible lockfile installation.
- `npm run check`: zero Astro/TypeScript errors, warnings, or hints.
- `npm run build`: one static homepage generated.
- Chromium viewports: 320, 360, 390, 430, 768, 1024, 1440 pixels. No document overflow or visible text clipping.
- Native mobile menu, menu dismissal, anchor destinations, Google Play destinations, FAQ disclosure, theme preference/persistence, correct/incorrect question feedback, and answer explanation checked.
- JavaScript disabled: content, navigation, download links, question selection, answer disclosure, and FAQs remain available. Instant answer feedback and theme override require JavaScript.
- Keyboard skip link and reduced-motion behavior checked.
- Marathi-only visible copy and Devanagari rendering checked.

Mobile Lighthouse, using the production preview and default simulated mobile throttling:

| Category | Score |
| --- | --- |
| Performance | 99 |
| Accessibility | 100 |
| Best practices | 100 |
| SEO | 100 |

Measured LCP was 2.3 seconds, CLS 0, and total blocking time 0 milliseconds. Results depend on the machine, network, and hosting. Field LCP and INP are not available until deployment and real usage. Automated accessibility checks do not replace a full assistive-technology audit.

The repository started empty. The app dashboard and calendar are original, clearly labeled illustrations; no real application UI or user performance data was supplied. These validation checks did not deploy or publish the website.

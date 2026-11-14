# Joel Salomon — Portfolio

Single-file portfolio for a senior IT engineer and systems architect: infrastructure, virtualization,
observability, automation and IT operations. Built to serve two audiences at once — consulting clients who
need to judge depth quickly, and recruiters who need the facts fast.

Live: <https://joelsalomon.healthyfolks.mu>

## What is in here

| File | Purpose |
| --- | --- |
| `index.html` | The entire site: markup, styles, scripts, SVG. No build step, no dependencies. |
| `joel_salomon_senior_it_engineer_systems_architect_v3_og.png` | 1200×630 social card used by Open Graph and Twitter tags. |
| `robots.txt`, `sitemap.xml` | Crawler hints for the live host. |

## Design and engineering notes

- **Zero dependencies, zero network on load.** No frameworks, no web fonts, no CDN, no analytics beacon.
  The page renders fully with JavaScript disabled.
- **One file, ~41 KB.** Served gzipped at ~11 KB.
- **Interaction:** click-to-run terminal cards, a click-through topology hero, count-up metrics,
  scroll reveals, a progress rail and a ring-shaped back-to-top control.
- **Accessibility:** skip link, visible focus states, `prefers-reduced-motion` support, live regions for
  the interactive demo output, semantic landmarks.
- **SEO:** canonical URL, Open Graph and Twitter cards, JSON-LD `Person` graph, sitemap and robots.
- **AI advisor (`#lab`)** posts to a same-origin `ai/generate` endpoint and expects `{ "text": "..." }`.
  The endpoint is served by the owner's own infrastructure running a local language model; no API keys
  ship in this file, and the page degrades to a plain offline notice when the endpoint is unreachable.

## Running it locally

```bash
python3 -m http.server 8080
# open http://127.0.0.1:8080
```

The AI advisor will report itself unavailable locally — that is expected, since `ai/generate` is only
served by the deployed host.

## Content policy

Only verifiable professional data is published: roles, dates, certifications and education are taken
from the owner's CV and LinkedIn profile. No client names, phone numbers, addresses or internal
hostnames appear anywhere in the page.

## License

Content and images © Joel Salomon. The code is provided as-is for reference; please do not republish the
personal content as your own.

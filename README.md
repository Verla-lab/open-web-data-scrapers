# Open Web Data Scrapers

A curated directory of open-source Python scrapers for public web data. One target per repository, runnable locally, with structured JSON/CSV output.

> The catalog starts small on purpose. Projects are added only after their data scope, implementation, fixtures, and responsible-use notes are verified.

## Scraper catalog

| Project | Public data | Method | Login | Output | Status |
|---|---|---|---|---|---|
| Amazon product data | Search results, titles, prices, ratings, product URLs | Browser | No | JSON/CSV | Planned |
| Transfermarkt market values | Players, clubs, positions, public market values | Browser | No | JSON/CSV | Planned |
| Hacker News data | Stories, scores, authors, comments | HTTP | No | JSON/CSV | Planned |
| Google Play app data | App metadata, ratings, categories, update dates | HTTP | No | JSON/CSV | Researching |
| Public article metadata | Titles, authors, dates, tags, canonical URLs | HTTP | No | JSON/CSV | Researching |

## Repository standard

Every published scraper should include:

- A focused, site-specific use case
- A minimal local quick start
- Typed output models and JSON/CSV exporters
- Sanitized example output
- Offline fixtures and tests
- Pagination, rate-limit, and failure handling
- A last-verified date and maintenance status
- Responsible-use and security guidance

## Access-state model

Scrapers report access states instead of hiding failures:

```json
{
  "status": "verification_required",
  "checkpoint": "interactive_verification",
  "retryable": false,
  "manual_action_required": true
}
```

When a site requires login, private access, payment, or human verification, the default behavior is to stop safely.

## Suggested repository layout

```text
project/
├── README.md
├── LICENSE
├── SECURITY.md
├── CONTRIBUTING.md
├── pyproject.toml
├── src/
├── examples/
├── fixtures/
├── tests/
├── sample-output/
│   ├── records.json
│   └── records.csv
└── .github/workflows/test.yml
```

## Responsible use

These projects are intended for public data, authorized research, QA, and personal automation. Users are responsible for reviewing website terms, robots guidance, rate limits, copyright, privacy obligations, and applicable laws.

Do not use these examples to access private or restricted data, automate account actions, collect sensitive personal information, or interfere with a service.

## Disclaimer

Verla Lab is not affiliated with the websites referenced by individual projects. Names and trademarks belong to their respective owners.

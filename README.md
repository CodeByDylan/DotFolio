# DotFolio

The central `.folio` configuration for [Folio](https://github.com/CodeByDylan/Folio), which assembles
a portfolio from GitHub repository metadata and the `.folio` files committed inside the showcased
repositories.

This repository holds the site-wide half of that: which projects appear, the tag and relation
vocabularies they draw on, the localized strings, and the pages the site publishes.

Sections are declared once and composed into pages by reference, so where a section appears is a
one-line change. A page carries a slug and may claim `home`; it never names a URL, because deciding
what path a slug becomes is the frontend's job.

```text
.folio/
├── site.toml          site URL, owner, declared locales, site links, sections, pages
├── projects.toml      which repositories are showcased, and in what order
├── tags.toml          the tag vocabulary; a tag outside it is dropped
├── locales/           one file per declared locale
│   ├── en.toml
│   └── nl.toml
└── content/           section bodies, one directory per declared locale
    ├── en/about.md
    └── nl/about.md
```

All three TOML files are required. If any is missing the refresh is abandoned and the previously
built snapshot keeps serving.

Point a Folio deployment at this repository with `GitHub__CentralRepository=CodeByDylan/DotFolio`.
The format is documented in the Folio repository under `docs/`.

## Licence

Apache 2.0. See [LICENSE](LICENSE).

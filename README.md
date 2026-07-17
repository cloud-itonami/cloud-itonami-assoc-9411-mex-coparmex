# cloud-itonami-assoc-9411-mex-coparmex

Industry rule/history catalog for **COPARMEX** (Confederación Patronal
de la República Mexicana) — the ELEVENTH entry aligned to **ISIC 9411**
(activities of business, employers, and professional membership
organizations), alongside
[`-9411-sau-fsc`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-sau-fsc)
(Saudi Arabia),
[`-9411-aut-wko`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-aut-wko)
(Austria),
[`-9411-irl-ibec`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-irl-ibec)
(Ireland),
[`-9411-nzl-businessnz`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-nzl-businessnz)
(New Zealand),
[`-9411-cze-spcr`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-cze-spcr)
(Czech Republic),
[`-9411-ind-cii`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-ind-cii)
(India),
[`-9411-zaf-busa`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-zaf-busa)
(South Africa),
[`-9411-bra-cni`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-bra-cni)
(Brazil),
[`-9411-ken-kam`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-ken-kam)
(Kenya), and
[`-9411-can-chamber`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-can-chamber)
(Canada). Part of the
[`cloud-itonami`](https://github.com/cloud-itonami) compliance-fact
family (ADR-2607141700, `cloud-itonami-compliance-fact-federation`,
in `com-junkawasaki/root`).

## Sourcing note

This repo fills Mexico's previously-open association-axis gap (one of
the 17-country gap list recorded at tick 145). Mexico now has real,
individually verified facts across all three axes: country
([`cloud-itonami-iso3166-mex`](https://github.com/cloud-itonami/cloud-itonami-iso3166-mex)),
municipality
([`cloud-itonami-municipality-mex-guadalajara`](https://github.com/cloud-itonami/cloud-itonami-municipality-mex-guadalajara)),
and association (this repo).

Both entries here were directly WebFetch-verified against
`coparmex.org.mx`'s own official "Nuestra Historia" page, which
rendered successfully — no fallback needed. No dedicated Wikidata
"inception" statement exists for COPARMEX (Q2996731 has a "start
time" property, but it is attached to the organization's
Facebook-username field dated 2012, not the actual founding) — noted
transparently rather than misused as corroboration.

## Scope

A **read-only reference/archive** catalog — not an Advisor⊣Governor
actuation actor. It proposes or executes nothing on COPARMEX's
behalf.

Coverage is reported honestly (see `association.facts/coverage`): an
association not in `catalog` has **no spec-basis**, full stop — never
fabricate one.

## Data

- `src/association/facts.cljc` — the catalog, source of truth.
- `schema/association-rule.edn` — DataScript schema.
- `data/datascript-tx.edn` — derived DataScript tx-data (query this
  alongside other `cloud-itonami`/`etzhayyim` compliance-fact sources via
  `com-junkawasaki/root`'s `scripts/compliance-fact-query.cljs`).

Both entries directly WebFetch-verified against `coparmex.org.mx`'s
own History page: the 26 September 1929 founding of COPARMEX in
Mexico City, and the 1989 start of COPARMEX's electoral-observer
work.

## License

AGPL-3.0-or-later (matches the `cloud-itonami-iso3166-*` /
`-municipality-*` / `-assoc-*` / `-lei-*` convention). Policy text
itself remains COPARMEX's; this repo stores only citation metadata
(id/title/url/dates), not full text.

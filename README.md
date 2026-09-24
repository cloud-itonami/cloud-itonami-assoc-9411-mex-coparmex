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

Every entry cites a page on `coparmex.org.mx` (Nuestra Historia,
¿Quiénes somos?, the Estructura Nacional pages for the Assembly, the
Board, the Executive Commission, the Federations and the Working
Commissions, Coparmex en tu Estado, Documentos Base, Transparencia,
Ser Socio, Representación Nacional e Internacional). Each entry carries
the verbatim Spanish span of that page the claim rests on
(`:source-quote`), taken from the page body rather than the site menu
and footer that every page repeats. The History page names the founder
next to the founding date and the governance pages list the people on
each organ; the quotes stop before every name. Figures COPARMEX gives
about itself (36,000 member employers, 30% of GDP) are recorded as what
COPARMEX states, not as independently measured facts.

No dedicated Wikidata "inception" statement exists for COPARMEX
(Q2996731 has a "start time" property, but it is attached to the
organization's Facebook-username field dated 2012, not the actual
founding), so the founding date rests on COPARMEX's own page only.

## Scope

A **read-only reference/archive** catalog — not an Advisor⊣Governor
actuation actor. It proposes or executes nothing on COPARMEX's
behalf.

Coverage is reported honestly (see `association.facts/coverage`): an
association not in `catalog` has **no spec-basis**, full stop — never
fabricate one.

## Data

- `data/datascript-tx.edn` — the catalog. Facts are authored here and
  nowhere else (DataScript tx-data; query it alongside other
  `cloud-itonami`/`etzhayyim` compliance-fact sources via
  `com-junkawasaki/root`'s `scripts/compliance-fact-query.cljs`).
- `src/association/facts.kotoba` (Clojure reading) and
  `src/association_facts.kotoba` (Kotoba port) — both GENERATED from the
  data file by `scripts/gen-kotoba-port.cljk`. Do not hand-edit.
- `schema/association-rule.edn` — DataScript schema.

```bash
# 1. edit data/datascript-tx.edn, then regenerate both readings
kbb --backend sci scripts/gen-kotoba-port.cljk
kbb --backend sci scripts/gen-kotoba-port.cljk --check   # exit 1 if either reading drifted

# 2. check the catalog against its own sources
kbb --backend sci scripts/verify-catalog.cljk            # structural, offline
kbb --backend sci scripts/verify-catalog.cljk --live     # fetch every :url, require every quote
```

`verify-catalog` exits 0 (checked, nothing wrong), 1 (findings printed)
or 2 (REFUSED: it could not read the catalog or a source, which is
neither a pass nor a finding). Dates are checked in the Spanish the
sources write them in (`26 de septiembre de 1929`).

## License

AGPL-3.0-or-later (matches the `cloud-itonami-iso3166-*` /
`-municipality-*` / `-assoc-*` / `-lei-*` convention). Policy text
itself remains COPARMEX's; this repo stores only citation metadata
(id/title/url/dates) and the short verbatim span each claim rests on,
not full text.

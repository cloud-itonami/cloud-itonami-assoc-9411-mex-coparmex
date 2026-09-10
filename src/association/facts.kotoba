(ns association.facts
  "Industry rule/history catalog for COPARMEX (Confederación Patronal
  de la República Mexicana) -- a 53rd industry-association-level
  source (see cloud-itonami-assoc-9411-sau-fsc, -9411-aut-wko,
  -9411-irl-ibec, -9411-nzl-businessnz, -9411-cze-spcr, -9411-ind-cii,
  -9411-zaf-busa, -9411-bra-cni, -9411-ken-kam, -9411-can-chamber for
  the first ten) per ADR-2607141700
  (cloud-itonami-compliance-fact-federation). The ELEVENTH entry
  aligned to ISIC 9411 (activities of business, employers, and
  professional membership organizations). Fills Mexico's
  previously-open association-axis gap (one of the 17-country gap
  list recorded at tick 145) -- Mexico now has real, individually
  verified facts across ALL THREE axes (country:
  cloud-itonami-iso3166-mex statute.facts; municipality:
  cloud-itonami-municipality-mex-guadalajara; association: this
  entry).

  Both entries directly WebFetch-verified against coparmex.org.mx's
  own official 'Nuestra Historia' page
  (https://coparmex.org.mx/nuestra-historia/), which renders
  successfully and states verbatim: 'Coparmex nace en la Ciudad de
  México el 26 de septiembre de 1929 por iniciativa del industrial
  regiomontano Don Luis G. Sada' (COPARMEX was born in Mexico City on
  26 September 1929) and 'Coparmex inicia trabajos como observador
  electoral' (1989, COPARMEX begins electoral-observer work). No
  dedicated Wikidata 'inception' statement was found for COPARMEX
  (Q2996731 has a 'start time' property but it is attached to the
  organization's Facebook-username field, dated 2012, not the
  organization's actual founding -- noted transparently rather than
  misused as corroboration). The founder's name (Luis G. Sada),
  incidentally encountered on the official page, is NOT persisted
  here per this project's no-personal-names rule.

  An association not in `catalog` has NO spec-basis, full stop; never
  fabricate one.")

(def catalog
  "association-slug -> vector of association-rule entries."
  {"coparmex"
   [{:association-rule/id "coparmex.founding-1929"
     :association-rule/title "COPARMEX (Confederación Patronal de la República Mexicana) founded in Mexico City on 26 September 1929 (coparmex.org.mx official 'Nuestra Historia' page)"
     :association-rule/association "coparmex"
     :association-rule/isic "9411"
     :association-rule/country "MEX"
     :association-rule/kind :governance-program
     :association-rule/url "https://coparmex.org.mx/nuestra-historia/"
     :association-rule/url-provenance :official-coparmex-org-mx
     :association-rule/established-date "1929-09-26"
     :association-rule/retrieved-at "2026-07-17"
     :association-rule/topic #{:governance}}
    {:association-rule/id "coparmex.electoral-observer-1989"
     :association-rule/title "COPARMEX begins work as an electoral observer ('Coparmex inicia trabajos como observador electoral'), 1989 (coparmex.org.mx official 'Nuestra Historia' page)"
     :association-rule/association "coparmex"
     :association-rule/isic "9411"
     :association-rule/country "MEX"
     :association-rule/kind :governance-program
     :association-rule/url "https://coparmex.org.mx/nuestra-historia/"
     :association-rule/url-provenance :official-coparmex-org-mx
     :association-rule/established-date "1989"
     :association-rule/retrieved-at "2026-07-17"
     :association-rule/topic #{:governance}}]})

(defn spec-basis [association] (get catalog association))

(defn coverage
  ([] (coverage (keys catalog)))
  ([associations]
   (let [have (filter catalog associations)
         missing (remove catalog associations)]
     {:requested (count associations)
      :covered (count have)
      :covered-associations (vec (sort have))
      :missing-associations (vec (sort missing))
      :note (str "cloud-itonami-assoc-9411-mex-coparmex Wave 0 (ADR-2607141700): "
                 (count (get catalog "coparmex")) " COPARMEX entries seeded "
                 "with coparmex.org.mx official History page (no valid Wikidata inception "
                 "statement exists for corroboration -- noted transparently). "
                 "Extend `association.facts/catalog`, never fabricate an id/url.")})))

(defn by-topic [association topic]
  (filterv #(contains? (:association-rule/topic %) topic) (spec-basis association)))

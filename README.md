# tass-lexicons

The public dictionary registry for [TASS](https://usetass.app) (Text Analysis for Social
Scientists, a [SIM DAD LLC](https://simdadllc.com) product). Every lexicon here is open, versioned, hash-pinned, and
citable. Install by name from the TASS CLI:

```
tass search
tass install politeness
tass score -i corpus.csv --text-column text --lexicons politeness -o scored.csv
```

Installed lexicons resolve like bundled ones, and their license and citation metadata travel
into the provenance manifest of every run that uses them.

## The openness mandate

TASS-native dictionaries (the T-Lex series, and TASS Politeness Markers) exist to be the
open, inspectable counter to proprietary, non-inspectable dictionaries. Therefore every
TASS-developed dictionary in this registry is released under an open license that permits
any use, including commercial use, with citation as the only requirement (CC-BY-4.0 for
curated word lists, ODC-BY for rating databases). They are never gated, never
academic-only, and never a paid differentiator.

## Layout

```
index.json                         registry index: id, versions, sha256 per version
lexicons/<id>/<version>/lexicon.json   the lexicon (TASS JSON format)
lexicons/<id>/<version>/CITATION.cff   citation metadata (authors, year, identifiers)
templates/tass-dictionary-template.csv the spreadsheet authoring template
```

## Authoring and contributing

You do not need to write JSON. Fill the spreadsheet template in Excel or Google Sheets,
save as CSV, and convert:

```
tass template -o my-dictionary.csv
tass import-csv -i my-dictionary.csv -o my-dictionary.json
```

To propose a dictionary for the registry, open a pull request adding
`lexicons/<id>/<version>/lexicon.json` plus a `CITATION.cff`. Requirements: an open license
(CC-BY-4.0 or ODC-BY for TASS-branded entries), a citation with author, year, and a
permanent URL or DOI, and category documentation. Substantive contributors to T-Lex
dictionaries are offered co-authorship on the associated dictionary paper and are named in
the dictionary metadata, which every user's manifest then carries. See CONTRIBUTING.md, or
write to tass@simdadllc.com with the subject "T-Lex Collaboration".

## Verification

Each version's `sha256` in `index.json` pins the exact bytes `tass install` will accept.
Releases of this repository are archived for DOI minting so each dictionary version is
independently citable.

(c) SIM DAD LLC and the individual dictionary authors. Each lexicon carries its own license.

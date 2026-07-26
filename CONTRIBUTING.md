# Contributing a dictionary

## Ground rules

1. **Open license, no exceptions.** TASS-branded (T-Lex) entries must be CC-BY-4.0 (word
   lists) or ODC-BY (rating databases). Third-party entries must carry a license that
   permits redistribution here (permissive, CC-BY, or public domain). Non-commercial and
   share-alike licensed resources are not accepted.
2. **Citable by construction.** Every entry needs a `CITATION.cff` with authors, year,
   version, and a permanent URL or DOI. This metadata surfaces in every TASS run manifest.
3. **Documented constructs.** Each category needs a one-line definition, and the dictionary
   description must state what it approximates and what it does not (see the politeness
   entry for the pattern: it is an approximation of a published taxonomy and says so).
4. **Nothing restricted, ever.** Do not submit LIWC, NRC, General Inquirer, or any other
   restricted resource, in whole or in part, including reformatted or "cleaned" versions.

## Process

1. Author your dictionary (spreadsheet template + `tass import-csv` recommended).
2. Validate locally: `tass score` against a small corpus; check category hit sanity.
3. Open a PR adding `lexicons/<id>/<version>/lexicon.json` + `CITATION.cff` and an
   `index.json` entry with the file's sha256 (`shasum -a 256 lexicon.json`).
4. Review checks: schema validity, license, citation completeness, construct documentation,
   and a scoring smoke test.

## T-Lex co-authorship

The T-Lex Project is building original, open lexicons for social science text analysis.
Contributor work includes reviewing and validating candidate word lists against published
measurement frameworks, re-scoring items that need domain expertise, supplementing seed
lists, and refining category definitions. Contribution is asynchronous and self-paced;
credit is proportional to contribution, and substantive contributors are offered
co-authorship on the dictionary paper. Contact: tass@simdadllc.com, subject
"T-Lex Collaboration".

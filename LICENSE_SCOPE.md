# License scope

This repository contains materials under three distinct licensing regimes. The scope is intentionally separated so that the code license is not mistaken for a license on all research data, and the authors' CC BY grant does not override OpenStreetMap terms.

## 1. Original source code — MIT License

The MIT License in `LICENSE` applies to the authors' original source-code files, including the code under `main_algorithm/` (excluding data and non-code files), `mechanism_audit/run_postman_experiment.py`, `analysis/*.py`, and `scripts/*.py`. Third-party dependencies and any third-party code retain their own licenses. The MIT notice does not license the research datasets or result files merely because they are stored beside source code.

## 2. OpenStreetMap-derived data — ODbL 1.0

The Open Database License (ODbL) 1.0 applies to OSM-derived databases and extracted OSM database contents, including:

- `main_algorithm/osm_data/`;
- `mechanism_audit/data/`;
- OSM-derived road geometries, node/way identifiers, road-link attributes, topology, and other extracted database content embedded in experimental route records, audit files, or figures.

See `OSM_DATA_LICENSE.md` for attribution and license links. OSM-derived content remains subject to ODbL 1.0 even when it appears inside a mixed experimental artifact. The CC BY 4.0 notice does not replace or waive ODbL obligations.

## 3. Authors' original non-code research materials — CC BY 4.0

Subject to the exclusions above, the authors' original non-code research materials are licensed under CC BY 4.0. This includes original experimental result tables, run logs, route/checkpoint records, audit outputs, plots, figures, and validation evidence in:

- `main_algorithm/results/`;
- `main_algorithm/verification_evidence/`;
- `mechanism_audit/results/`;
- `results/`;
- `figures/`;
- `main_algorithm/fixtures/`.

Where a file combines original research outputs with OSM-derived database content, CC BY 4.0 covers only the authors' original contributions and rights they control; the OSM-derived portions remain subject to ODbL 1.0. Third-party material remains under its own license or attribution terms.

See `LICENSE-CC-BY-4.0.md` for the license link, scope notice, and suggested attribution.

## Practical interpretation

- Use `LICENSE` for original source-code reuse.
- Use `LICENSE-CC-BY-4.0.md` for the authors' original non-code research outputs.
- Use `OSM_DATA_LICENSE.md` for OSM-derived datasets and any OSM-derived content embedded in mixed artifacts.
- When a file contains material from more than one category, comply with every applicable notice; do not assume that one license supersedes another.

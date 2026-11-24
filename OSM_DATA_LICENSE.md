# OpenStreetMap attribution and data license

The road-network graph instances and derived geometries in this repository were derived from OpenStreetMap data.

**© OpenStreetMap contributors.**

The OSM-derived databases are distributed under the **Open Database License (ODbL) 1.0**.

- License: https://opendatacommons.org/licenses/odbl/1-0/
- Attribution and copyright notice: https://www.openstreetmap.org/copyright

This notice applies, in particular, to:

- `main_algorithm/osm_data/` (the Beijing, Shanghai, and Chongqing graph instances, geometries, and associated source metadata);
- `mechanism_audit/data/` (the six frozen city graph extracts and their OSM node/road-link identifiers);
- OSM-derived database content reproduced or extracted in route records, pair-audit records, checkpoint evidence, or figures elsewhere in the repository.

The relevant source metadata, bounding boxes, retrieval information, and graph-instance hashes are retained in the conversion manifests and graph metadata. The raw PBF extracts are not redistributed; the frozen processed graph instances used by the experiments are included.

When reusing OSM-derived material, retain the OpenStreetMap attribution and comply with ODbL 1.0. Where an experimental artifact mixes OSM-derived content with the authors' original analysis, the ODbL continues to govern the OSM-derived database content. The authors' original non-code contributions are separately licensed under CC BY 4.0 as described in `LICENSE-CC-BY-4.0.md`; that license does not relicense OSM content.

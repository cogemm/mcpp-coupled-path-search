# Preflight before making the repository public

Please complete these checks before pushing to a public GitHub repository:

- [x] The submitting author confirmed that all authors agree to release the team-owned original algorithm code under MIT and the authors' original non-OSM research outputs under CC BY 4.0.
- [ ] Confirm the exact copyright-holder wording in `LICENSE`; the current notice uses the generic wording `The Authors`. Replace it with the author group or institution's preferred wording if required.
- [x] The MIT scope in `LICENSE_SCOPE.md` is limited to the authors' original source code.
- [x] OSM-derived graph databases are identified as ODbL 1.0 in `OSM_DATA_LICENSE.md`; retain attribution in the repository and any reuse.
- [x] The repository separates code (MIT), authors' original non-code research materials (CC BY 4.0), and OSM-derived data (ODbL 1.0).
- [x] The authors confirmed that original non-OSM research outputs (experimental results, logs, route records, and figures) may be released under CC BY 4.0. See `LICENSE-CC-BY-4.0.md`.
- [ ] Review mixed artifacts that contain OSM identifiers, road-link attributes, topology, or extracted road-network content. Ensure ODbL 1.0 attribution and obligations remain visible; CC BY 4.0 applies only to the authors' original contributions in those files.
- [ ] Review preserved Windows absolute paths in historical run records. They retain provenance and include a project-folder path such as `E:\PythonProject8`; no credentials are included, but authors may prefer normalized public copies.
- [ ] Review `PROVENANCE_RECONCILIATION.md`: the older provenance record's PythonProject8 archive hash does not match the currently supplied archive, and the referenced manuscript DOCX was not included in the uploads.
- [ ] Compare the manuscript's current tables, figures, abstract, and Data Availability Statement against `results/reanalysis/` before release. Do not silently revise the experiment scope or the 99/108 run distinction.
- [ ] Confirm that all included third-party algorithm descriptions are cited in the manuscript and in `literature_fidelity_manifest.json`.
- [ ] After pushing, verify the public GitHub repository and create a tagged Release. Only then connect Zenodo and use the resulting DOI in the manuscript.

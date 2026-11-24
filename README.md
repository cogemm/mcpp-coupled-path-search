# mcpp-coupled-path-search
Coupled-Path Search for the Mixed Chinese Postman Problem
Manuscript: Coupled-Path Search for the Mixed Chinese Postman Problem: Algorithm Design and Verifiable Evaluation  
Target journal: Algorithms  
Manuscript ID: algorithms-4755266
This repository contains the V21 CPRNPS implementation, frozen OpenStreetMap-derived graph instances, the archived three-city algorithm comparison, the six-city paired-path mechanism audit, route/checkpoint verification records, reanalysis outputs, figures, and selected development diagnostics supplied for the manuscript.
> \*\*Evidence boundary.\*\* The three-city experiment is marked in its archived integrity files as exploratory development evidence, not an untouched confirmatory test. The three cities are the inference clusters; seeds are nested within graph instances. The package does not establish universal superiority, global optimality of the full MCPP heuristic, or official numerical equivalence to the authors' software for the published comparison methods.
Repository map
`main\_algorithm/` — V20/V21 source, runner scripts, frozen three-city OSM graph instances, formal experiment protocol, all run-level artifacts, checkpoints, candidate records, Euler tours, and route-audit records.
`mechanism\_audit/` — six-city paired-path audit script, frozen city graphs, full `pair\_audit.csv`, centre-level records, run manifest, and route witnesses.
`results/reanalysis/` — supplied independent reanalysis tables, audit summary, candidate/checkpoint audit, source provenance, and reanalysis log.
`results/development\_diagnostics/` — five-seed large-graph ablation results and a separate one-seed large-graph diagnostic. These are diagnostics, not the primary literature-comparison table.
`figures/` — supplied Fig. 1–Fig. 6 assets (PNG/TIFF).
`analysis/` — reanalysis and figure-regeneration scripts.
Archived experiment facts
Three-city main experiment
The formal run archive contains nine OSM-derived graph instances: Beijing, Shanghai, and Chongqing, each with target labels 100, 300, and 1000. The actual vertex counts range from 103 to 1,341; target labels are extraction targets, not guaranteed graph sizes.
The archived protocol contains 180 method/seed labels and 108 physical executions:
CPRNPS: 45 physical executions.
GRASP reimplementation: 45 physical executions.
Frederickson reimplementation: 9 physical executions, with deterministic results reused across five seed labels.
Modified Mixed reimplementation: 9 physical executions, with deterministic results reused across five seed labels.
The manuscript abstract's 99-run comparison scope is CPRNPS (45) + GRASP (45) + Frederickson (9). The additional nine Modified Mixed physical executions are retained in the complete experiment archive and its summary tables; do not silently count deterministic reused labels as new physical runs. The auxiliary Modified Mixed comparison is 9/9 graph-level wins with a 2.03662% descriptive macro mean cost reduction. It is not named in the abstract's stated 99-run comparison scope, so the authors should reconcile the manuscript's tables and abstract before final submission. All 99 selected primary-comparison physical runs have feasible routes in the supplied reanalysis. The archived audit reports 2,012 checkpoint candidates and 131,861 Euler-walk steps for those 99 runs.
Descriptive mean cost reductions in the supplied audit are 1.70263% against the Frederickson reimplementation and 0.22652% against the GRASP reimplementation. Against GRASP, the nine graph-level comparisons are 4 wins, 4 ties, and 1 loss. These are descriptive results across three city clusters, not evidence of broad or universal dominance. The reimplementations are not the original authors' software; see `main\_algorithm/results/v21\_formal/experiment/literature\_fidelity\_manifest.json`.
The archived eligibility analysis reports a maximum eligible incumbent timestamp of 59.23485 s. Some worker processes exit slightly after the nominal 60 s window because of watchdog/supervisor latency; the eligibility timestamp and process-exit time are distinct fields. Do not describe all process exit times as strictly below 60 s.
Six-city paired-path mechanism audit
The separate audit uses Chengdu, Guangzhou, Hangzhou, Nanjing, Wuhan, and Xiamen. It contains 30 centres per stage (six cities × five seeds) and 61,440 audited pairs per stage, for 122,880 pair rows across the initial and after-single-descent stages.
After bounded single-path descent, 23 of 61,440 audited pairs satisfy the strict pair-specific condition: neither constituent path reversal individually improves the incumbent, while the joint reversal does. Among 24 centres where the sampled single-path pool was stalled and eligible pairs existed, 10 centres were improved by a paired reversal. This is a bounded, sampled-neighborhood mechanism audit, not a proof that all possible single-path moves were exhausted or a fully independent confirmatory test. The run manifest and README in `mechanism\_audit/` define the exact sampling and timing scope.
Development diagnostics
The five-seed large-graph ablation records are retained under `results/development\_diagnostics/`. They include unfavorable or inconclusive outcomes. They must not be selectively omitted when discussing the limitations of the joint-search schedule. These results are separate from the main 99-run comparison.
Reproduction
Environment
The original formal protocol records Python 3.13.13 on Windows 11 and the package versions in `main\_algorithm/results/v21\_formal/protocol.json` and `plan.json`. The V21 kit also contains a separate `requirements-tested.txt` for a Linux/Python 3.12.14 delivery-verification environment. These are different recorded environments; do not treat the latter as the exact environment of the archived formal runs.
Install the combined dependencies from the repository root:
```bash
python -m pip install -r requirements.txt
```
Verify the archived package and run a smoke test
From `main\_algorithm/`:
```bash
python Check\_Environment.py
python Verify\_Package.py
python Run\_V21\_Mechanism\_Tests.py
python Run\_V21\_Smoke.py
```
The smoke test is a new short test, not a reproduction of the archived 60-second formal results. To rerun the full V21 experiment, use `Run\_V21\_ThreeCity\_60s.py`; it is a new execution and will create a new results directory. Do not overwrite the archived `results/v21\_formal` evidence.
Recompute supplied audits and figures
From the repository root:
```bash
python analysis/recompute\_audit.py
python analysis/make\_figures.py
```
These scripts require the combined dependencies. `recompute\_audit.py` checks archived task/source/instance hashes, checkpoint candidates, route walks, six-city pair definitions and witnesses, and writes reanalysis outputs to `results/reanalysis/`.
Rerun the six-city paired-path audit
From `mechanism\_audit/`:
```bash
python -m pip install -r requirements.txt
python run\_postman\_experiment.py --self-test
python run\_postman\_experiment.py
```
This generates a new timestamped output directory. It does not overwrite the archived run.
Data and licensing
Source code covered by the MIT license: see `LICENSE` and `LICENSE\_SCOPE.md`.
OSM-derived road-network databases: ODbL 1.0; see `OSM\_DATA\_LICENSE.md`.
Other non-code research outputs: no separate open-data license is assigned in this package; see `LICENSE\_SCOPE.md`.
Raw PBF files are not redistributed. Frozen processed graph instances, geometries, source metadata and hashes are included.
Provenance and known limitations
`PROVENANCE\_RECONCILIATION.md` records the actual SHA-256 hashes of the two uploaded source archives and explains a mismatch in the older provenance record. The source provenance also references a manuscript DOCX that was not included in either uploaded archive. The discrepancy is disclosed, not silently repaired.
The code package does not claim universal superiority, global optimality of the heuristic, or exact equivalence to the original authors' baseline software. All route feasibility claims are limited to the supplied independent audits and their stated scope.

Simulation reproducibility package for logical-network dissipativity certificates
This repository contains the computational artifacts associated with:
Compositional Dissipativity Certificates and Hitting-Time Bounds for Logical Control Networks
Release: 2.0.2
Date: 2026-07-23
The repository is intentionally simulation-only. It contains finite-model inputs, certificate tables, exact dynamic-programming audits, linear-programming scripts, scheduler-word verifiers, machine-readable results, deterministic numerical figure-data tables, tests, manifests, and hashes. It contains no manuscript source or PDF, bibliography, LaTeX/TikZ/PGFPlots source, reviewer material, or supplementary theorem exposition.
Computational coverage
The release supports four manuscript case studies:
GZMB/MCL1 projected T-cell large granular lymphocyte leukemia certificate;
TPL2/S1P projected certificate with independent source-rule closure and kernel audit;
an unreduced path family for synchronous LP scaling and bounded-window asynchronous singleton updates;
DISC/Caspase/Apoptosis verification under a finite-memory bounded-deadline scheduler.
The bundled T-LGL record contains 54 update rules for the dynamic nodes of the published 60-node model; six source nodes are treated as fixed inputs. Exact finite scheduler-word maximization and complete maximizing/violating-word recovery support the asynchronous audits but do not constitute a fifth case-study row. No module-independent scalable treewidth claim is made for time-unrolled asynchronous scheduler-word separation.
Repository layout
```text
configs/       Retained TPL2/S1P LP configuration.
data/          Frozen GZMB/MCL1 projected-certificate tables.
model/         T-LGL Boolean-network record and module metadata.
results/       Frozen reference outputs and deterministic figure-data tables.
scripts/       Certificate, LP, scheduler, export, and release-verification code.
tests/         Static, finite-state, and deterministic-regeneration checks.
docs/          Reproducibility boundary and interpretation notes.
```
Environment
Python 3.10 or newer is recommended. The finite logical and scheduler verifiers use the Python standard library. LP regeneration additionally requires NumPy, SciPy, and SymPy.
```bash
python3 -m venv .venv
. .venv/bin/activate
pip install -r requirements.txt
```
or
```bash
conda env create -f environment.yml
conda activate bn-passivity-automatica-repro
```
Quick clean-clone validation
```bash
bash scripts/reproduce_all.sh
```
The command emits a JSON summary with `"pass": true` when the static release ledger, finite verifiers, scheduler-word checks, deterministic figure-data regeneration, smoke checks, and small LP-scaling sample all pass. The quick workflow does not rerun the two larger certificate LPs.
Equivalent checks are:
```bash
python3 scripts/verify_release_claims.py
python3 tests/run_async_checks.py
python3 tests/run_scheduler_word_checks.py
python3 tests/run_tpl2_s1p_checks.py
python3 tests/run_figure_data_checks.py
python3 tests/run_smoke_checks.py
```

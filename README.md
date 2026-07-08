Simulation reproducibility package for finite-alphabet dissipativity certificates
This repository contains simulation, model, certificate, and validation artifacts for the paper:
Compositional Finite-Alphabet Dissipativity Certificates for Logical Network Control
Release version: 1.0  
Date: 2026-07-08
This repository is intentionally limited to computational reproducibility artifacts. It does not include paper source files, paper PDFs, bibliography files, or LaTeX/TikZ figure sources.
What is included
```text
configs/       Candidate and clamp-configuration files for optional solver reruns.
data/          Frozen GZMB/MCL1 projected-certificate tables.
model/         T-LGL Boolean-network model record and model-partition metadata.
results/       Reference outputs, solver summaries, and case-study claim ledgers.
scripts/       Verification, solver rerun, and release-check scripts.
tests/         Static package and claim-integrity checks.
docs/          Reproducibility-scope and release-check notes.
```
The package includes executable checks for the main GZMB/MCL1 projected certificate, the projection-free compensation-chain benchmark, and a bounded-treewidth scaled-linear-programming search family. It also includes frozen reference summaries and optional solver-rerun scripts for the promoted TPL2/S1P gate and related candidate-screening workflow.

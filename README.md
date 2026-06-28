# Shiphandling Eye-Gaze & Simulation Data Analysis

> A pilot operations-research study linking expert–novice attention-allocation patterns to performance in a simulation-based shiphandling trainer, in order to drive adaptive feedback in an intelligent tutoring system.

**Author:** Salman Aleem · M.S. Operations Research, Naval Postgraduate School (2017)
**Source thesis:** [*Analysis of Shiphandlers' Eye-Gaze and Simulation Data for Improvements in COVE-ITS System*](https://apps.dtic.mil/sti/pdfs/AD1046288.pdf) — DTIC AD1046288, approved for public release.

---

## Overview

The U.S. Navy's Conning Officer Virtual Environment (COVE) is an immersive shiphandling trainer paired with an intelligent tutoring system (ITS) that monitors trainees and delivers spoken feedback. This project asks whether that feedback can be made *adaptive* by modelling the cognitive state of the trainee — specifically, where expert versus novice shiphandlers direct their visual attention during a simulated transit, and how that attention relates to performance.

The work sits at the intersection of **operations research, modelling & simulation, and human-performance analytics**. It instruments a simulation-based training environment, fuses several heterogeneous data streams captured from a single exercise, and turns the result into a performance model the training system can act on. The central relationship under study is between a shiphandler's *experience level*, their *attention-allocation pattern*, and their *measured performance*.

## Key findings

- Experts achieved measurably better shiphandling performance, characterised by **tight, targeted attention-allocation** focused only on the relevant areas of interest.
- Novices exhibited **scattered, irregular scan patterns** distributed across the visual field.
- Expertise differences were detectable not only in task outcomes but in general eye-tracking measures, scan transitions, and time distribution across areas of interest (AOIs).
- The "ideal" expert gaze patterns can be encoded back into the ITS so it can tell a novice *where to look and when* — converting a descriptive finding into a prescriptive training intervention.

*This was a pilot study (four experts, five novices); the results indicate clear directions and warrant confirmation with a larger sample.*

## Methods

- **Multi-source data fusion** — eye-tracking records, simulator state logs, and instructor voice logs from the same exercise, temporally synchronised into a single analysable record.
- **Eye-gaze metrics** — fixations, scan transitions, and area-of-interest dwell-time distributions.
- **Performance modelling** — measures of performance derived from simulator logs, with structured expert-versus-novice evaluation.
- **Multi-criteria decision analysis** — the Analytical Hierarchy Process (AHP) to weight and combine performance criteria into a single structured evaluation.
- **Statistical analysis and visualisation** in Python (pandas, NumPy, SciPy, Matplotlib).

This repository re-implements the original thesis analysis as a clean, reproducible Python pipeline.

## Repository structure

```
shiphandling-eye-tracking-analysis/
├── README.md
├── requirements.txt
├── LICENSE
├── data/
│   ├── derived/      # aggregated, de-identified datasets used in the analysis
│   └── sample/       # small synthetic sample for exercising the full pipeline
├── notebooks/        # exploratory and final analysis notebooks
├── src/              # reusable modules: synchronisation, gaze metrics, AHP
├── figures/          # generated scan graphs, AOI distributions, ship-path plots
└── docs/             # methodology notes and link to the source thesis
```

## Data availability

This study was conducted under an approved Institutional Review Board protocol (IRB number recorded in the thesis), with nine human participants, and was DoD-sponsored. The thesis and its **aggregated results are cleared for public release**.

Raw participant-level eye-tracking data is **not** redistributed here, because its reuse is governed by the original IRB consent terms. Instead, this repository provides:

- de-identified, aggregated datasets sufficient to reproduce the reported results, and
- a small **synthetic** sample dataset that exercises the full analysis pipeline end to end.

Researchers needing the underlying data should contact the author; any release is subject to NPS / IRB conditions.

## Reproducing the analysis

```bash
git clone https://github.com/salman-aleem-dev/shiphandling-eye-tracking-analysis.git
cd shiphandling-eye-tracking-analysis
pip install -r requirements.txt
jupyter lab        # open notebooks/ and run top to bottom
```

## Context

This repository is part of a broader body of work in **simulation-based training and modelling & simulation** — instrumenting synthetic environments, extracting behavioural and performance models from them, and feeding those models back so that training becomes adaptive. It complements ongoing work on discrete-event and DEVS-based simulation architectures for multi-domain training federations.

## Citation

If you reference this work, please cite the thesis:

```bibtex
@mastersthesis{aleem2017shiphandling,
  author  = {Aleem, Salman},
  title   = {Analysis of Shiphandlers' Eye-Gaze and Simulation Data for Improvements in {COVE-ITS} System},
  school  = {Naval Postgraduate School},
  address = {Monterey, CA},
  year    = {2017},
  note    = {Approved for public release; distribution unlimited. DTIC AD1046288},
  url     = {https://apps.dtic.mil/sti/pdfs/AD1046288.pdf}
}
```

## License

Analysis code is released under the [MIT License](LICENSE). Documentation and generated figures © Salman Aleem. The source thesis is a U.S. Government work distributed via DTIC under public release.

## Author

**Salman Aleem** — M.S. Operations Research, Naval Postgraduate School · MORS-Tisdale Award.
[linkedin.com/in/salman-aleem] · [sa.tvf.au@gmail.com]

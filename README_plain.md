# TPI 3.1 - Theory of the Informative Pixel

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue)](https://www.python.org/)
[![Termux](https://img.shields.io/badge/Termux-Android-green)](https://termux.dev/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> Planckian pixel lattice, emergent gravity, and golden monodromy inflation.
> This repository contains the theoretical framework, numerical simulations,
> and visualization tools for the Theory of the Informative Pixel (TPI) 3.1.

---

## Abstract

The Theory of the Informative Pixel (TPI) 3.1 proposes that spacetime is a
discrete lattice of Planckian pixels, where gravity emerges from quantum
entanglement between these pixels. The theory unifies three fundamental
elements:

1. Entropic gravity - curvature emerges from entanglement gradients on the
   Planckian graph.
2. Golden monodromy inflation - a light scalar field Phi drives inflation
   with a potential whose linear slope and oscillatory period are fixed by
   the golden ratio phi = (1+sqrt(5))/2.
3. Log-periodic primordial spectrum - the power spectrum of curvature
   perturbations exhibits a modulation with frequency omega_N = 2*pi/ln(phi)
   ~ 13.06 and amplitude A_TPI = 7.7e-4.

All parameters are derived from the geometry of the phyllotactic (golden-angle)
lattice, not fitted to data. The theory is compatible with Planck 2018 and
provides unique, falsifiable signatures for CMB-S4, LISA, Euclid, and SPHEREx.

---

## Key Predictions

| Observable              | Prediction                          | Status                        |
|-------------------------|-------------------------------------|-------------------------------|
| P(k) modulation freq.   | omega_N = 13.060371...              | Derived from lattice geometry |
| Modulation amplitude      | A_TPI = 7.7 x 10^-4               | Derived from boundary/volume  |
| CMB oscillations        | ~11.5 coherent peaks (l=10..2500) | Testable by CMB-S4 / LiteBIRD |
| Stochastic GW (LISA)    | Log-periodic Omega_GW(f)            | Unique n_s-r decorrelation    |
| Non-Gaussianity         | f_NL peaks at k1+k2 = phi*k3      | Testable by Euclid / SPHEREx  |

---

## Repository Structure

```
tpi-3.1/
|-- paper/
|   |-- TPI_3_1_paper_completo.tex    # Full LaTeX paper (arXiv-ready)
|-- code/
|   |-- tpi_multicampo.py             # Multi-field inflation simulation
|   |-- tpi_spettro.py                # Primordial power spectrum
|   |-- tpi_bispectrum.py             # Resonant non-Gaussianity estimate
|   |-- tpi_generate_gifs.py          # 3D visualizations (GIF/HTML)
|-- figures/
|   |-- spettro_potenza_TPI.png
|   |-- multipoli_CMB_TPI.png
|   |-- potenziale_TPI.png
|   |-- simulazione_multi_campo_TPI.png
|-- README.md                         # This file
```

---

## Installation (Termux / Android)

Tested on Motorola Edge 40 Neo, Android 14, Termux with Python 3.14.

```bash
# Update packages
pkg update && pkg upgrade

# Install Python and build tools
pkg install python clang cmake libffi openssl

# Install Python packages
pip install numpy scipy matplotlib plotly Pillow imageio

# Clone the repository
git clone https://github.com/YOUR_USERNAME/tpi-3.1.git
cd tpi-3.1/code

# Run the multi-field simulation
python tpi_multicampo.py
```

NOTE: If numpy or scipy fail to compile due to memory limits, enable swap:
```bash
termux-setup-storage
dd if=/dev/zero of=$HOME/swapfile bs=1M count=2048
mkswap $HOME/swapfile && swapon $HOME/swapfile
```

---

## Quick Start

### 1. Multi-Field Inflation Simulation

```bash
python tpi_multicampo.py
```

Output:
- 75 e-foldings of stable inflation
- Golden attractor verified: Phi2/Phi1 = Phi3/Phi2 = 1/phi (to 6 decimals)
- Final slow-roll parameter epsilon ~ 2.9e-3
- Figure saved as simulazione_multi_campo_TPI.png

### 2. Power Spectrum

```bash
python tpi_spettro.py
```

Generates the log-periodic primordial power spectrum P(k) with TPI modulation.

### 3. Bispectrum (Phenomenological Estimate)

```bash
python tpi_bispectrum.py
```

Produces a phenomenological estimate of resonant non-Gaussianity and the
golden-resonance condition k1 + k2 = phi * k3.

---

## The Golden Constraint

The core of TPI is the golden constraint, derived from informational
equilibrium of the phyllotactic lattice:

    mu^3 = (3 * H^2 * Phi_phi) / ln(phi)

This fixes the linear slope of the inflationary potential. Combined with the
boundary-energy term Lambda_0^4, it yields the exact modulation amplitude:

    A_TPI = (4*pi*ln(phi) / (Phi_phi/M_P)) * (Lambda_0^4 / (3*H^2*M_P^2))
          = 7.7 x 10^-4

---

## Citation

If you use this code or the TPI framework in your research, please cite:

```bibtex
@article{TPI2026,
  title={Theory of the Informative Pixel (TPI) 3.1},
  author={TPI Research Group},
  year={2026},
  note={arXiv preprint, forthcoming},
  url={https://github.com/YOUR_USERNAME/tpi-3.1}
}
```

---

## License

- Code: MIT License - free to use, modify, and distribute.
- Paper: CC BY 4.0 - free to share and adapt with attribution.

---

## Contact

- Issues: Open a GitHub issue for bugs or questions.
- Discussions: Use GitHub Discussions for theoretical questions.

"It from bit. Every it - every particle, every field of force, even the
spacetime continuum itself - derives its function, its meaning, its very
existence entirely from binary choices, bits." - John A. Wheeler

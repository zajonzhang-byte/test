# VASP and CINEB Reporting

Use this reference for methods sections, computational-detail checks, and result interpretation involving VASP and CI-NEB/CINEB.

## Minimum Method Details

Report these when available:

- Code: VASP version if known.
- Exchange-correlation functional: for example GGA-PBE.
- PAW potentials and valence treatment for W, H, and He.
- Plane-wave cutoff energy.
- Supercell size and number of W atoms before adding H/He.
- k-point mesh and smearing method.
- Energy and force convergence criteria for static relaxation.
- Whether lattice vectors were fixed or relaxed.
- Defect construction: He_n cluster geometry, H initial/final sites, and reference pristine W.
- CINEB setup: number of images, spring constant if used, climbing image, force convergence, endpoint relaxation, and whether endpoints have the same composition and charge state.

## Energetic Quantities

Do not mix definitions. State the formula used.

Formation energy:

```latex
E_f = E(\mathrm{W}_{N}\mathrm{He}_{n}\mathrm{H}_{m}) - E(\mathrm{W}_{N}) - n\mu_{\mathrm{He}} - m\mu_{\mathrm{H}}
```

Binding energy, one possible convention:

```latex
E_b(\mathrm{H}, \mathrm{He}_{n}) =
E(\mathrm{W}_{N}\mathrm{He}_{n}) + E(\mathrm{W}_{N}\mathrm{H})
- E(\mathrm{W}_{N}\mathrm{He}_{n}\mathrm{H}) - E(\mathrm{W}_{N})
```

Migration barrier:

```latex
E_m = E_{\mathrm{saddle}} - E_{\mathrm{initial}}
```

If the final state is not energetically equivalent to the initial state, report both forward and reverse barriers:

```latex
E_m^{\mathrm{forward}} = E_{\mathrm{saddle}} - E_{\mathrm{initial}},
\quad
E_m^{\mathrm{reverse}} = E_{\mathrm{saddle}} - E_{\mathrm{final}}
```

## CINEB Quality Gate

Before using a barrier in writing, check:

- Initial and final structures are both locally relaxed.
- Image ordering follows the intended H migration path.
- Maximum force on images meets the chosen threshold.
- The saddle image is physically plausible, not an artifact of atom overlap or endpoint mismatch.
- The path does not accidentally include He cluster rearrangement unless that is the intended mechanism.
- For asymmetric paths, the final state energy difference is discussed separately from the saddle barrier.
- Images preserve the same atom indexing and composition.

## Common Writing Errors

- Do not call every NEB calculation "diffusion coefficient"; CINEB gives a migration barrier, not a rate unless a prefactor and temperature model are added.
- Do not compare barriers from different reference states without explaining the reference.
- Do not claim "He blocks H diffusion" unless the barrier/path evidence shows a blocked or raised-barrier route.
- Do not claim electronic bonding from geometry alone. Require charge density, Bader, DOS, ELF, or a cautious statement based on structural/energetic evidence.


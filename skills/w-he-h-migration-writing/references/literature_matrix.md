# Literature Matrix for W-He-H Migration

Use this reference when extracting papers or building the evidence base for a literature review, introduction, or related work section.

## Core Fields

| Field | What to Extract |
|---|---|
| Citation | Title, authors, year, journal, DOI if available |
| Material model | Bulk W, surface W, vacancy, SIA, dislocation, grain boundary, bubble, or interface |
| H/He object | Isolated H, isolated He, interstitial He_n, vacancy-He_m, H-He, H-He-V, bubble |
| Method | DFT/VASP, other DFT, MD, empirical potential, rate theory, experiment |
| Calculation details | Functional, PAW/pseudopotential, supercell size, k-points, cutoff, relaxation convergence, spin if relevant |
| Migration method | NEB/CI-NEB/CINEB, number of images, endpoint states, force criterion, barrier |
| Energetics | Formation energy, binding energy, trapping energy, solution energy, migration barrier, reference states |
| Key finding | One or two sentences, with numerical values only if reported |
| Mechanism | Strain/free volume, electronic interaction, vacancy stabilization, bubble interface, trap mutation, diffusion blocking |
| Relevance to this project | Direct, supporting background, comparison only, or not directly comparable |
| Limitation | What prevents direct comparison with interstitial He_n controlled CINEB results |

## Thematic Buckets

Use these buckets to avoid chronological summaries:

1. Baseline H behavior in W: solution sites, diffusion path, intrinsic migration barrier.
2. He in W: interstitial He, He-He clustering, local strain, and cluster stability.
3. H-He interaction: direct attraction/repulsion, trapping, and cluster energetics.
4. Vacancy-mediated H-He behavior: useful comparison, but not the same defect environment.
5. Bubble and near-surface behavior: relevant for fusion retention, often beyond pure DFT-scale interstitial clusters.
6. Migration-barrier studies: NEB/CINEB evidence, path choices, and force convergence.
7. Multiscale bridge: how DFT barriers feed MD, rate theory, or kinetic Monte Carlo.

## Evidence Weaving Pattern

Write by claim rather than by paper:

`Claim -> evidence from DFT/MD/experiment -> why evidence is comparable or not comparable -> gap -> how the user's CINEB work addresses it.`

Example skeleton:

```markdown
Existing atomistic studies agree that H and He do not behave as independent solutes in W, but the reported interaction depends strongly on the defect environment. Vacancy-centered DFT work shows strong gas trapping inside open-volume defects, whereas interstitial-cluster calculations isolate the effect of local strain and He-He aggregation without a pre-existing vacancy. This distinction matters for migration: vacancy complexes mainly change H retention capacity, while interstitial He_n clusters can also modify the minimum-energy path between neighboring interstitial sites. Therefore, a controlled CINEB comparison around He_1-He_6 is needed to separate trapping from migration-barrier modification.
```


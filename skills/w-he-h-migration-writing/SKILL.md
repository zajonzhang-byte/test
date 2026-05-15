---
name: w-he-h-migration-writing
description: Use this skill for academic writing, literature review, paper planning, methods reporting, results interpretation, and reviewer-style checking for research on hydrogen migration in tungsten affected by interstitial helium clusters. Trigger it for W-H-He, tungsten plasma-facing materials, interstitial He clusters, H trapping or diffusion, VASP first-principles calculations, DFT, CI-NEB/CINEB migration barriers, POSCAR/CONTCAR/OUTCAR based result interpretation, Chinese or English thesis/paper sections, literature matrices, introductions, methods, results, discussion, abstracts, and rebuttal or self-review tasks in this research direction.
---

# W-He-H Migration Writing

## Overview

Use this skill as a domain-specific writing and review workflow for the topic: interstitial helium clusters in tungsten and their influence on hydrogen migration, studied with VASP first-principles calculations and CI-NEB/CINEB.

The skill combines four reusable patterns: citation-grounded literature synthesis, scientific paper extraction, section-by-section manuscript writing, and strict technical self-review. It should produce the user's requested artifact directly, not just a prompt template.

## Source-Aware Defaults

When the user provides a workspace, first inspect the local artifacts before drafting. Prefer these project signals when present:

- `已读/` or `read/`: already processed papers, review drafts, literature matrices.
- `未读/` or `unread/`: papers that may need extraction before synthesis.
- `H-He-IS/`, `FS/`, `He1-6/`, `真空He/`: calculation structures, initial/final states, and VASP outputs relevant to He cluster and H migration.
- `literature_extract.json`, `.xlsx`, `.md`, `.docx`: existing literature notes and draft material.
- `POSCAR`, `CONTCAR`, `OUTCAR`, `OSZICAR`, `INCAR`, `KPOINTS`, `.cif`, `.vasp`: calculation inputs and outputs.

Never invent numerical results. If a barrier, binding energy, formation energy, lattice constant, or convergence criterion is not available in the provided files or notes, mark it as `to be calculated`, `not reported in the provided material`, or ask for the missing data.

## Workflow Decision Tree

1. If the user asks to read or summarize papers, use the paper-extraction workflow and the matrix fields in `references/literature_matrix.md`.
2. If the user asks for a literature review, introduction, or related work, organize by mechanism and evidence, not paper-by-paper. Use `references/writing_patterns.md`.
3. If the user asks for methods, computational details, or CINEB reporting, load `references/vasp_cineb_reporting.md`.
4. If the user asks to explain results, discussion, or mechanisms, connect structure, energy, charge/electron-density evidence, and migration barriers. Use both `references/writing_patterns.md` and `references/vasp_cineb_reporting.md`.
5. If the user asks for a pre-submission check, harsh review, or "is this good enough", use the reviewer checklist in `references/review_quality_gate.md`.
6. If the user asks where the skill came from or how it was composed, cite `references/source_skills.md`.

## Domain Frame

Keep the research frame narrow and precise:

- Material: body-centered cubic tungsten, usually a supercell model of bulk W unless the user specifies surface, grain boundary, dislocation, or vacancy.
- Defect object: interstitial He cluster, preferably written as He_n or He_n-H when H is included. Do not blur this with vacancy-He complexes unless the literature being discussed does.
- Migrating species: H atom or hydrogen isotope proxy. Mention D/T relevance only with isotope caveats.
- Method: VASP DFT for relaxed structures and energies; CI-NEB/CINEB for minimum-energy paths and migration barriers.
- Main question: how He cluster size, local strain, electronic redistribution, and H-He interaction change H site preference, trapping, and migration barrier.

## Literature Synthesis Rules

- Build a literature matrix before drafting whenever enough papers are available.
- Separate first-principles, molecular dynamics, empirical potential, rate theory, and experimental/plasma-exposure evidence.
- Separate interstitial He cluster evidence from vacancy-He, He bubble, surface, dislocation, and self-interstitial-atom evidence.
- Prefer claims like "existing calculations suggest..." over overconfident language such as "it proves...".
- When evidence conflicts, identify whether the difference comes from cluster type, defect environment, temperature, potential/functional, supercell size, charge treatment, or migration path choice.
- End each major section with a technical gap that motivates the user's work.

## Manuscript Writing Rules

For an original paper or thesis section, keep the narrative chain:

1. Fusion plasma-facing W must manage H isotope retention and He-induced damage.
2. H and He are coupled because He clusters/bubbles can alter local strain fields, trap distributions, and migration paths.
3. Many studies emphasize vacancies, surfaces, or bubbles, while interstitial He clusters and their direct effect on H migration remain less resolved.
4. VASP plus CINEB can isolate the atomic-scale migration pathway and barrier change around a controlled He_n cluster.
5. The user's contribution should be stated as a concrete comparison: He_n size/configuration -> H stable site -> migration path -> migration barrier -> mechanistic interpretation.

Use English or Chinese according to the user's target draft. For Chinese thesis writing, prefer precise technical prose over broad praise. Define abbreviations on first use, for example "爬山图像弹性带方法 (climbing image nudged elastic band, CI-NEB)".

## Result Interpretation Rules

When interpreting calculations, look for and report:

- Stable adsorption/interstitial sites for H around He_n.
- H-He distance, W lattice distortion, and local free volume around the cluster.
- Binding, trapping, or solution energy definitions used by the user.
- CINEB initial state, final state, path images, force convergence, and saddle-point image.
- Migration barrier directionality: toward the He cluster, away from it, around it, or between equivalent sites.
- Whether the He cluster raises the barrier by trapping H, lowers it by creating local free volume, or creates asymmetric forward/backward barriers.
- Electronic mechanism only when evidence exists: charge density difference, Bader charge, density of states, electron localization, or bond-length/strain analysis.

## Quality Bar

Before finalizing a draft, check:

- Every number has a source in files, notes, tables, figures, or user-provided text.
- Every comparison uses compatible systems: same defect type, similar cell size, similar reference energy, and comparable migration path.
- CINEB and static relaxation settings are reported separately.
- The text distinguishes "H binding to He_n" from "H migration near He_n".
- The conclusion does not generalize H behavior to D/T retention without stating isotope and fusion-safety caveats.
- The novelty statement is narrow enough to defend.

## References

Load these only when needed:

- `references/literature_matrix.md`: paper extraction fields and W-H-He matrix templates.
- `references/vasp_cineb_reporting.md`: computational-method reporting and CINEB quality gates.
- `references/writing_patterns.md`: section-by-section writing patterns in English and Chinese.
- `references/review_quality_gate.md`: strict review checklist for drafts, methods, and result interpretation.
- `references/source_skills.md`: GitHub sources and design ideas used when composing this skill.

---
name: fusion-materials-literature-review
description: Use this skill for literature review work in nuclear fusion materials, including tungsten plasma-facing materials, reduced-activation steels, ODS steels, SiC/SiC composites, vanadium alloys, high-entropy alloys, liquid metal plasma-facing concepts, irradiation damage, hydrogen and helium effects, tritium retention/permeation, thermal shock, sputtering, transmutation, and review writing in Chinese or English. Use it to plan a review topic, build a paper matrix, synthesize mechanisms instead of listing papers, draft or revise review sections, and check whether a literature review has enough critical analysis.
---

# Fusion Materials Literature Review

## Overview

This skill helps write rigorous literature reviews for nuclear fusion materials. It favors mechanism-centered synthesis over paper-by-paper summaries and keeps the review tied to fusion-relevant service conditions.

## When To Use

Use this skill when the user asks to:

- choose or narrow a literature review topic in fusion materials;
- summarize papers about plasma-facing materials, blanket/structural materials, irradiation damage, hydrogen isotope behavior, helium effects, tritium, thermal loads, sputtering, corrosion, or activation;
- create a literature matrix, review outline, section draft, abstract, introduction, conclusion, or future outlook;
- rewrite a review paragraph so it becomes more analytical;
- check whether a review is only "stacking papers" instead of comparing mechanisms, evidence, and limitations.

## Core Workflow

1. Define the review scope using the MEPMA frame:
   - Material: composition, microstructure, fabrication route, alloying, coating, composite architecture.
   - Environment: neutron irradiation, ion irradiation, plasma exposure, hydrogen/deuterium/tritium, helium, heat flux, coolant/corrosion, magnetic confinement device relevance.
   - Property: retention, permeation, swelling, hardening, embrittlement, thermal conductivity, sputtering yield, recrystallization, fatigue, creep, oxidation/corrosion.
   - Mechanism: defects, bubbles, voids, traps, segregation, phase evolution, transmutation, crack initiation, surface morphology, grain boundary effects.
   - Application: divertor, first wall, blanket, breeding zone, structural component, diagnostic or coating layer.
2. Choose the review type:
   - Narrative review: good for broad thesis chapters and mechanism explanation.
   - Systematic review: good when search strategy, inclusion criteria, and reproducibility matter.
   - Mapping review: good for surveying materials, test conditions, or research gaps.
   - Mini-review: good for a focused mechanism or recent progress section.
3. Build a literature matrix before drafting. If no matrix exists, ask for papers or create a template using `references/literature_matrix_template.md`.
4. Synthesize by mechanism, material class, or service condition. Avoid chronological summaries unless the evolution of the field is itself the argument.
5. Draft sections with a claim-evidence-limitation-transition pattern:
   - Claim: the paragraph's main technical point.
   - Evidence: key studies, conditions, and findings.
   - Limitation: why the evidence is incomplete or not directly comparable.
   - Transition: what this implies for the next mechanism, material, or research gap.
6. Check the draft using `references/review_quality_checklist.md`.

## Fusion Materials Taxonomy

Use this taxonomy to organize topics:

- Plasma-facing materials: W, W alloys, W fiber-reinforced W, W coatings, Be, C/C, liquid Li/Sn/Ga concepts.
- Structural and blanket materials: RAFM steels, ODS steels, Eurofer-type steels, F/M steels, austenitic steels for comparison, V alloys, SiC/SiC composites.
- Emerging materials: refractory high-entropy alloys, nanostructured alloys, multilayer coatings, self-passivating W alloys.
- Cross-cutting mechanisms: displacement damage, helium bubble formation, hydrogen isotope trapping, radiation-induced segregation, transmutation, swelling, hardening, embrittlement, recrystallization, plasma erosion, fuzz formation, cracking.
- Evaluation methods: neutron irradiation, ion irradiation, plasma exposure, high heat flux testing, thermal desorption spectroscopy, permeation tests, TEM, SEM, APT, XRD, nanoindentation, positron annihilation, modeling and multiscale simulation.

## Literature Matrix Fields

When extracting information from papers, prefer fields that make comparison possible:

- citation and year;
- material system and preparation route;
- initial microstructure;
- irradiation or plasma condition, including species, energy, dose/fluence, dose rate, temperature, and exposure time;
- hydrogen isotope or helium condition;
- heat flux, thermal shock, or mechanical loading condition;
- characterization methods;
- main observations;
- proposed mechanism;
- fusion relevance;
- limitations and comparability notes;
- useful quotation or figure/table to revisit.

## Writing Rules

- Do not write a review as "Author A found..., Author B found..., Author C found...". Convert this into "The current evidence suggests..., but the conclusion depends on...".
- Always distinguish neutron irradiation from ion irradiation and explain what each can and cannot prove.
- Always include temperature, dose/fluence, energy, and species when comparing irradiation or plasma studies if the source provides them.
- Treat D, T, and H behavior carefully. Do not casually generalize hydrogen results to tritium retention without noting isotope and safety relevance.
- When discussing tungsten, consider recrystallization, thermal conductivity degradation, helium fuzz, hydrogen isotope retention, cracking, and transmutation.
- When discussing steels, consider activation, swelling, radiation hardening, embrittlement, helium effects, creep/fatigue, and joining/welding issues.
- When discussing SiC/SiC or ceramics, consider irradiation stability, thermal conductivity, hermeticity, joining, corrosion, and tritium permeation.
- End major sections with a technical gap, not a generic sentence.

## Chinese Review Style

For Chinese thesis-style literature reviews:

- Use headings such as "研究背景与意义", "聚变堆服役环境对材料的要求", "候选材料体系研究进展", "辐照损伤与氢氦行为", "关键表征与评价方法", "现有问题与发展趋势".
- Prefer concise analytical transitions: "然而", "相比之下", "值得注意的是", "这一差异可能源于", "现有研究仍受限于".
- Avoid overusing vague praise such as "取得了显著进展" unless the progress is specified.
- Translate technical terms consistently: plasma-facing material as "面向等离子体材料", reduced-activation ferritic/martensitic steel as "低活化铁素体/马氏体钢", tritium retention as "氚滞留", transmutation as "嬗变".

## Useful References

Load these files only when needed:

- `references/literature_matrix_template.md`: table templates for extracting and comparing papers.
- `references/review_quality_checklist.md`: checklist for diagnosing weak synthesis.
- `references/section_patterns.md`: reusable Chinese and English section patterns.


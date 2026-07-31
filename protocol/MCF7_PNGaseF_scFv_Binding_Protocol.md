# Detection of Glycan-Dependent scFv Epitopes on MCF7 Surface Proteins
### Cell-Surface Biotinylation → PNGase F Deglycosylation → Yeast-Display scFv Capture

---

## 1. Overview / Rationale

Live-cell surface biotinylation tags all accessible surface proteins. After lysis, the lysate is split into a **mock** and a **PNGase F**-treated arm to test whether N-glycans are required for scFv recognition. Equal amounts of each lysate are then incubated with a **fixed, defined number of yeast** displaying the scFv of interest; biotin retained on yeast-bound antigen is read out with streptavidin-FITC/PE by **fluorescence microscopy**. A drop in signal in the PNGase F arm relative to mock indicates the scFv epitope is N-glycan-dependent (or that deglycosylation disrupts the relevant conformation).

---

## 2. Materials

**Cells/reagents**
- MCF7 cells, ~80–90% confluent, healthy (low passage)
- Sulfo-NHS-SS-Biotin or Sulfo-NHS-Biotin (EZ-Link, Thermo #A39258 or similar)
- Ice-cold PBS (pH 7.4–7.5; avoid Tris/glycine/amine-containing buffers for biotinylation)
- Quenching buffer: 100 mM glycine or 1× PBS with 100 mM Tris-HCl pH 7.4
- Lysis buffer: 1% NP-40 or 1% Triton X-100, 150 mM NaCl, 50 mM Tris-HCl pH 7.5, 1 mM EDTA, + protease inhibitor cocktail (add fresh)
- PNGase F, recombinant, glycerol-free (NEB #P0705, ≥500,000 U/mL)
- 10× Glycoprotein Denaturing Buffer and 10× G7/NP-40 reaction buffer (NEB kit) — used only if the denaturing protocol is chosen (see 4.2)
- Yeast displaying scFv (induced, e.g., pYD1/EBY100 system)
- Yeast wash/stain buffer: PBS + 0.5–1% BSA (or 0.1% BSA + 2 mM EDTA), pH 7.4, ice-cold
- Streptavidin-FITC or Streptavidin-PE (working conc. ~1–5 µg/mL, titrate)
- BCA/Bradford assay kit for lysate normalization
- Concanavalin A (ConA)-coated glass-bottom 96-well plates, or poly-L-lysine-coated glass slides/coverslips, for immobilizing yeast prior to imaging
- 4% paraformaldehyde (PFA) in PBS (optional, for fixing before imaging)
- Mounting medium (e.g., ProLong Gold or Fluoromount-G; with or without DAPI) if mounting fixed samples on slides
- Hemocytometer or automated cell counter, for precise yeast enumeration

**Equipment**
- **Epifluorescence or confocal microscope** with FITC/PE-appropriate filter sets, fitted with a camera capable of quantitative (non-saturating, linear) image capture
- Image analysis software (Fiji/ImageJ or CellProfiler) for per-cell fluorescence quantification

---

## 3. Surface Biotinylation and Lysis (brief)

1. Wash MCF7 monolayer 2× ice-cold PBS. Keep everything at 4°C from here to prevent internalization of labeled receptors.
2. Incubate with 0.5–1 mg/mL Sulfo-NHS-biotin in PBS, 30 min, 4°C, gentle rocking.
3. Quench unreacted NHS-ester with 100 mM glycine (or Tris) in PBS, 5–10 min, 4°C. Wash 3× ice-cold PBS.
4. Lyse in NP-40/Triton lysis buffer + protease inhibitors, 30 min on ice, vortex intermittently. Clarify lysate 14,000 × g, 10 min, 4°C. Keep supernatant.
5. Quantify total protein (BCA). Normalize all downstream samples to identical µg protein input.

---

## 4. PNGase F Treatment — Core Focus

The single most important design decision is **native vs. denaturing PNGase F digestion**, because the yeast-scFv binding readout requires the antigen to remain in a form the scFv can still recognize (unless you are *specifically* testing whether denaturation itself, independent of deglycosylation, affects binding — in which case run both arms as separate controls, see 4.3).

### 4.1 Recommended default: Non-denaturing (native) digestion
Preserves tertiary structure/conformational epitopes, appropriate when the scFv binds a folded/native antigen (most yeast-display scFv selections are on native or cell-surface antigen).

| Parameter | Condition |
|---|---|
| Detergent | 1% NP-40 (from lysis buffer) — **no SDS, no reducing agent, no heat denaturation** |
| Reaction buffer | 1× G7 buffer (50 mM sodium phosphate, pH 7.5) or PBS if enzyme tolerant |
| PNGase F amount | 2–5 µL (1,000–2,500 U) per 20–50 µg total protein (scale up 2–5× relative to denaturing protocol, since native substrate is deglycosylated less efficiently) |
| Final reaction volume | Keep lysate concentration ≥1 µg/µL; do not over-dilute |
| Temperature | 37°C |
| Time | 16–18 h (overnight), gentle rotation |
| Mock control | Identical volume/composition, enzyme replaced with equal volume of PNGase F storage buffer (or heat-inactivated PNGase F) — **not just "no enzyme," to control for the reaction buffer/dilution** |

### 4.2 Alternative: Denaturing digestion (maximal/complete deglycosylation)
Use only if conformational integrity is not required (e.g., epitope is linear, or you're benchmarking maximal glycan removal by Western/lectin blot in parallel).

| Parameter | Condition |
|---|---|
| Step 1 | Add 1× Glycoprotein Denaturing Buffer (0.5% SDS, 40 mM DTT final), heat 95–100°C, 10 min |
| Step 2 | Cool to RT; add 1× NP-40 (final 1%) and 1× G7 buffer to neutralize SDS |
| PNGase F amount | 1–2 µL (500–1,000 U) per 20 µg protein |
| Temperature/time | 37°C, 1–3 h (reaction is fast and typically complete under denaturing conditions) |
| Mock control | Same denaturation + buffer steps, enzyme omitted/heat-inactivated |

**Caution:** if you use this protocol, the mock sample is also SDS/DTT/heat-treated — this alone can abolish scFv binding to conformational epitopes, confounding interpretation of "PNGase F effect." Only use 4.2 if you independently confirm (e.g., by a denatured-mock vs. native-mock comparison) that denaturation itself does not eliminate scFv binding.

### 4.3 Controls to include regardless of method
- **Mock (vehicle) control:** enzyme storage buffer substituted 1:1, same incubation time/temp — this is the primary comparator for the "PNGase F" arm.
- **Heat-inactivated PNGase F control (optional but recommended):** PNGase F pre-heated 95°C/10 min, added at same volume — controls for nonspecific effects of enzyme protein/buffer components independent of catalytic activity.
- **Digestion efficiency check:** run a small aliquot (~2–5 µg) of mock vs. PNGase F–treated lysate on SDS-PAGE/Western blot (anti-target or streptavidin-HRP) — a downward molecular-weight shift confirms deglycosylation occurred before you commit the rest of the lysate to the yeast-binding assay.
- **Post-digestion normalization:** re-check protein concentration is unaffected by dilution from added buffer/enzyme; equalize input µg to yeast in the next step regardless of which lysate arm.

### 4.4 Stopping the reaction
- Native digestion: no stop needed if proceeding directly to yeast incubation on ice; optionally add PNGase F inhibitor or simply keep on ice/4°C.
- Denaturing digestion: dilute SDS below ~0.05% with lysis/wash buffer before incubating with yeast (residual SDS can lyse/damage yeast and strip surface-displayed scFv).

---

## 5. Yeast-scFv Capture

1. Induce yeast-displayed scFv (standard galactose induction, 20°C, 16–24 h); confirm expression (e.g., anti-c-myc/HA tag stain) by flow before the assay, if a cytometer is available for that QC step (the binding assay itself is read out by microscopy — see Section 7).
2. Wash induced yeast 2× ice-cold PBS/BSA buffer; count on a hemocytometer or automated counter.
3. **Use exactly 2 × 10⁶ yeast cells per condition** (mock lysate, PNGase F lysate, and each control from 4.3), aliquoted from the same induced culture so cell number, induction time, and expression level are matched across arms. This number is chosen to give a dense-but-non-overlapping monolayer of single, individually resolvable yeast cells when ~50–100 µL of the final suspension is plated onto one well of a ConA-coated glass-bottom 96-well plate (or spotted onto a poly-L-lysine slide) — the density needed for reliable per-cell segmentation during image quantification. If your imaging surface has a different area, scale the cell number proportionally and confirm empirically (via a quick pilot image) that cells remain non-overlapping before running the full experiment.
4. Incubate yeast with **equal total protein amount** of mock or PNGase F–treated lysate (normalize µg protein, not volume) in a fixed final volume, 1–2 h, 4°C (or room temp if scFv affinity is low), rotating, protected from light if fluorophores present.
5. Include a no-lysate (buffer only) yeast control (also 2 × 10⁶ cells) to establish streptavidin background/autofluorescence.

---

## 6. Wash, Streptavidin Staining, and Slide Preparation

1. Pellet yeast, 3,000 × g, 3 min, 4°C; wash 3× with cold PBS/BSA buffer, discarding supernatant fully each time (unbound biotinylated protein must be removed).
2. Stain with streptavidin-FITC or streptavidin-PE (pre-titrated concentration, typically 1–5 µg/mL), 20–30 min, 4°C, dark.
3. Wash 3× cold PBS/BSA to remove unbound streptavidin conjugate.
4. Optional fixation: resuspend in 4% PFA/PBS, 10–15 min, RT, dark; wash 2× PBS. Fixation is recommended if slides won't be imaged the same day.
5. Resuspend the full 2 × 10⁶-cell pellet in a fixed, identical volume of PBS/BSA across all conditions (e.g., 100 µL), so plated cell density is comparable between samples.
6. Plate/spot the entire volume onto a ConA-coated glass-bottom well or poly-L-lysine slide; allow yeast to settle and adhere 10–15 min at RT in the dark before imaging. If mounting a fixed sample under a coverslip, use a minimal volume of mounting medium to avoid disturbing the monolayer.

---

## 7. Microscopy Readout and Quantification

1. Using the same microscope, objective, exposure time, gain, and laser/lamp power for **all** samples in an experiment (set exposure on the brightest expected sample — typically the mock/no-PNGase F arm — to just below saturation, then keep it fixed for every other condition), acquire brightfield/DIC and fluorescence (FITC or PE channel) images.
2. Capture **≥5 non-overlapping fields per condition** (more if yeast density is uneven), aiming for ≥100 individually segmentable yeast cells per condition in total.
3. Image analysis (Fiji/ImageJ or CellProfiler):
   a. Use the brightfield/DIC image (or a yeast-autofluorescence/bud-scar channel, if available) to segment individual yeast cells and generate a cell mask, independent of the fluorescence channel — this avoids biasing cell selection toward brighter cells.
   b. Apply the mask to the fluorescence channel and measure mean (or integrated) fluorescence intensity per cell.
   c. Subtract local background (an ROI without cells) from each field.
   d. Export per-cell intensities for each condition.
4. Summarize per condition as mean/median fluorescence intensity across all segmented cells (report n = number of cells and number of independent fields/replicates).
5. **Interpretation:** MFI(PNGase F) < MFI(mock), beyond what's seen in denatured/heat-inactivated controls → scFv-antigen interaction is N-glycan dependent. Comparable MFI between mock and PNGase F → epitope recognition is glycan-independent (confirm digestion worked via the Western blot check in 4.3).
6. Statistics: compare per-cell intensity distributions between conditions (e.g., Mann-Whitney/t-test on cell-level data, or on per-field/per-replicate means if treating each field as the unit of replication — pre-specify which before analysis) across ≥3 independent biological replicates (independent PNGase F digestions/yeast inductions, not just repeated imaging of the same sample).

---

## 8. Quick Troubleshooting Notes
- No signal drop but Western confirms complete deglycosylation → epitope is likely protein-backbone dependent, not glycan-dependent.
- Signal drop in both mock and heat-inactivated-enzyme arms (relative to no-buffer control) → nonspecific effect of dilution/buffer, not true PNGase F activity; re-normalize protein amount and volume across arms.
- Low/no digestion on Western → increase enzyme units and/or extend native-digestion time to 24–48 h rather than switching to denaturing conditions if conformational epitope preservation matters.
- Yeast cells overlapping/clumped in the field, preventing clean segmentation → reduce plated cell number below 2 × 10⁶ (re-titrate empirically for your imaging surface), or add a brief mild sonication/vortex step before plating to break up clumps.
- Uneven illumination or photobleaching across fields → randomize/interleave imaging order across conditions rather than imaging one condition fully before starting the next, and keep total light exposure per field minimal until acquisition.

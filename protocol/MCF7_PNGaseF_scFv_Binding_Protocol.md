# Detection of Yeast-scFv binding to MCF7 cell lysate after PNGase treatment


---

## Overview / Rationale
Cell-Surface Biotinylation → PNGase F Deglycosylation → Yeast-Display scFv Capture

Live-cell surface biotinylation tags all accessible surface proteins. After lysis, the lysate is split into a **mock** and a **PNGase F**-treated arm to test whether N-glycans are required for scFv recognition. Equal amounts of each lysate are then incubated with yeast displaying the scFv of interest; biotin retained on yeast-bound antigen is read out with streptavidin-PE by confocol. A drop in signal in the PNGase F arm relative to mock indicates the scFv epitope is N-glycan-dependent (or that deglycosylation disrupts the relevant conformation).
>"arm" means one experimental group or one branch of an experiment

---

## Materials

**Cells/reagents**
- MCF7 cells, ~80–90% confluent, healthy (low passage)
- Sulfo-NHS-SS-Biotin or Sulfo-NHS-Biotin (EZ-Link, Thermo # MSPP-A39257 )
- Ice-cold PBS (pH 7.4–7.5; avoid Tris/glycine/amine-containing buffers for biotinylation)
- (need prepare)Quenching buffer: 100 mM glycine or 1× PBS with 100 mM Tris-HCl pH 7.4 (75.1mg glycine in 10mL PBS)
- Lysis buffer: #9803 + protease inhibitor cocktail (prepare fresh following [[mcf7_protocols#Cell Lysis]])
- PNGase F, recombinant, glycerol-free (NEB # P0704S)
- 10x Glycobuffer2 (cat# B3704s)
- Yeast displaying scFv (induced)
- Yeast wash/stain buffer: PBS + 0.5–1% BSA, pH 7.4, ice-cold
- Streptavidin-PE (cat# 554061 working conc. ~1–5 µg/mL, titrate)
- BCA/Bradford assay kit for lysate normalization

**Equipment**
- Refrigerated centrifuge (cell pelleting: 300–500 × g; yeast pelleting: 2,500–3,000 × g)
- Rotator/nutator, 4°C and 30°C (yeast) or 37°C (enzyme) capability

---

## Step 1: Surface Biotinylation and Lysis

1. Wash 10 million MCF7 cells ice-cold PBS. Keep everything at 4°C 
2. Incubate with 0.5 mg/mL Sulfo-NHS-biotin in 2mL PBS, 30 min, 4°C, gentle rocking. 
	Take out fresh tube and discard after use
	 In [whole cell biopanning protocol](doi:10.1016/j.ymeth.2012.03.010.), it is 5mL 0.5mg/mL for 25million cells
3. Quench unreacted NHS-ester with 100 mM glycine (or Tris) in PBS, 5–10 min, 4°C. Wash 3× ice-cold PBS. (75.1mg glycine in 10mL PBS)
4. Lyse with 400uL cell lysis buffer (with inhibitor) 15 min on ice, vortex intermittently. Clarify lysate 14,000 × g, 10 min, 4°C. Keep supernatant. [[mcf7_protocols#Cell Lysis]]
	400uL cell lysis buffer is recommended in website for 10million adherent cells
5. Quantify total protein (BCA). Normalize all downstream samples to identical µg protein input. Keep lysate concentration ≥1 µg/µL
	BCA result: 20mg/mL, 400uL

---

## Step2: PNGase F Treatment
Group set:
	PNGase treatment
	mock control
	untreated control
1. Cell lysate: 100ug per group. (Not sure, I added 2000ug cell lysate in my first try)
2. Add 10xGlycoBuffer and 5uL PNGase F, total volume <100uL
3. Incubate 37°C overnight with rotation

| Parameter       | Condition                                               |
| --------------- | ------------------------------------------------------- |
| Detergent       | The cell lysis buffer already have                      |
| Reaction buffer | GlycoBuffer (dilute from x10) or PBS if enzyme tolerant |
| PNGase F        | 2-5 µL (1,000–2,500 U) per 100 µg total protein         |
| Temperature     | 37°C                                                    |
| Time            | 16–18 h (overnight), gentle rotation                    |
| Mock control    | Identical volume/composition in 37 °C                   |

> Native digestion: no stop needed if proceeding directly to yeast incubation on ice; optionally add PNGase F inhibitor or simply keep on ice/4°C.

---
## Step3: Yeast-scFv capture
Group set:
	1. Yeast-scFv
	2. Yeast-scFv + Mock cell lysate (only glycobuffer treatment) 
	3. PNGase treated dilute x10
	4. PNGase treated 50uL
	5. 100ug PNGase 
	6. Yeast-scFv + native cell lysate 
	7.  Yeast without induction + native cell lysate

1. Wash induced yeast with PBS buffer; count and aliquot equal yeast numbers (10⁶ cells) per condition
2. Incubate yeast with equal protein amount in a fixed final volume, 4°C, rotating, protected from light if fluorophores present.
	I incubated 24 h for the first time and it is too long. I highly suspect glycobuffer or PNGase will affect yeast viability. 
---

## Step4: Streptavidin Staining

1. Pellet yeast, 3,000 × g, 3 min, 4°C; wash 3× with PBS, discarding supernatant fully each time (unbound biotinylated protein must be removed).
2. Stain with streptavidin-PE (typically 1–5 µg/mL), 20–30 min, 4°C, dark.
	5uL 0.5mg/mL streptavidin-PE into 1mL PBS -> 2.5 µg/mL
3. Wash 3× PBS to remove unbound streptavidin conjugate.
4. Resuspend in a fixed volume of PBS.

---

## 7. Microscopy Readout
Resuspend the final pellet in PBS and use confocol 35mm dish for confocol imaging
Select Alexa555 or cy3 dye on confocol for PE signal

|                    | **PE spectral properties**                          |
| ------------------ | --------------------------------------------------- |
| **Excitation max** | ~496 nm (secondary peak) and ~565 nm (primary peak) |
| **Emission max**   | ~578 nm                                             |

| Property       | PE      | Alexa Fluor 555 | Cy3     |
| -------------- | ------- | --------------- | ------- |
| Excitation max | ~565 nm | ~555 nm         | ~550 nm |
| Emission max   | ~578 nm | ~565 nm         | ~570 nm |

| Laser line selection            | Suitability                                                                                                                                                                                                                           |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **561 nm (yellow-green laser)** | **Best choice** — sits almost exactly at PE's excitation peak (565 nm), giving optimal excitation efficiency and brightest signal                                                                                                     |
| **488 nm (blue laser)**         | Good alternative, very commonly available on standard confocal systems — PE is efficiently excited here too (it's actually why PE works well on standard FITC/GFP-configured instruments), though somewhat less efficient than 561 nm |
| 532 nm (green laser)            | Also works reasonably well if that's what your system has, intermediate excitation efficiency between 488 and 561                                                                                                                     |

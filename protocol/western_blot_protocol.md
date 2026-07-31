# Western Blot Protocol

## Overview

Western blot detects a specific protein within a complex mixture. Proteins are separated by size via SDS-PAGE, transferred to a membrane, and probed with antibodies specific to the target protein.

**Mechanism:** Sodium dodecyl sulfate (SDS) denatures proteins and coats them with a uniform negative charge, so separation on the gel depends solely on molecular weight — smaller proteins migrate faster toward the positive electrode. After electrophoresis, proteins are electrophoretically transferred from the gel onto a PVDF membrane, then detected by sequential blocking, primary antibody, and secondary antibody (or, as here, a directly conjugated HRP antibody) incubations, followed by chemiluminescent imaging.

**Estimated timeline:**

| Stage | Time |
|---|---|
| Sample preparation (lysis) | ~30–45 min |
| Gel electrophoresis | ~1 h |
| Transfer | ~1–1.5 h (varies by apparatus) |
| Blocking | 1 h |
| Primary antibody | 1 h (RT) or overnight (4°C) |
| Washes + secondary antibody (if needed) | ~1.5–2 h |
| Detection/imaging | ~15 min |

**Equipment needed (not consumed):** SDS-PAGE gel tank and power supply, transfer apparatus (wet or semi-dry), PCR machine or heat block, tabletop centrifuge (4°C capable), sonicator, rocking platform, chemiluminescence imager, pipettes.

**Safety notes:**
- BME (2-mercaptoethanol) is a flammable, foul-smelling reducing agent — handle in a fume hood and keep in the flammable cabinet.
- Methanol (used for PVDF activation and in transfer buffer) is toxic and flammable — use in a ventilated area.
- Wear gloves throughout; SDS and acrylamide gels are irritants.

## Materials and Preparation

| Reagent | Cat# | Storage |
|---|---|---|
| Cell lysis buffer | #9803S | Aliquoted in small tubes, -20 storage room |
| Protease inhibitor | #A32963 (Yanmiao) | 4°C, storage room |
| TGX gel, 4–20% | #4561095 | 4°C fridge B, storage room, on the door |
| Laemmli sample buffer | #1610737 | DNA gel bench shelf |
| 2-mercaptoethanol (BME) | #M3148-25mL | Flammable cabinet |
| Protein ladder | #1610374 | — |
| Running buffer | #1610732 | — |
| PVDF membrane, 0.4 µm | #1212781 | — |
| Filter paper | #88600 | — |
| TBST | #9997S (or prepare, see below) | — |
| SuperSignal West Femto (20 µL) | #34094 | 4°C |

**Antibody needed based on experiment**: primary and secondary

| Antibody | Cat# | Storage |
|---|---|---|
| HRP anti-His antibody | #362613 | — |

**1x TBST (1 L):** 20 mM Tris, 150 mM NaCl, 0.05–0.1% Tween 20
- 20 mL 1 M Tris-HCl (pH 7.5)
- 8.77 g NaCl
- 1 mL Tween-20
- Bring to 1 L with water

**Transfer buffer:** 25 mM Tris base, 192 mM glycine, 20% methanol (v/v), pH ~8.3 (adjust pH before adding methanol)

**1x running buffer (1 L):** 900 mL water + 100 mL 10x running buffer (#1610732)

## 1. Sample Preparation

**Goal:** lyse cells and recover a clarified, quantified protein extract.

1.1. Dilute 10x cell lysis buffer (#9803S) 1:10 in water (900 µL ddH2O + 100 µL 10x cell lysis buffer). Add protease inhibitor (#A32963) fresh, just before use.

1.2. Resuspend 10 million cells in 1 mL diluted lysis buffer. Incubate 10 min at 4°C with rocking, then sonicate to complete cell lysis (short pulses, keep on ice to avoid heat-induced protein degradation).

1.3. Spin down at 14,000 g for 5 min at 4°C to pellet insoluble material (membranes, DNA, debris). Transfer the supernatant to a fresh tube on ice — this is your lysate.

1.4. Determine protein concentration by Bradford or BCA assay so you can normalize loading across samples.

1.5. Storage: aliquot lysate (in loading buffer, if not needed immediately) and store at -80°C; avoid repeated freeze-thaw cycles, which degrade protein quality. If not using the same day, store the raw lysate at -80°C until ready.

**Troubleshooting:** weak or absent signal downstream often traces back to this step — under-lysis, protein degradation from slow thawing, or inaccurate quantification.

## 2. Gel Loading and Electrophoresis

**Goal:** separate proteins by molecular weight. Proteins migrate from the negative electrode toward the positive electrode.

2.1. Prepare reducing sample buffer: 95 µL 2x Laemmli buffer (#1610737) + 5 µL BME (#M3148-25mL). BME reduces disulfide bonds, ensuring full denaturation.

2.2. Mix 10 µL sample buffer with 10 µL sample (20 µL total loading volume) to bring total protein to ~1–2 mg/mL. For the ladder, mix 10 µL Protein ladder (#1610374) with 10 µL sample buffer.

2.3. Denature samples at 95°C for 5 min in a PCR machine. Thaw lysates quickly before use — prolonged time on ice shifts pH and can affect band quality.

2.4. Assemble the gel cassette (TGX gel, #4561095, 4–20%):
- Remove the comb and green tape from the gel.
- Load two gels into the cassette with the shorter side of each gel facing inward.
- Fill the inner chamber (between the two gels) with 1x running buffer, then fill the outer chamber to the 2-gel fill line.
- Check for leaks before loading samples.

2.5. Load 10–40 µg of protein (for a lysate) or 10–500 ng (for purified protein) per well, keeping the amount equal across all samples/lanes. Load the ladder in an outer lane for orientation.

2.6. Run at constant voltage: 124 V, 72 mA, 1 h (same conditions as a DNA gel). Watch the dye front — stop the run once it nears the bottom of the gel or once your target's expected MW has resolved well.

2.7. While the gel runs, prepare 2 L of transfer buffer (see recipe above) so it's ready immediately after the run.

**Troubleshooting:** smeared lanes usually indicate overloading or incomplete denaturation; a bowed ("smiley") gel front often means the voltage was too high or the gel ran too long.

## 3. Transfer to Membrane

**Goal:** electrophoretically move separated proteins from the gel onto a membrane for antibody probing.

**Materials:** SDS-PAGE gel, transfer apparatus, wash buffer (TBST), membrane — nitrocellulose or PVDF, 0.4 µm (#1212781; equivalent commercial options: ab133411, ab133412, ab133413), methanol (for PVDF), filter paper (#88600).

3.1. If using PVDF, activate the membrane by soaking in methanol for ~1 min, then rinse in water, then equilibrate in transfer buffer for 10 min at 4°C. (Nitrocellulose does not require methanol activation — soak directly in transfer buffer.)

3.2. Assemble the transfer "sandwich" in the cassette, from negative to positive electrode: sponge → filter paper → gel → membrane → filter paper → sponge.
- Gel closest to the negative electrode.
- Membrane closest to the positive electrode.
- Roll out any air bubbles with a small roller — trapped bubbles cause blank spots on the membrane.

3.3. Run the transfer (electric field drives proteins from gel onto the membrane, gel side negative, membrane side positive). Keep the apparatus cold (ice block or cold room) if running longer than ~30–45 min, since transfer generates heat.

3.4. Check transfer efficiency:
- Coomassie-stain the post-transfer gel — it should be mostly clear of protein if transfer was efficient.
- Compare the pre-stained ladder on the gel vs. the membrane as a quick visual check that bands transferred.
- Note: Ponceau S staining is not recommended before fluorescent detection, since it can raise background fluorescence even after extensive washing — use a non-fluorescent alternative stain if fluorescent detection is planned. Ponceau S is fine as a quick, reversible check before chemiluminescent (HRP) detection.

**Troubleshooting:** little/no protein on the membrane suggests incomplete transfer (check assembly orientation and current); excess protein remaining on the gel after transfer suggests transfer time was too short or voltage too low.

## 4. Antibody Staining and Detection

**Goal:** specifically label the target protein and visualize it.

**Materials:** blocking buffer (3–5% milk or BSA in TBST, or a non-mammalian protein blocker), wash buffer (TBST, #9997S or prepared), membrane, HRP anti-His antibody (#362613), SuperSignal West Femto (#34094).

4.1. Block the membrane in blocking buffer for 1 h at room temperature with gentle rocking, to prevent nonspecific antibody binding. Use milk or BSA (3–5% in TBST) — check which the specific antibody's datasheet recommends, since some antibodies (e.g., phospho-specific) perform poorly with milk.

4.2. Dilute the HRP anti-His antibody (#362613) in blocking buffer at the manufacturer-recommended dilution.

4.3. Incubate the membrane with the antibody in blocking buffer, with gentle rocking — either overnight at 4°C (typically better signal-to-noise) or 1 h at room temperature (faster, if time-limited).

4.4. Wash the membrane 3x with TBST, 5 min each, with rocking, to remove unbound antibody.

4.5. If using an unconjugated primary antibody instead of a directly HRP-conjugated one, incubate with the appropriate HRP-conjugated secondary antibody (species-matched to the primary) in blocking buffer for 1 h at room temperature with gentle rocking, then repeat the 3x, 5 min TBST washes.

4.6. Prepare SuperSignal West Femto substrate (#34094) fresh (1:1 mix of the two components per manufacturer instructions), apply evenly across the membrane, and incubate ~1–5 min at room temperature, protected from light.

4.7. Image the membrane on a chemiluminescence imager. Start with a short exposure and increase as needed — Femto substrate is very sensitive and can saturate quickly.

**Troubleshooting:**
- High background: increase wash stringency (more washes, longer washes, or add up to 0.1% Tween-20), or dilute the antibody further.
- No signal: confirm transfer efficiency (step 3.4), check antibody dilution/expiration, and verify substrate was mixed correctly and applied before it degrades.
- Multiple/nonspecific bands: increase antibody dilution, extend blocking time, or confirm antibody specificity against the target (e.g., via a knockout/knockdown control).

## Expected Outcome

A clean chemiluminescent image with a single band (or bands, if isoforms/PTMs are expected) at the target protein's predicted molecular weight, with signal intensity roughly proportional to loaded protein amount, and minimal background across the rest of the membrane.

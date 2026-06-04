# SAMBA — Annotation Guide

## Purpose
This guide defines the standardised procedure for annotating blood smear images
to build the SAMBA training dataset.

## Cell classes to annotate

| Class | Label | Description |
|---|---|---|
| Normal erythrocyte | `RBC_normal` | Round, 7–8 µm, central pallor ≤ 1/3 diameter |
| Hypochromic RBC | `RBC_hypo` | Central pallor > 1/2 diameter |
| Microcytic RBC | `RBC_micro` | Diameter < 6 µm |
| Blast cell | `BLAST` | Large, immature, prominent nucleolus, high N/C ratio |
| Platelet | `PLT` | Small fragment, 1–3 µm |
| Atypical cell | `ATYPICAL` | Sickle, schistocyte, ovalocyte |

## Annotation tool
Use **Label Studio** (free, runs offline): https://labelstud.io

## Image naming convention
`[SLIDE_ID]_FIELD[NN].jpg`  — e.g. `HV-001_FIELD01.jpg`

## Minimum per slide
- 10 fields (100× oil immersion)
- ≥ 150 erythrocytes per field
- Annotate ALL visible blasts and platelets per field

## Quality criteria
- Good focus (sharp cell borders)
- Optimal staining (pink-red RBCs, blue-purple nuclei)
- No overlapping cells > 30% of field

# SAMBA — System for Acute Malignancy Blood-smear Analysis

> AI-powered blood smear analysis for acute leukemia screening in resource-limited settings.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Active%20Development-green)]()
[![Country](https://img.shields.io/badge/Country-Mozambique-red)]()
[![INS](https://img.shields.io/badge/Institution-INS%20Mozambique-blue)]()

---

## About

**SAMBA** is a mobile application that uses computer vision and AI to screen for acute hematological malignancies (leukemia, lymphoma) directly from blood smear images captured with a smartphone-adapted optical microscope.

Designed for health units with limited laboratory infrastructure, SAMBA works **fully offline** and requires only:

- A standard optical microscope (100× oil immersion objective)
- An Android smartphone with universal adapter (~$20–30 USD)
- Giemsa or May-Grünwald stained blood smears
- No reagents, no automated analyser, no internet connection

---

## Clinical Targets

| Finding | Method | Alert threshold |
|---|---|---|
| Blast cells | Morphological AI detection | ≥ 5% of WBC |
| Severe anaemia | Chromatic pallor analysis | Hb proxy < 7 g/dL |
| Thrombocytopenia | Platelet count per field | < 50 × 10⁹/L |
| Leucocytosis | WBC estimation | > 50 × 10⁹/L |

### SAMBA Risk Score (0–18 points)

| Score | Alert level | Action |
|---|---|---|
| 0 – 4 | 🟢 Low risk | Clinical surveillance |
| 5 – 9 | 🟡 Suspected | Priority flow cytometry |
| ≥ 10 | 🔴 Urgent | Same-day referral to haemato-oncology |

---

## Repository Structure

```
samba-app/
├── app/                    # Flutter mobile app (Android/iOS)
├── model/
│   ├── training/           # Google Colab training notebooks
│   └── weights/            # Exported TFLite models
├── dataset/
│   ├── annotation_guide/   # Labelling instructions for lab technicians
│   └── metadata/           # Slide metadata (no clinical images)
├── docs/
│   ├── protocol/           # Clinical and ethics protocol (CNBS)
│   └── publications/       # Manuscripts in preparation
├── dashboard/              # Web surveillance dashboard (React)
└── .github/
    └── workflows/          # CI/CD pipelines
```

---

## Institutions

| Institution | Country | Role |
|---|---|---|
| [Instituto Nacional de Saúde (INS)](https://www.ins.gov.mz) | 🇲🇿 Mozambique | Lead institution |
| Universidade Católica de Moçambique (UCM) | 🇲🇿 Mozambique | Co-investigator |
| [Fiocruz / FIOTEC](https://www.fiocruz.br) | 🇧🇷 Brazil | Technical partner |
| [IPO Lisboa](https://www.ipolisboa.min-saude.pt) | 🇵🇹 Portugal | Clinical validation |

---

## Development Roadmap

- [x] Clinical SAMBA Score algorithm (v0.1)
- [x] Annotation protocol (Excel + PDF)
- [x] Visual identity and branding
- [ ] Flutter app — base structure
- [ ] Image capture module (microscope + smartphone)
- [ ] Cell segmentation (OpenCV, offline)
- [ ] Morphological feature extraction
- [ ] AI model training (TFLite, Google Colab)
- [ ] TFLite integration in Flutter app
- [ ] Cloud sync (Supabase, offline-first)
- [ ] Web surveillance dashboard
- [ ] Ethics protocol — CNBS submission
- [ ] Clinical validation study (n = 50, prospective)
- [ ] Scientific publication (STARD 2015)
- [ ] FCT / Wellcome Trust funding submission

---

## Scientific Background

SAMBA builds on five years of programmatic data from the Haemato-Oncology Programme at INS Mozambique, including paediatric and adult leukaemia/lymphoma diagnostics confirmed by flow cytometry (BD FACSLyric DxFlex BC platform).

The image analysis approach adapts open-source models (CellViT, Hover-Net) via fine-tuning on locally annotated blood smear datasets, with TensorFlow Lite for on-device inference.

---

## Contact

**Principal Investigator:** Edson Mongo  
**Institution:** Instituto Nacional de Saúde (INS), Maputo, Mozambique  
**Affiliations:** UCM · CIDE  
**Programme:** Haemato-Oncology · Biosafety · Public Health  

---

## Citation

If you use SAMBA in your research, please cite:

```
Mongo E. et al. (2025). SAMBA: System for Acute Malignancy Blood-smear Analysis.
Instituto Nacional de Saúde, Mozambique. https://github.com/Edson-Mongo/samba-app
```

---

## License

This project is licensed under the MIT License — see [LICENSE](LICENSE) for details.


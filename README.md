# Thymus-Derived Myeloid Education Signatures (MES)

**Thymus-Derived Myeloid Education Signatures Predict Microglial Tolerance Positioning and Are Modulated by Glucocorticoid Stress-Axis Activity**

Sanwal Ahmad Zafar and Wei Qin*

School of Biomedical Engineering, Shanghai Jiao Tong University, Shanghai, China

*Corresponding author: Assoc. Prof. Wei Qin (wqin@sjtu.edu.cn)

---

## Overview

This repository contains the complete analysis pipeline for deriving thymus-based Myeloid Education Signatures (MES) and evaluating their relationship with microglial tolerance positioning across independent human cohorts.

We show that:
- The human thymus encodes eight conserved MES modules (chemokine, ECM/adhesion, axon guidance, and tolerance-associated axes)
- These programs predict microglial functional positioning when transferred to four independent brain cohorts (SEA-AD, Olah, Tuddenham, MS)
- Glucocorticoid receptor (GR) activity negatively modulates MES-tolerance associations
- Findings replicate in Visium spatial transcriptomics and LPS-tolerized microglia

## Notebooks

| Notebook | Description |
|----------|-------------|
| `NB1_Setup_DatasetRegistry.ipynb` | Quality control, dataset curation (19 datasets), environment logging, Supplementary Table S1 |
| `NB2_Aim1_Thymus_NegCtrl_InnateMemory.ipynb` | Single-cell QC of three thymus cohorts, peripheral blood negative control, innate memory datasets |
| `NB3_NMF_MES_Derivation.ipynb` | Consensus NMF (K=8), rank-sweep optimization, cross-cohort module matching, functional enrichment |
| `NB4_Microglia_Transfer_Spatial_Stress.ipynb` | MES projection onto microglia, Visium spatial validation, GR calibration (AUC=0.95), LPS tolerance |
| `NB5_Correlation_MetaAnalysis_Robustness.ipynb` | Donor-level correlations, DerSimonian-Laird meta-analysis, LODO sensitivity, HK robustness, GR-DE |
| `NB6_BiologicalContext_Age_Pathology_Irisin.ipynb` | Age/neuropathology stratification, irisin-pathway scoring, GR x age interaction, threshold sensitivity |

## Setup

### Requirements

```
python >= 3.9
scanpy >= 1.9
anndata >= 0.8
numpy
pandas
scipy
scikit-learn
matplotlib
seaborn
openpyxl
```

### Data

Raw data are publicly available from:
- **Tabula Sapiens Thymus** — [tabula-sapiens-portal.ds.czbiohub.org](https://tabula-sapiens-portal.ds.czbiohub.org/)
- **SEA-AD** — [portal.brain-map.org/explore/seattle-alzheimers-disease](https://portal.brain-map.org/explore/seattle-alzheimers-disease)
- **GEO datasets** — GSE144870, GSE139042, GSE204702, GSE180759, GSE219208, GSE184241, GSE220442

See Supplementary Table S1 for the full dataset catalog with accession numbers.

### Running

1. Clone this repository
2. Download raw data into `data/raw/` following the structure in NB1
3. Update `BASE_DIR` in each notebook to your project root
4. Run notebooks sequentially (NB1 -> NB6)

```bash
git clone https://github.com/Sjtu-Fuxilab/innate.git
cd innate
# Download data, then:
jupyter notebook
```

## Directory Structure

```
innate/
├── NB1_Setup_DatasetRegistry.ipynb
├── NB2_Aim1_Thymus_NegCtrl_InnateMemory.ipynb
├── NB3_NMF_MES_Derivation.ipynb
├── NB4_Microglia_Transfer_Spatial_Stress.ipynb
├── NB5_Correlation_MetaAnalysis_Robustness.ipynb
├── NB6_BiologicalContext_Age_Pathology_Irisin.ipynb
├── README.md
└── LICENSE
```

## License

This project is licensed under the MIT License — see [LICENSE](LICENSE) for details.


# innate

Code for *Thymus-derived myeloid programs track microglial tolerance states across human cohorts*.

The pipeline runs in order, NB1 through NB13. Each notebook reads the outputs of
the earlier ones from a shared project folder and writes tables and figures back
into it. Set `MES_BASE_DIR` (or the `BASE_DIR` at the top of each notebook) to your
project root before running. Raw data are public; accessions are listed in
Supplementary Table S1 and in NB1's registry.

| Notebook | What it does |
|----------|--------------|
| NB1  | Environment setup, dataset registry, Supplementary Table S1 |
| NB2  | QC for the thymus cohorts, blood negative control, innate-memory data |
| NB3  | Consensus NMF on Tabula Sapiens thymus, eight MES modules (K=8) |
| NB4  | MES projection into microglia, spatial validation, GR stress-axis scoring |
| NB5  | Donor-level correlations, random-effects meta-analysis, robustness |
| NB6  | Age, neuropathology and irisin-pathway stratification |
| NB7  | TCGA survival, purity adjustment, marker-stability sensitivity |
| NB8  | Robustness pack: cutoff, HVG, no-priors, purity, mito and Visium checks |
| NB9  | Whether coupling strength tracks neuropathological stage |
| NB10 | Blood-derived module control for tissue specificity |
| NB11 | Multi-tissue specificity (blood, spleen, liver, lung, bone marrow, lymph node) |
| NB12 | Rebuild manuscript tables from pipeline outputs |
| NB13 | Rebuild figure panels from pipeline outputs |

Data are from Gene Expression Omnibus, Tabula Sapiens, and the Allen Institute
SEA-AD portal. See Supplementary Table S1 for the full list.

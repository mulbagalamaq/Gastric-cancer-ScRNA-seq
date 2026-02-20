# Gastric Cancer Peritoneal Fluid scRNA-seq

Reproducing and extending the scRNA-seq analysis from [Sullivan et al. 2024](https://doi.org/10.1038/s41467-024-47683-4) (PMID 38612926) on macrophage gene signatures in gastric cancer malignant ascites.

## Data

GSE228598 — 10 patient samples from peritoneal fluid, 10x Chromium scRNA-seq.

## Analysis

**Part 1** (`scripts/GI_Analysis.Rmd`) — QC, doublet removal (scDblFinder), Harmony integration, broad compartment annotation, macrophage subset with CD68+CD163+ M2 flagging, module scoring (M2TS/M1TS/CTLTS), and Azimuth PBMC reference mapping.

**Part 2** (`scripts/Downstream analysis.Rmd`) — CellChat cell-cell communication inference (triMean), immunosuppressive pathway analysis (MIF, SPP1, GALECTIN, CCL, FN1), sender-receiver heatmaps, ligand-receptor bubble plots.

## Key Findings

- Myeloid cells dominate the peritoneal fluid (~57%), with ~56% co-expressing CD68+CD163+
- M2TS signature enriched in CD68+CD163+ macrophages, replicating the paper's core result
- CD14 monocytes are the dominant signaling hub in the immunosuppressive network
- LGALS9-HAVCR2 (galectin-9/TIM-3) axis drives T cell exhaustion
- FN1→CD44 links the M2TS prognostic signature to functional cell-cell communication

## Tools

R 4.5.2, Seurat v5, Harmony, scDblFinder, Azimuth, CellChat

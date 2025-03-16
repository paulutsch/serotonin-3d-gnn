# Serotonin 3D GNN

Start here: `serotonin-3d-gnn.ipynb`

## Overview

This project is inspired by research from Łapińska et al. (2024): https://doi.org/10.3390/pharmaceutics16030349

The research linked above presents two Quantitative Structure-Activity Relationship (QSAR) models to predict serotonergic binding affinity and selectivity, respectively, using Mordred molecular 2D descriptors. Specifically, one model classifies compounds binarily as "active" or "inactive", with a cutoff of pKi = 7. Another model does multiclass classification to predict the serotonergic selectivity of compounds previously classified as "active".

In this project, 3D molecular graph representations are used as input modality instead of 2D molecular descriptors. The ChEMBL 35 database and RDKit were used to create those representations. A 3D GCN regression model (SeroGCN) is constructed and evaluated, predicting the serotonergic binding affinity of molecules on the 5-HT2A receptor.

## Setup

Install dependencies:

```sh
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

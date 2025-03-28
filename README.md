# Overview
This repository is focused on the Drug-Drug Interaction (DDI) Prediction Task for the Outreachy contribution period on the Ersilia project. 

## File Structure overview
This describes what files are present in the repository.

```bash
.
├── LICENSE
├── README.md
├── data
│   ├── drugbank.tab
│   ├── test.csv
│   ├── train.csv
│   └── valid.csv
├── models
├── notebooks
└── scripts
    └── data_download.py
```

# Project Task
Drug-Drug Interactions (DDIs) occur when two or more drugs interact in a way that affects their effectiveness or safety. These interactions can lead to adverse effects, reduced therapeutic efficacy, or unexpected pharmacological outcomes.
This prediction is a Multi-class classification. The model will be predicting the interaction type when given the SMILES strings of two drugs.

## Dataset Preparation
### DrugBank Multi-Typed DDI Dataset
DrugBank drug-drug interaction dataset is manually sourced from FDA/Health Canada drug labels as well as primary literature. It has 86 interaction types.

### 📂 Details
The dataset is split into three files:
- `test.csv` - Test set
- `train.csv` - Training set
- `valid.csv` - Validation set

### ⚙️ Installation
```py
pip install PyTDC 
```

### 📥 Downloading the Dataset
To download and save the dataset to the _data_ folder, run the next block of code.
```bash
python ./scripts/data_download.py
```

## Featurisation
**Model:** The Continuous and data-driven descriptors representation model from ersilia hub will be used for featurisation. Details about the model can be found [here](https://github.com/ersilia-os/eos7a04).

**Rationale of choice:** 
1. The model extracts meaningful molecular descriptors, on a large dataset of molecular structures which perfectly describes the dataset used in this project.
2. It can generalize better to unseen molecules because it was pretrained on ChEMBL and ZINC and it is less prone to overfitting.
3. The performance is consistent in all experiments.



------
## References
Robin Winter, Floriane Montanari, Frank Noé, Djork-Arné Clevert, Learning continuous and data-driven molecular descriptors by translating equivalent chemical representations. 10.1039/c8sc04175j

Turon, G., Arora, D., & Duran-Frigola, M. Ersilia Model Hub: A repository of AI/ML models for neglected tropical diseases (Version 0.1.42). Zenodo. https://doi.org/10.5281/zenodo.7274645

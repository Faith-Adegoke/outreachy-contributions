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
```py
python ./scripts/data_download.py
```

## Featurisation
**Model:** The Continuous and data-driven descriptors representation model from ersilia hub will be used for featurisation. Details about the model can be found [here](https://github.com/ersilia-os/eos7a04).

**Rationale:** 
 Encodes Molecular Information in a Dense, Continuous Space

Unlike sparse binary fingerprints (e.g., Morgan fingerprints), this neural machine translation-based featurizer learns a compact, meaningful representation of molecular structures.

2️⃣ Captures Chemical and Structural Relationships

Since it is trained on IUPAC to SMILES translation, the intermediate representation contains information about:

Molecular connectivity

Functional groups

Chemical properties

3️⃣ Useful for Deep Learning Models

These low-dimensional continuous vectors are well-suited for deep learning models like Graph Neural Networks (GNNs), Transformers, or Recurrent Neural Networks (RNNs).

4️⃣ Generalizes Well Across Drug Datasets

Pretrained on ChEMBL and ZINC, it can generalize better to unseen molecules in DrugBank, making it useful for DDI tasks where drugs might be novel.



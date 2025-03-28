# Overview
This repository is focused on the Protein-Protein Interaction (PPI) Task for the Outreachy contribution period on the Ersilia project. 
Everything done is according to the tasks specified for interns.

## File Structure overview
This describes what files are present in the repository for easy viewing.

```bash

```

## Project Task
Proteins are the building blocks of life and they usually interact with each other to carry out functions. Identifying this is important in discovering targets to cure diseases, it reduces the time and cost expense in checking for this in the wet lab. Filling in the missing parts of the PPI network can improve human's understanding of diseases and potential disease target.

This prediction is a binary classification. The model will be predicting if a target amino acid sequence pairs interact or not.


## Protein-Protein Interaction Prediction Dataset (HuRI)
The dataset used is from the human reference interactome (HuRI) map. It contains a pairwise combinations of human protein-coding genes to identify which are involved in binary PPI.

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
python ./scripts/data_download.pynb
```


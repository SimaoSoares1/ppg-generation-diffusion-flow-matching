# ppg-generation-diffusion-flow-matching


This repository contains the code developed as part of a master's thesis, gathering the notebooks used for synthetic generation of PPG signals. The work explores and compares two diffusion-based approaches for conditional PPG signal generation — Denoising Diffusion Probabilistic Models (DDPM), with both ancestral and DDIM sampling, and Optimal Transport Conditional Flow Matching (OT-CFM). These are evaluated under a multi-level validation protocol (statistical and physiological fidelity, functional evaluation and cross-domain validation).

## Repository contents

Three distinct datasets were used to train the models, so there are two notebooks per dataset, one for each generative model architecture (DDPM and OT-CFM). Each notebook's name identifies the dataset and the model used, following the pattern `<DATASET>-<MODEL>`. For example, `MIMIC-III-OTCFM.ipynb` and `MIMIC-III-DDPM.ipynb` both correspond to the MIMIC-III dataset, trained with OT-CFM and DDPM respectively.

## Datasets

The data used in this work can be obtained from the following sources:

- **MIMIC-III**: [https://physionet.org/content/mimic-iii-ext-ppg/1.1.0/]. Access requires a credentialed, authenticated PhysioNet account.
- **MIMIC-AF**: [https://www.kaggle.com/datasets/raditya0/mimic-perform-iii-af-and-non-af-dataset]
- **Zenodo v2**: [https://zenodo.org/records/11242869]
- **VitalDB**: [(https://physionet.org/content/vitaldb/1.0.0/)]. Used as a cross-domain test set.

## Running the notebooks

The notebooks are self-contained, as each one is designed to run from start to finish without external dependencies beyond the data and the packages installed in the setup cell itself. They were developed and tested on the Kaggle environment, taking advantage of its GPUs; running them elsewhere may require adjusting paths and hardware configuration.

## Pretrained models

A folder with the already-trained models is also provided, to allow using the notebooks without repeating training, which in some cases takes several hours. To use a pretrained model:

1. Run the notebook normally from the start.
2. Let the training cell start — the first moments are needed for the notebook to define the variables used in subsequent cells.
3. As soon as the training epochs begin running, interrupt the cell's execution.
4. Follow the instructions in the dedicated cell (present in every notebook) explaining how to load the pretrained checkpoint instead of training the model again.

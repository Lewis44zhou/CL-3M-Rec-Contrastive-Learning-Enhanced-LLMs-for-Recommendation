# CL^3M-Rec-Contrastive-Learning-Enhanced-LLMs-for-Recommendation

This repository contains the source code for **CL3M-Rec**, a framework that enhances Large Language Models (LLMs) with contrastive learning for recommendation tasks.

## 📦 Download Large Files
Due to GitHub’s file size limits, large files (e.g., datasets, pre-trained models, processed data) are hosted on Google Drive:

👉 [Google Drive Folder](https://drive.google.com/drive/folders/1dfe2gw2L1ltcK0ogbGejtueFGDJG24cO?dmr=1&ec=wgc-drive-hero-goto)

Please download the files and follow this guideline to run the code。
---

## ⚙️ Getting Started

### 1. Download the files
Download from Google Drive (link provided above).

### 2. Set up the environment
```bash
conda env create -f environment.yml
conda activate cl3mrec
```

### 3. Code Structure
```bash
├── .git/                         # Git repository metadata
│
├── collm-datasets/               # Raw and processed datasets for CoLLM-Rec
├── dataset/                      # Dataset preprocessing scripts
├── figs/                         # Figures used in paper/README
│
├── minigpt4/                     # Core code of CL³M-Rec (built on MiniGPT-4)
│   ├── models/                   # Model architectures (CoLLM, LGCN, MF, SASRec)
│   ├── datasets/                 # Dataset classes and dataloaders
│   ├── task/                     # Task definitions (training/evaluation workflows)
│   ├── runners/                  # Runner for managing training and evaluation
│   ├── common/                   # Utility functions (logging, metrics, helpers)
│   ├── configs/                  # Model & experiment configurations
│   └── __init__.py               # Package initializer
│
├── minigpt4rec-log/              # Training and evaluation logs (tensorboard, checkpoints)
├── train_configs/                # Training configs (YAML files for hyperparameters)
│
├── baseline_train_lightgcn_ood.py        # Baseline training: LightGCN (out-of-domain)
├── baseline_train_lightgcn_ood_amazon.py # Baseline training: LightGCN (Amazon dataset OOD)
├── baseline_train_mf_ood.py              # Baseline training: Matrix Factorization (OOD)
├── baseline_train_mf_ood_amazon.py       # Baseline training: Matrix Factorization (Amazon OOD)
├── baseline_train_sasrec.py              # Baseline training: SASRec
├── baseline_train_sasrec_amazon.py       # Baseline training: SASRec (Amazon dataset)
│
├── environment.yml               # Conda environment configuration
├── train_cl_llm_rec.py           # Main training script for the CL³M-Rec model
├── run_test.py                   # Script to run evaluation on test sets
├── LICENSE                       # License file for the repository
├── README_minigpt4.md                     # Main documentation file
└── requirements.txt              # Python package requirements
├── train_collm_lgcn.py       # Training with LGCN backbone
├── test.json
├── train_collm_lgcn.py       # Training with LGCN backbone
├── train_collm_mf_din.py     # Training with MF + DIN backbone
├── train_collm_sasrec.py     # Training with SASRec backbone
```

### 4. 🚀 Training

The main training entry point is:

```bash
python train_cl_llm_rec.py --config ./train_configs/config.yaml
```

Each config file controls LoRA/CIE tuning stages, datasets, and evaluation metrics. Please adjust them as needed.

### 🙌 Acknowledgements
Our implementation builds upon the structure of MiniGPT-4. We thank the open-source community for their contributions.

```bash
This work was supported by:

Guangdong Provincial Key Laboratory of Intellectual Property and Big Data (2018B030322016)

National Key Research and Development Program of China (2024YFA1011900)

Open Project Program of Guangxi Key Laboratory of Digital Infrastructure (GXDIOP2024011)

Guangxi Key R&D Program (2024AB08144)

NSFC (62276277)
```

### 📑 Citation
If you find this work useful in your research, please cite:
```bash
@inproceedings{zhou2025cl3mrec,
  title     = {CL³M-Rec: Contrastive Learning Enhanced LLMs for Recommendation},
  author    = {Yu-Xuan Zhou and Ru-Bin Li and Zhe Xuan-Yuan and Chang-Dong Wang and Pei-Yuan Lai},
  booktitle = {Proceedings of the IEEE International Conference on Data Mining (ICDM)},
  year      = {2025}
}
```


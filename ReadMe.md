# Self2Seg: Single-Image-Based Unsupervised Joint Segmentation and Denoising

This repository contains a fork of the implementation of the [paper](https://arxiv.org/abs/2309.10511) **"Single-Image-Based Unsupervised Joint Segmentation and Denoising"** by Nadja Gruber et al. The code provides a cleaned version of the framework for performing segmentation and denoising tasks without requiring external supervision, using a single noisy image as input.

---

## Directory Structure

```
Self2Seg/
├── README.md                     # Project documentation
├── Functions_pytorch.py          # Core functions and utilities for PyTorch
├── data_loading.py               # Functions for data preprocessing and loading
├── environment_self2seg.yml      # Conda environment configuration file
├── layer.py                      # Custom layer definitions
├── model_N2F_faster_padding.py   # Noise2Seg model with faster padding implementation
├── noise2seg.py                  # Implementation of Noise2Seg framework
├── run.py                        # Entry point for running the model
└── utils.py                      # General utility functions
```

---

## Installation

### Prerequisites

- Python 3.8 or later
- [Conda](https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html)

### Setup Environment

1. Clone the repository:
   ```bash
   git clone https://github.com/GregoirePetit/Self2Seg.git
   cd Self2Seg
   ```

2. Create the Conda environment:
   ```bash
   conda env create -f environment_self2seg.yml
   ```

3. Activate the environment:
   ```bash
   conda activate self2seg
   ```

---

### Data Preparation

Prepare your noisy images in a folder. Ensure that the `data_loading.py` script points to the correct file path and format for your dataset.

### Running the Model

To train and evaluate the model, use the provided `run.py` script:
```bash
python run.py --output_directory output_directory --input_directory input_directory --image_name image_name --learning_rate learning_rate --method method --lam lam --dataset dataset --number_of_denoisers number_of_denoisers --use_filter use_filter --mu mu --initialization initialization --denoised_provided denoised_provided --initialization_boxes initialization_boxes
```

---

## Acknowledgments

We thank the original authors, Nadja Gruber et al., for their work on the Noise2Seg framework. To cite their work, please refer to the following:

```
@article{gruber2023single,
  title={Single-Image based unsupervised joint segmentation and denoising},
  author={Gruber, Nadja and Schwab, Johannes and Debroux, No{\'e}mie and Papadakis, Nicolas and Haltmeier, Markus},
  journal={arXiv preprint arXiv:2309.10511},
  year={2023}
}
```
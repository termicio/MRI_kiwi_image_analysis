# Kiwi MRI Segmentation

A compact Python project for processing and analyzing kiwi fruit MRI scans. The notebook loads image data, segments fruit, core, and seeds, and evaluates results against a ground truth mask. Outputs include masks, visualizations, and a simple metrics report.

## Features

- Load NIfTI files from `files/` directory
- Preprocess and segment fruit, core, and seeds in 3D
- Compute volumes and counts (seed count, fruit volume, etc.)
- Baseline evaluation using Jaccard index and seed count comparison
- Save segmentation masks and plots to `generated_files/`

## Method

The algorithm normalizes the volume, applies median filtering slice-by-slice, and uses Otsu thresholding adjusted by a factor to isolate the fruit. Core detection finds the largest dark region inside the fruit with 3D morphological closing. Seed segmentation restricts to an eroded interior region, thresholds for dark pixels, and removes small objects. Metrics are calculated from the 3D masks and compared to a provided ground truth mask.

## Requirements

The notebook uses the following Python libraries:

- nibabel
- numpy
- matplotlib
- scikit-image
- scipy
- scikit-learn

Install with:

```bash
pip install nibabel numpy matplotlib scikit-image scipy scikit-learn
```

## Usage

Run the `polaczenie_projekt.ipynb` notebook in a Jupyter environment. Place input files in `files/` and inspect outputs in `generated_files/`. Adjust parameters at the top of the notebook if needed.

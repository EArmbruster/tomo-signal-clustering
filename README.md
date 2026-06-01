# Ribosome Spatial Clustering in Cryo-Electron Tomography

This project explores the 3D spatial distribution of ribosomes identified in a cryo-electron tomogram, applying unsupervised clustering methods to uncover spatial patterns that may reflect functional subpopulations.

## Methods

Three unsupervised clustering approaches are applied and compared:
1. K-Means Clustering
2. DBSCAN (Density-Based Spatial Clustering of Applications with Noise)
3. Agglomerative (Hierarchical) Clustering

## Results

No strongly periodic or regularly spaced subpopulations were identified. One cluster of 16 ribosomes in a high-Z corner of the tomogram showed somewhat distinct spatial cohesion, but overall the CV distribution across clusters did not reveal robust regular-spacing patterns. This suggests that ribosome spatial heterogeneity in this tomogram is not sufficiently structured to be resolved by these methods on coordinate data alone.

Promising future directions include:
- **HDBSCAN** — removes reliance on epsilon and handles variable-density clusters, though it is computationally expensive
- **Gaussian Mixture Models (GMM)** — incorporates priors via the Expectation-Maximization algorithm, well-suited for biological data where prior knowledge exists
- **Other biological targets** — molecules with known geometric packing (e.g., Ryanodine Receptors on the Sarcoplasmic Reticulum in quasi-2D arrays) may show stronger spatial signals

## Data

| Item | Details |
|---|---|
| Source | [EMPIAR-10988](https://www.ebi.ac.uk/empiar/EMPIAR-10988/) |
| Tomogram | TS_026 |
| Input file | `TS_026_cyto_ribosomes.csv` |
| Particles | 838 ribosomes, X/Y/Z coordinates |
| Voxel size | ~13.48 Å (4× binned, 3.3702 Å/px original) |

## Requirements

```
pandas
numpy
matplotlib
scikit-learn
scipy
```

Install with:

```bash
pip install pandas numpy matplotlib scikit-learn scipy
```

## Usage

Open `particle_clustering.ipynb` in Jupyter and run cells sequentially. The input CSV (`TS_026_cyto_ribosomes.csv`) must be in the same directory as the notebook.

## File Structure

```
.
├── particle_clustering.ipynb       # Main analysis notebook
├── TS_026_cyto_ribosomes.csv       # Ribosome coordinate data
└── README.md
```

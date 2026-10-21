# Lithology Prediction Using Well Log Data

This repository contains several classifiers for predicting lithology (facies) from well log data. Each model is evaluated using precision, recall, F1-score, and accuracy. The repository also includes exploratory data analysis of the dataset, with descriptive statistics and plots of the log data.

## Dataset

The dataset comes from a class exercise at the University of Kansas and contains well logs from the Hugoton and Panoma fields, which together make up one of the largest gas fields in North America.

Facies (rock types) were identified from core samples taken every half foot and matched with the logging data at each well location. The feature variables include five wireline log measurements and two geologic constraining variables derived from geological knowledge.

### Features

| Feature | Description |
|---------|-------------|
| `GR` | Gamma ray: gamma emission measured by the wireline logging tool |
| `ILD_log10` | Deep resistivity measurement (log base 10) |
| `PE` | Photoelectric effect log |
| `DeltaPHI` | Neutron-density porosity difference (Phi is the porosity index in petrophysics) |
| `PNHIND` | Average of the neutron and density porosity logs |
| `NM_M` | Nonmarine/marine indicator |
| `RELPOS` | Relative position within the geologic unit |

### Facies (Classes)

The dataset has nine discrete facies:

| Facies | Label | Description | Adjacent Facies |
|--------|-------|-------------|-----------------|
| 1 | SS | Nonmarine sandstone | 2 |
| 2 | CSiS | Nonmarine coarse siltstone | 1, 3 |
| 3 | FSiS | Nonmarine fine siltstone | 2 |
| 4 | SiSh | Marine siltstone and shale | 5 |
| 5 | MS | Mudstone (limestone) | 4, 6 |
| 6 | WS | Wackestone (limestone) | 5, 7 |
| 7 | D | Dolomite | 6, 8 |
| 8 | PS | Packstone-grainstone (limestone) | 6, 7, 9 |
| 9 | BS | Phylloid-algal bafflestone (limestone) | 7, 8 |

> **Note:** Facies are not strictly discrete; they blend gradually into one another, and some neighboring facies are quite similar. Mislabeling between adjacent facies is therefore expected.

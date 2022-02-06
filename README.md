# Heatmap
Uses genomic regions of same size in bed file format into greyscale heatmap.

Author: Mrutyunjaya Parida, David Price Lab, UIOWA

## Usage:
Heatmap program runs on Python 2.7+. It is a linux based, multi-thread capable program with a command line interface. It uses parameters in the parameter file provided by the user to build a heatmap. The program folder contains an installation of bedtools2. Please run HEATMAP_CODE.py from the program folder. The steps used in this program were published in https://pubmed.ncbi.nlm.nih.gov/32597978/.

```
python HEATMAP_CODE.py <PARAMETER FILE> 
                 
Example run: python  HEATMAP_CODE.py PARAMETER.txt                 
```

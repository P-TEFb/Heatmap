# Heatmap
Uses genomic regions of same size in bed file format into greyscale heatmap.

Author: Mrutyunjaya Parida, David Price Lab, UIOWA

## Usage:
Heatmap program runs on Python 2.7+. It is a linux based, multi-thread capable program with a command line interface. It uses parameters in the parameter file provided by the user to build a heatmap. If a PARAMTER.txt file is not provided then the program writes the Parameter description below and exits the run. The program folder contains an installation of bedtools2. Please run HEATMAP_CODE.py from the program folder. The steps used in this program have been published in the following research papers:
https://pubmed.ncbi.nlm.nih.gov/30755505/ ,
and https://pubmed.ncbi.nlm.nih.gov/32597978/.

```
python HEATMAP_CODE.py <PARAMETER FILE> 
                 
Example run: python  HEATMAP_CODE.py PARAMETER.txt                 
```
### Parameter description:
```
Please provide a PARAMETER.txt file containing the following parameters:
REGION= bed file containing genomic regions of the same size.
BEDFILE= bed file containing mapped fragments of variable sizes.
FRAGMENTSIZE= preferred fragment size selection. Users may write All to use fragments of all sizes. Users may be selective such as 35-60,90-200. Here, fragments between 35 to 60bp will be used for one heatmap and 90 to 200bp fragments will be used for another heatmap.
OUTPUTDIR= HEATMAP_CODE.py will create an output folder mentioned here by the user.
STRAND= yes/no. If yes then only strand specific data will be used to make this heatmap. Please make sure to use this option the sixth column of the REGION file must have strand information for all genomic regions.
ORDER= DESC/ASC/RANDOM. This option will sort the REGION file based on the 5th column that represents strength of the genomic regions.
AVGROWS= <int>. This option will average every <int> rows of the total number of genomic regions. If user prefers to average every 10 regions out of a total of 10,000 genomic regions then AVGROWS=10. This will result in a table with 1,000 rows. 
WIDTH= <int>. This option will replicate the columns based on the given value. For example, if all the genomic regions are 500bp in size and WIDTH =2, then each genomic region will be assigned 2 pixels.
HEIGHT= <int>. This option will replicate the rows based on the given value. For example, after averaging if the total number of rows are 1,000 and HEIGHT=2, then each row will be assigned 2 pixels.
BLACK= max or an integer or avgx<int>. This option will assign the darket pixel/s to the max value or a preferred value and above or avgx2 or avgx3 value and above such as the average value of the heatmap table times 2 or 3 and values above it. A gradient from black to white will be assigned to the values lower than the BLACK value. Users may write max or 30 or avgx2. 
GAMMA= default or a decimal such as 0.5. This option allows better contrast between black and white in our images.
```
## Requirements:
Python libraries: ``` joblib, statistics, and glob. ```

This program is designed to run on genomic intervals of same size and mapped fragments of variable sizes in bed file format.

### Output:
An OUTPUTDIR is created by the program where heatmap output TIFF image is submitted along with other files such as the following:

STATISTICS file: showing minimum value pixel,maximum value pixel, average value pixel, and the value at and above which were assigned the darkest pixels in the heatmap. 

Heatmap matrix file: showing the heatmap table without averaging of rows.

Heatmap adjusted matrix file: showing the heatmap table after averaging of rows that are adjusted for the BLACK value based on user preferences.

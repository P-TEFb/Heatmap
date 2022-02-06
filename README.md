# Heatmap
Uses genomic regions of same size in bed file format into greyscale heatmap.

Author: Mrutyunjaya Parida, David Price Lab, UIOWA

## Usage:
Heatmap program runs on Python 2.7+. It is a linux based, multi-thread capable program with a command line interface. It uses parameters in the parameter file provided by the user to build a heatmap. The program folder contains an installation of bedtools2. Please run HEATMAP_CODE.py from the program folder. The steps of this program was published in https://pubmed.ncbi.nlm.nih.gov/32597978/.

```
python DNAfastqtoBigWig.py <URL> \
                 <fastq folder> \
                 <sample #'s> \
                 <min insert> \
                 <max insert> \
                 <# of threads> \
                 <bowtie index> \
                 <chr size file> \
                 <genome assembly> \
                 <sample key>
                 
Example run: python  DNAfastqtoBigWig www.DNA-Seqdata.com /home/xyz-user/fastq-folder 1-10 18 \
             1000 8 /home/xyz-user/genome-bowtie-index /home/xyz-user/genome-chrom.sizes hg38,KF297339.1 samplekey.csv                 
```

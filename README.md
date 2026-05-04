# Holofood remapping
Analysis of the HoloFood chicken data using Drakkar

## Directory structure

- genomes/ -> all MAG fasta files
- holofood_remapping.tsv -> sample names and accession numbers to use for analysis

## Analysis

### 1) Preprocessing of the raw reads

```{sh}
screen -r holofood_remapping
useconda
conda activate drakkar
drakkar preprocessing -f holofood_remapping.tsv -r https://ftp.ncbi.nlm.nih.gov/genomes/all/GCF/016/699/485/GCF_016699485.2_bGalGal1.mat.broiler.GRCg7b/GCF_016699485.2_bGalGal1.mat.broiler.GRCg7b_genomic.fna.gz
```

### 2) Annotation of the MAG catalogue

```{sh}
screen -r holofood_remapping
useconda
conda activate drakkar
drakkar annotating -b genomes/
```

### 3) Quantification of the preprocessed reads

```{sh}
screen -r holofood_remapping
useconda
conda activate drakkar
drakkar profiling -b genomes -r preprocessing/final
```

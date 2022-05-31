<h1 align="center">Convert2PacBioBAM</h1>

***

Convert2PacBioBAM converts FASTA and FASTQ files to PacBio BAM files. To use the IsoSeq v3 pipeline, a file with the reads must be provided in PacBio BAM format, which carries quality information in a specific way. Users cannot always access the IsoSeq3 workflows because the scripts do not accept reads in FASTA or FASTQ format as input. To put a temporary patch to this problem, you can use the `convert_to_pacbio_bam.py` script. Given your reads in FASTA or FASTQ format and a real PacBio BAM file generated with `css` (also supports BAM files after using `lima` and `isoseq refine`), it will "convert" your sequences into a PacBio BAM file using the input file as a template.

## Requirements

- Python (3.7)
- samtools

## Usage

```
usage: convert_to_pacbio_bam.py [-h] [--keep_files] reads bam output

Reformats FASTA and FASTQ files to PacBio BAM files

positional arguments:
  reads         Read sequences in FASTA or FASTQ format
  bam           PacBio real BAM to use as template
  output        Output path and prefix for converted BAM file
                (".converted.bam" suffix will be added")

optional arguments:
  -h, --help    show this help message and exit
  --keep_files  If used the program will not delete intermediate files
```

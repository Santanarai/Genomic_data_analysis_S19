# Bioinformatics Tools Used in This Repository

This document provides a comprehensive list of all bioinformatics tools employed in this genomic data analysis project and their specific purposes.

## **SEQUENCE READ PROCESSING**

- **parallel-fastq-dump** - Downloads FASTQ files from SRA (Sequence Read Archive) database with parallel processing
- **fastq-dump** - Downloads FASTQ files from SRA database
- **fastqc** - Quality control analysis and reports for raw FASTQ sequencing files
- **cutadapt** - Removes adapter sequences from 3' end of reads; removes Illumina universal adapters
- **sickle** - Trims low-quality bases and filters low-quality reads using sliding window approach
- **scythe** - Removes adapter contamination from sequencing reads using FASTA adapter files

## **GENOME ASSEMBLY**

- **ABySS** (Assembly by Short Sequences) - De novo sequence assembler for short reads using k-mer approach
- **SPAdes** (St. Petersburg genome assembler) - De Bruijn graph-based assembler; generates assembly from multiple k-mers
- **MIRA** - Mapper of short reads; used for mapping assembly and genome assembly
- **MITObim** - Mitochondrial baiting and iterative mapping pipeline; reconstructs mitochondrial genomes through iterative assembly
- **Velvet** - De Bruijn graph assembler
- **Trinity** - Transcriptome assembler for RNA-seq data

## **ASSEMBLY QUALITY ASSESSMENT & SCAFFOLDING**

- **QUAST** - Assembly statistics tool; evaluates assembly quality metrics (contigs, N50, total length)
- **SSPACE** (SSAKE with SSPACE extension) - Secondary scaffolding tool; extends and scaffolds pre-assembled contigs
- **AlignGraph** - Rescaffolding tool using reference genomes; improves assembly quality using related genomes as reference
- **Jellyfish** - K-mer counting tool; determines k-mer frequency distribution for genome size estimation
  - **jellyfish count** - Counts k-mer occurrences in sequencing data
  - **jellyfish histo** - Generates k-mer frequency histograms
- **GenomeScope** - Fits mixture models to k-mer profiles for genome size and heterozygosity estimation

## **SEQUENCE ALIGNMENT & COMPARISON**

- **BLAST/BLAST+** - Basic Local Alignment Search Tool; searches for matching sequence regions between query and subject sets
  - **blastp** - Protein vs. protein sequence searches
  - **blastn** - Nucleotide vs. nucleotide searches
  - **blastx** - Nucleotide vs. protein searches
  - **tblastn** - Protein vs. nucleotide searches
  - **tblastx** - Nucleotide vs. nucleotide in protein space
  - **psiblast** - Position-Specific Iterated BLAST
  - **deltablast** - Domain-Enhanced BLAST
  - **rpsblast** - BLAST against profile sets
  - **megaBLAST** - High-speed BLAST for closely-related genomes
- **makeblastdb** - Creates indexed, searchable BLAST databases from FASTA files
- **blastdbcmd** - Tool to query and extract sequences from BLAST databases
- **MUMmer** - Whole genome alignment tool using maximal unique matches
  - **mummer** - Global genome alignment overview
  - **nucmer** - Detailed nucleotide-level alignment
  - **mummerplot** - Visualization of mummer alignment results using GNUplot
- **BLAT** - BLAST-like Alignment Tool for fast sequence alignment

## **READ MAPPING & ALIGNMENT PROCESSING**

- **HISAT2** - Fast and sensitive aligner for mapping sequencing reads to reference genomes
  - **hisat2-build** - Builds genome indices for HISAT2 mapping
- **BWA** (Burrows-Wheeler Aligner) - Maps sequence reads to reference genomes
- **bowtie** - Ultrafast, memory-efficient short read aligner
- **samtools** - Suite of tools for working with SAM/BAM alignment files
  - **samtools view** - Converts and views alignment files
  - **samtools sort** - Sorts alignment files by coordinates

## **GENE/TRANSCRIPT QUANTIFICATION**

- **htseq-count** - Counts reads mapped to genomic features; generates count matrices for differential expression analysis

## **GENOME COMPARISON & SYNTENY ANALYSIS**

- **MCScanX** - Multiple Collinearity Scan; detects syntenic blocks and generates pairwise synteny blocks
- **detect_syntenic_tandem_arrays** - Identifies tandem array duplications in syntenic blocks
- **dissect_multiple_alignment** - Analyzes syntenic blocks into intra- and inter-species components
- **dot_plotter** - Java script generating dot plots for syntenic blocks between chromosomes
- **dual_synteny_plotter** - Java script generating dual synteny plots linking syntenic blocks with lines
- **circle_plotter** - Java script generating circular synteny plots for within and between chromosome comparisons

## **PHYLOGENETIC ANALYSIS**

- **MUSCLE** (Multiple Sequence Comparison by Log-Expectation) - Multiple sequence alignment tool; generates alignments in PHYLIP format for downstream phylogenetic analysis
- **RAxML** (Randomized Axelerated Maximum Likelihood) - Phylogenetic tree construction tool
  - **raxmlHPC-PTHREADS-SSE3** - Constructs maximum likelihood trees with bootstrap support; generates trees with bootstrap values

## **R PACKAGES FOR STATISTICAL & VISUALIZATION ANALYSIS**

- **edgeR** - Bioconductor package for differential expression analysis of gene counts
- **ggtree** - R package for visualizing phylogenetic trees with bootstrap support
- **treeio** - R package for reading and manipulating tree files
- **ggplot2** - Grammar of graphics package for data visualization
- **WGCNA** - Weighted Gene Co-expression Network Analysis package
- **dynamicTreeCut** - Dynamic tree cutting for module identification
- **cluster** - R package for clustering analysis
- **flashClust** - Fast hierarchical clustering implementation
- **Hmisc** - Miscellaneous functions for data analysis
- **reshape** - Data restructuring package
- **foreach** - Loop iteration package
- **doParallel** - Parallel computing backend
- **impute** - Bioconductor package for imputation of missing values
- **plyr** - Data manipulation package
- **gridExtra** - Extra grid graphics functions
- **ggdendro** - Dendrogram visualization with ggplot2
- **RColorBrewer** - Color palette generation
- **fastOC** - Multi-merge HTseq counts function

## **DATA FORMAT & VISUALIZATION TOOLS**

- **GNUplot** - Plotting package for visualizing alignment results
- **sed** - Stream editor for text processing; converts FASTQ to FASTA format

## **DATA COMPRESSION & TRANSFER**

- **wget** - Downloads files from URLs and FTP sites
- **gunzip** - Decompresses gzip files

---

## **TOOL PURPOSE SUMMARY BY ANALYSIS TYPE**

**Read Quality Control**: fastqc, fastq-dump, parallel-fastq-dump, cutadapt, sickle, scythe

**De Novo Assembly**: ABySS, SPAdes, MIRA, MITObim, Velvet, Trinity

**Assembly Optimization**: QUAST, SSPACE, AlignGraph, Jellyfish, GenomeScope

**Sequence Comparison**: BLAST suite, MUMmer, GNUplot, BLAT

**Read Mapping**: HISAT2, BWA, bowtie, samtools

**Genome Synteny**: MCScanX, dot_plotter, dual_synteny_plotter, circle_plotter

**Quantification**: htseq-count

**Phylogenetics**: MUSCLE, RAxML, ggtree, treeio

**Statistical Analysis**: edgeR, WGCNA, plyr, dynamicTreeCut, cluster

**Data Visualization**: ggplot2, RColorBrewer, ggdendro, GNUplot

---

## **WORKFLOW OVERVIEW**

These tools collectively support comprehensive genomic data analysis workflows including:

1. **Read Processing** - Quality control, adapter trimming, and filtering of raw sequencing data
2. **Genome Assembly** - De novo assembly of genomes and transcriptomes
3. **Quality Assessment** - Evaluation and optimization of assembly quality
4. **Comparative Genomics** - Whole genome alignment and synteny analysis
5. **Gene Expression Analysis** - Read mapping, quantification, and differential expression
6. **Phylogenetic Reconstruction** - Multiple sequence alignment and tree construction
7. **Network Analysis** - Gene co-expression network construction and module detection

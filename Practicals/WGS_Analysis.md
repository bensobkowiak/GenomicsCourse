# Genomic Analysis and Phylodynamics Workshop

## Practical Session 1 - Whole genome sequence data analysis and reference-based mapping


Objectives
---

By the end of this activity, you will be able to:<br>
<br>
•	Retrieve genomic sequencing data from online repositories.<br>
•	View and understand short-read sequencing data files (FASTQ format).<br>
•	Inspect FASTQ files using FASTQC and identify potential issues.<br>
•	Clean FASTQ files by trimming low quality bases and removing adapters.<br>
•	Map short-read sequence data to a reference strain.<br>


Required Programs
---

Web Browser<br>
Java <br>
FASTQC <br>
Trimmomatic <br>
Extended Text Viewer (e.g. BBEdit, Notepad++, etc.) - Optional <br>
Burrow-Wheeler Aligner (BWA) <br>
SAMtools/BCFtools <br>
GATK <br>
Tablet <br>


## Activities

[1. Obtaining sequencing data](Obtaining_sequencing_data.md)<br>
<br>
[2. Viewing raw sequence data (FASTQ) files](View_raw_sequence.md)<br>
<br>
[3. Quality control (QC) of FASTQ files](Quality_control.md)<br>
<br>
[4. Cleaning and filtering FASTQ files](cleaning_fastq.md)<br>
<br>
[5. Mapping/aligning sequence data to a reference genome](mapping.md)<br>

Background
---

In the lecture, we introduced whole genome sequencing (WGS) and explained the different forms of sequencing data that can be produced. In this exercise, we will first explore different . Next, we will view some typical WGS data produced from short-read sequencing with Illumina platforms, in the FASTQ format. We will also learn how to interrogate FASTQ files and perform quality control (QC) steps to identify any potential errors or issues that may be found in the raw sequence data. These issues include poor read quality, base call errors, or contamination. We can then use software to fix some of these errors and improve the quality of our sequence data for the next stage of our analysis. Finally, we will align the sequenced reads contained in these cleaned FASTQ files to a reference strain to create an alignment file in the BAM format.

A FASTQ file is essentially a text file that contains the information from each sequenced read that has passed the filtering process on a flow cell. For a single-end read sequencing, one FASTQ file is created for each sample per flow cell lane. For a paired-end run, you will receive two FASTQ files, usually denoted R1 and R2 for the forward and reverse reads, for each sample in each lane. Often, FASTQ files are compressed with the extension *.fastq.gz as they can be very large files (100s MB).

If samples were multiplexed (multiple samples combined and run in the same lane of the sequencer – a cost-effective and efficient strategy), the first step in FASTQ file generation is demultiplexing, which assigns reads to a sample based on the cluster’s index sequence. After demultiplexing, the assembled sequences are written to FASTQ files per sample. You will also receive an associated spreadsheet with statistics including the number of reads that have been assigned to each sample and an additional FASTQ containing all reads that could not be assigned to a sample based on the index sequence, marked “Undetermined_reads.fastq”.

*Tip: If the number of reads assigned to each sample FASTQ is low but the number of reads in the undetermined reads FASTQ is large, there may have been a problem with the indexing by the sequencer.*

Typical short-read sequencing platforms produce reads of ~50 - 350bp, substantially shorter than the complete genome or even the majority of genes. One of the biggest challenges when using short-read sequencing is determining how to arrange the sequenced reads into chromosomes or full genomes. Determining how reads orient is called genome assembly. The most common method of genome assembly from short-read sequencing is called reference mapping or aligning. This approach matches the code in the sequenced reads to a reference genome. A good reference genome would be a single consensus sequence of the same or similar organism as your sequenced sample that has been previously sequenced, hopefully with a high degree of confidence in the code.

Reference-based mapping re-assemble short-reads into full genomes by matching the sequence of the read to an area of the genome with the same or very similar sequence. Bioinformatic tools can also allow for small differences between the read and reference sequence that may be present due to biological variation between the sample and the reference (e.g., SNPs). They will also take into account the base quality scores in the reads to reduce mapping errors and can include paired-end information on the distance and orientation of mate-pairs to better predict stretches of DNA that may be present or absent in the sequence compared to the reference (indels). However, there are regions of the genome that can be difficult to confidently assemble due to repeated motifs (e.g., GC-rich regions) or high-variability that will reduce the chances of matching the sequence of a reads correctly in these areas.


In the practical, we will focus on mapping reads to a reference genome using a specialized alignment program designed to map short reads onto a longer reference sequence, Burrow-Wheeler Aligner (BWA). Other software exist (e.g. Bowtie2, CLC, Novoalign) so it is good to check the capabilities of each program and even test multiple aligners when carrying out analysis. All these programs will produce an alignment file in the Sequence Alignment/Map (SAM) format (H. Li et al. 2009) that can be converted to a Binary Alignment/Map (BAM) format file for storage and use in downstream bioinformatic tools (e.g. variant callers, alignment viewers). The development and improvement of efficient short-read alignment algorithms has made the fast processing of data produced by current sequencing platforms.

*Note: This practical only takes you through reference mapping but another approach of reference-free _do novo_ assembly can be used to assemble genomes. In addition, long-read sequencing (reads of >500bp) can improve assemblies, particularly in difficult to map regions of the genome. Please see further reading for more details of these subjects.*

## Resources for further reading

### Whole genome sequencing: <br>

https://www.sciencedirect.com/topics/neuroscience/whole-genome-sequencing <br>

### De novo assembly: <br>

https://www.nature.com/articles/nmeth.1935 <br>
https://link.springer.com/content/pdf/10.1007/s40484-019-0166-9.pdf <br>
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8279138/ <br>

### Long-read sequencing: <br>

https://www.nature.com/articles/s41592-022-01730-w <br>
https://pubmed.ncbi.nlm.nih.gov/31483244/ <br>





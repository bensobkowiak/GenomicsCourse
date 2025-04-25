# De novo (reference-free) assembly 

De novo assembly is the process of reconstructing genomes from sequencing read data without the use of a reference genome. It involves overlapping and merging reads to form longer contiguous sequences (contigs) that represent the genomic sequence. This process is useful when no suitable reference genome is available or when the goal is to discover novel genomic features, such as structural variations, insertions, or new genes. It is also valuable for assembling organisms with high levels of recombination, as it allows reconstruction of unique genome arrangements without bias from a reference.

We will use a *de novo* assembly software called [Unicycler](https://github.com/rrwick/Unicycler). This program uses an assembly software called [SPAdes](https://github.com/ablab/spades) to   

For this activity, we will use the following files found in your /data/ folder:

- **Kleb1_R1.fastq.gz** and **Kleb1_R2.fastq.gz** – Paired-end 150bp sequence data from _Klebsiella pneumoniae_, collected in Taiwan. These have been inspected and cleaned already.

<br>

1. First we can view the options in Unicycler by simply typing the following command in your terminal:

```bash
unicycler
```

This will display all options for Unicycler:

<img src="Pictures/Unicycler1.jpeg" alt="Description" width="60%"/>

<br>

2. We can then run the main command for Unicycler. This may take a little while to complete as it will test different k-mer lengths (see Lecture 1 for k-mer definition) to produce the optimal assembly. Perhaps run this command over the lunch break:

```bash
unicycler -1 Kleb1_R1.fastq.gz -2 Kleb1_R2.fastq.gz --keep 0 -t 2 -o Kleb1
```

Where the options specified are: 
 
| Option                                         | Description                                                                                                  |
|------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| -1                       | The forward read of short-read paired end sequence data                                                             |
| -2                       | The reverse read of short-read paired end sequence data                                                             |
| --keep                       | The file to keep in the output directory.  0 = only keep final files: assembly (FASTA, GFA and log),                                                             |
| -t                       | The number of threads to use.                                                            |
| -o                       | The name of the output directory                                                             |


3. We will now have the final assembly files for the optimal k-mer length that Unicycler determines using some quality metrics (outlined on the Unicycler Github). These files include:


---

### This is the end of the activities in practical session 1. Navigate back to the homepage for other activities [here](../index.html).

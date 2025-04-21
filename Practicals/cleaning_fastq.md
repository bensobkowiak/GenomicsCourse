# Cleaning and filtering FASTQ files 

Although alignment tools can handle reads with some poor quality bases in a read and ignore junk reads, it can also be helpful to apply some cleaning and filtering steps to improve the quality of the remaining reads and to get a better sense for the good quality reads that remain. 

For instance, the quality of the last few bases of the read can be lower than the rest of the sequence read but we would not want to discard the whole read just because of few low-quality bases at the end. Also some adapter sequences may not have been filtered out after sequencing or there may be some reads that are completely useless from the sequencing run. 

[Trimmomatic](https://academic.oup.com/bioinformatics/article/30/15/2114/2390096) is a fast command line tool that can be used to trim and crop Illumina sequencing data, along with removing adapters and overrepresented sequences. 

The different flags and options for Trimmomatic are as follows:

|         Flag          | Option                                                                                             |
|-------------------------|---------------------------------------------------------------------------------------------------------|
| `ILLUMINACLIP`     | fastaWithAdapters: the path to a fasta file containing all the adapters, PCR sequences, etc.        |
|                         | seedMismatches: a value for the maximum mismatch count which will still allow a full match to be performed.      |
|                         | palindromeClipThreshold: a value for the treshold for how accurate the match between the two 'adapter ligated' reads must be for PE palindrome read alignment. |
|                         | simpleClipThreshold: a value for the treshold for how accurate the match between any adapter etc. sequence must be against a read. |
| `SLIDINGWINDOW`    | windowSize: a value for the number of bases to average across.                                                    |
|                         | requiredQuality: a value for the average quality required.                                                        |
| `LEADING`               | a value for  the minimum quality required to keep a base.                                                |
| `TRAILING`              | a value for  the minimum quality required to keep a base.                                                |
| `CROP`                  | a value for the number of bases to keep, from the start of the read.                                     |
| `HEADCROP`              | a value for the number of bases to remove from the start of the read.                                    |
| `MINLEN`                | a value for  the minimum length of reads to be kept.                                                      |

The format to use a flag is `Flag:Option(s)`.

An example of how to run Trimmomatic is as follows:

```bash
trimmomatic <SE or PE> <fastq file> <output fastq> <options>
```

So for example, a simple command to remove the first 10 bases from the start of the single-end reads of ‘Test1.fastq.gz” and output a file containing these trimmed reads called 'Test1_trimmed.fastq.gz' would be:

```bash
trimmomatic SE Test1.fastq.gz Test1_trimmed.fastq.gz HEADCROP:10
```

A more complex example is to remove an adapter sequence called “Truseq2-PE.fasta” (found in the ./Trimmomatic-0.39/adapters/” folder) from the pair-end read sequencing data ‘Test3_R1.fastq.gz' and ‘Test3_R2.fastq.gz'. We have set the seed mismatches at 2, palindrome clip threshold as 30, and the simple clip threshold as 10. Please note that ‘SE’ has now changed to ‘PE’.

```bash
trimmomatic PE Test3_R1.fastq.gz Test3_R2.fastq.gz\
Test3_R1_paired.fastq.gz Test3_R1_unpaired.fastq.gz\
Test3_R2_paired.fastq.gz Test3_R2_unpaired.fastq.gz\
ILLUMINACLIP:./Trimmomatic-0.39/adapters/TruSeq2-PE.fa:2:30:10
```

Note that we have specified 4 output files: 2 for the 'paired' output where both reads survived the processing, and 2 for 'unpaired' output where a read survived, but the partner read did not.

<br>

#### Please complete the following exercises:

<br>

**Exercise 1.** Inspect “Test1.fastq.gz” using FASTQC.

Question: Given the options in Trimmomatic above, what could you do to improve the sequence data?

Question: Why may this not be suitable for these data?

<br>

**Exercise 2.** Inspect “Test2.fastq.gz” using FASTQC.

Question: Given the options for Trimmomatic, what could you do to improve the sequence data? 

- Please execute a Trimmomatic command that you think may improve the sequence data and produce an output FASTQ called “Test2_trimmed.fastq.gz”.

- Look at the ‘overrepresented sequences’ in “Test2.fastq.gz”. Perform a BLASTN (BLAST nucleotide) search using the following website:

[BLASTN SEARCH](https://blast.ncbi.nlm.nih.gov/Blast.cgi?PROGRAM=blastn&PAGE_TYPE=BlastSearch&LINK_LOC=blasthome)

Question: What is the likely source of the overrepresented sequence? What might this suggest to you?

<br>

**Exercise 3.** Inspect “Test3_1.fastq.gz” and “Test3_2.fastq.gz” using FASTQC.

Question: Given the options for Trimmomatic, what could you do to improve the sequence data? 

- Please write and execute the Trimmomatic command that you think may improve the sequence data and produce output files called “Test3_1_paired.fastq.gz”, “Test3_1_unpaired.fastq.gz”, “Test3_2_paired.fastq.gz”, “Test3_2_unpaired.fastq.gz”.

<br>

**Exercise 4.** Inspect “Test4_1.fastq.gz” and “Test4_2.fastq.gz” using FASTQC.

- Write a command to remove the adapter sequences from these sequence data. (_Tip: you can use the same adapter and parameters as in the example_)


Question: Based on what you have learnt from previous activities and exercises, what can you see are the main issues with these sequence data after removing adapter sequences? What may be the source of these issues? (_Hint: Use BLASTN search and look at Basic sequence stats; M. smegmatis genome is around 7MB in size_)

<br>

Next acitvity: [Mapping/aligning sequence data to a reference genome](mapping.md)

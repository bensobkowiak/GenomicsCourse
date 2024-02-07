# Maximum likelihood timed trees with TreeTime

These first two exercise will take you through different methods for producing time-calibrated trees using the untimed ML tree produced in the last practical. These methods use the existing topology of the input tree and dates at the tips (sequences) to estimate the date of nodes and re-scale branches per unit time.

First, we will use [TreeTime](https://treetime.readthedocs.io/en/latest/tutorials/timetree.html) to produce a timed phylogeny by applying a maximum likelihood approach. This is a powerful tool that will not only infer a timed phylogeny but also run an ancestral reconstruction of sequences, estimate past population demographics, and assess the amount of temporal signal in your data by performing a root-to-tip distance regression.

The following files will be used for this exercise:

- **P1_aligned_masked.fasta** – The aligned multisequence FASTA file of 1788 SARS-CoV-2 sequences downloaded from GISAID and aligned and masked in previous exercises.

- **P1_MLtree.treefile** – The un-timed Maximum Likelihood phylogeny produced from the 1788 SARS-CoV-2 sequences in the previous exercise. This has also been provided for you in the Data folder.

- **P1_dates_location.csv** – A CSV file containing the sequence names (column 1), collection dates (column 2), and location of collection (column 3) for the P1 SARS-CoV-2 sequences.



<br>

### To run TreeTime we will use the following command:

```bash
treetime --tree P1_MLtree.treefile --dates P1_dates_location.csv --aln P1_aligned_masked.fasta --outdir P1_treetime --clock-rate 0.0008 --clock-std-dev 0.0004 --reroot MN908947.3 --coalescent skyline
``` 

<br>

### Where the parameters are as follows: <br>

- --tree = The input un-timed phylogeny. <br>
		- Here we have used a ML tree but any type (parsimony, neighbour-joining) can be used if branch lengths are in substitution per site. <br>
- --dates = A CSV file with tip names and dates (format %Y-%m-%d or decimal year) in the first two columns. <br>
		- These can be collection dates or date of symptom onset. Some dates can be partial or missing. <br>
- --aln = The alignment file used to create the un-timed phylogeny. <br>
		- TreeTime can also take a VCF file as input. <br>
- --outdir = The name to use as the directory to save all output files. <br>
- --clock-rate = A fixed clock rate to use in substitutions/site/time. <br>
		- This can be removed if the clock rate can be confidently estimated from the data. <br>
- --clock-std-dev = The standard deviation on the clock rate in substitutions/site/time. <br>
		- Only to be used if using the --clock-rate parameter. <br>
- --reroot = Re-root the tree to the named sequence. <br>
		- This can also be set to 'oldest' to re-root on the sequence with the oldest date. <br>
- --coalescent = Activates the Kingman Coalescent model. <br>
		- This can be set as constant or skyline, or left blank to run without a tree prior. <br>

There are other parameters that can be included when running TreeTime, for full details please see [here](https://treetime.readthedocs.io/en/latest/tutorials/timetree.html).

<br>

### Explore the output from TreeTime, there will be 11 files in the "P1_treetime" folder:

1. Open "ancestral_sequences.fasta":

_Discuss what we think these sequences are, why are there more sequences (rows) than tips in the tree? <br>_

2. The tree files are saved in the two .nexus files, as well as a plotted tree in PDF format. In FigTree, or using any other tree viewing software, you can open the two .nexus files: <br>

_What is the difference between these trees? <br>_

3. Finally, open the "skyline.pdf" file: <br>

_Let's discuss what we think this plot represents <br>_


More information on the effective population size can be found [here](https://www.sciencedirect.com/topics/earth-and-planetary-sciences/effective-population-size)

<br>

Next activity: [Two-step Bayesian timed trees with BactDating](BactDating.html)

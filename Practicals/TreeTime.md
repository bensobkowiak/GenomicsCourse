# Maximum likelihood timed trees with TreeTime

These first two exercise will take you through different methods for producing time-calibrated trees using the untimed ML tree produced in the last practical. These methods use the existing topology of the input tree and dates at the tips (sequences) to estimate the date of nodes and re-scale branches per unit time.

First, we will use [TreeTime](https://treetime.readthedocs.io/en/latest/tutorials/timetree.html) to produce a timed phylogeny by applying a maximum likelihood approach. This is a powerful tool that will not only infer a timed phylogeny but also run an ancestral reconstruction of sequences, estimate past population demographics, and assess the amount of temporal signal in your data by performing a root-to-tip distance regression.

The following files will be used for this exercise:

- **Taiwan_B117_aligned_masked.fasta** – The aligned multisequence FASTA file of 246 SARS-CoV-2 B.1.1.7 sequences from Taiwan downloaded from GISAID and aligned and masked in previous exercises.

- **Taiwan_B117_MLtree.treefile** – The un-timed Maximum Likelihood phylogeny with bootstrapping produced from the 246 SARS-CoV-2 sequences in the previous exercise. This has also been provided for you in the Data folder.

- **Taiwan_B117_dates.csv** – A CSV file containing the sequence names (column 1) and collection dates (column 2) of the 246 SARS-CoV-2 B.1.1.7 sequences from Taiwan.



<br>

### To run TreeTime we will use the following command:

```bash
treetime --tree Taiwan_B117_MLtree.treefile --dates Taiwan_B117_dates.csv --aln Taiwan_B117_aligned_masked.fasta --outdir Taiwan_B117_treetime --clock-rate 0.0008 --clock-std-dev 0.0004 --reroot MN908947.3 --coalescent skyline
``` 

<br>

Where the parameters are as follows: 
 
| Option                                         | Description                                                                                                  |
|------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| --tree                       | The input un-timed phylogeny. Here we have used a ML tree but any type (parsimony, neighbour-joining) can be used if branch lengths are in substitution per site.                                                            |
| --dates                      | A CSV file with tip names and dates (format %Y-%m-%d or decimal year) in the first two columns.     These can be collection dates or date of symptom onset. Some dates can be partial or missing.                                                        |
| --aln                       | The alignment file used to create the un-timed phylogeny.                                                             |
| --outdir                       | The name to use as the directory to save all output files.                                                            |
| --clock-rate                       | A fixed clock rate to use in substitutions/site/time. This option can be removed if the clock rate can be confidently estimated from the data.                                                          |
| --clock-std-dev                       | The standard deviation on the clock rate in substitutions/site/time. Only to be used if using the --clock-rate parameter.                                                          |
| --reroot                       | Re-root the tree to the named sequence. This can also be set to 'oldest' to re-root on the sequence with the oldest date.                                                         |
| --coalescent                       | Activates the Kingman Coalescent model. This can be set as constant or skyline, or left blank to run without a tree prior.                                                       |

There are other parameters that can be included when running TreeTime, for full details please see [here](https://treetime.readthedocs.io/en/latest/tutorials/timetree.html).

<br>

### Explore the output from TreeTime, there will be 11 files in the "Taiwan_B117_treetime" folder:

1. Open "ancestral_sequences.fasta":

_Discuss what we think these sequences are, why are there more sequences (rows) than tips in the tree? <br>_

2. The tree files are saved in the two .nexus files, as well as a plotted tree in PDF format. In FigTree, or using any other tree viewing software, you can open the two .nexus files: <br>

_What is the difference between these trees? <br>_

3. Finally, open the "skyline.pdf" file: <br>

_Let's discuss what we think this plot represents <br>_


More information on the effective population size can be found [here](https://www.sciencedirect.com/topics/earth-and-planetary-sciences/effective-population-size)

<br>

Next activity: [Two-step Bayesian timed trees with BactDating](BactDating.html)

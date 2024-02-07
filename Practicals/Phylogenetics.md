# Genomic Analysis and Phylodynamics Workshop

## Practical Session 3 - Timed phylogenetic trees


Objectives
---

In this activity you will be carrying out the following analyses:<br>
<br>
•	Ancestral dating of un-timed phylogenies using Maximum Likelihood and Bayesian frameworks <br>
•	Full Bayesian reconstruction of timed phylogenies from sequence data with BEAST2 <br>


Required Programs
---

TreeTime <br>
BactDating (R package) <br>
BEAST2 (BEAUti, BEAST, TreeAnnotator) <br>
Tracer <br>
FigTree <br>

## Activities

[1. Maximum likelihood timed trees with TreeTime](TreeTime.md)<br>
<br>
[2. Two-step Bayesian timed trees with BactDating](BactDating.md)<br>
<br>
[3. Bayesian reconstruction of timed trees with BEAST2](Beast.md)<br>
<br>


Background
---

Timed phylogenetic trees, also known as dated phylogenies or chronograms, introduce the dimension of evolutionary time into traditional phylogenetic analyses. Unlike untimed phylogenetic trees that represent only the branching relationships among taxa, timed trees incorporate temporal information, typically in the form of estimated divergence times. These trees are constructed by combining sequence data with molecular clock models and mutation rates to calibrate the rate of molecular evolution. Timed phylogenetic trees provide a temporal framework for understanding the historical sequence of evolutionary events, enabling researchers to estimate the ages of common ancestors, divergence times, and rates of molecular evolution. 

Two widely used approaches for this task are Maximum Likelihood (ML) and Bayesian methods. Choosing between a ML or Bayesian approach depends on the specific goals of the analysis and the available computational resources. ML methods may be preferred for their speed and simplicity, especially in cases where a quick estimate of the phylogeny is sufficient. Bayesian methods, on the other hand, are advantageous when a more comprehensive exploration of uncertainties and incorporation of prior knowledge is critical for accurate timed tree inference.

A key consideration when building timed trees is the choice of molecular clock model to use. For example, a strict clock assumes a constant rate of molecular evolution across all lineages, while a relaxed clock allows for rate variation among branches. Selecting the appropriate clock model depends on the nature of the data and the evolutionary processes under investigation. Additionally, understanding and incorporating accurate population demography information is vital. Demographic factors, such as changes in population size over time, can significantly impact the accuracy of divergence time estimates. Accurate demographic models help in distinguishing between genetic divergence due to speciation events and that caused by fluctuations in population sizes. For example, you may estimate that the past population has grown in a constant, exponential, or logistic manner. Alternatively, more intricate population demographic patterns may be explored using coalescent theory. Please see the further reading for more information about choosing molecular clock and population demographic models.

This practical will introduce you to three tools that can be used for constructing timed phylogenies. The first two exercises will produce a dated phylogeny using a two-step approach that requires un-timed phylogeny to be constructed first. We will use Maximum Likelihood tree produced in the previous practical as an input and use date information to estimate node dates and re-scale the branch lengths to time. First, [TreeTime](https://treetime.readthedocs.io/en/latest/tutorials/timetree.html) will be used to estimate the dated phylogeny using Maximum Likelihood and next a Bayesian approach will be carried out [BactDating](https://www.ncbi.nlm.nih.gov/pmc/articles/pmid/30184106/). Finally, we will use [BEAST2](https://www.beast2.org) to build a timed phylogeny directly from the sequence data, incorporating more complex models to infer the evolutionary history of our data over time. 




## Resources for further reading

### Molecular clock models: <br>

https://onlinelibrary.wiley.com/doi/10.1111/mec.12953 <br>

### Population demography and coalescent theory

https://www.jstor.org/stable/56120 <br>
https://wakeleylab.oeb.harvard.edu/files/wakeleylab/files/wakeleychaptershortdraft.pdf <br>


### BEAST: <br>

https://taming-the-beast.org <br>


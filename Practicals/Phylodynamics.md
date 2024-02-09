# Genomic Analysis and Phylodynamics Workshop

## Practical Session 4 - Phylogeography and phylodynamic analysis


Objectives
---

In this activity, we will go through the following analyses:<br>
<br>
• Phylodynamic inference in BEAST2 (estimating the effective population size and reproduction number) <br>
• Phylogeographic reconstruction in R <br>
• Testing for SNPs under selection in R <br>
• Performing Genome Wide Association Studies using TreeWAS <br>


Required Programs
---

R <br>
BEAST2 (BeautI, BEAST, TreeAnnotator) <br>
Tracer <br>


## Activities

[1. Phylodynamic analysis in BEAST2](Phylodynamics_beast.md)<br>
<br>
[2. Phylogeography using ancestral state reconstruction](Ancestral_reconstruction.html)<br>
<br>
[3. Testing for selection](Selection.html)<br>
<br>
[4. Genome Wide Association Studies](GWAS.html)<br>
<br>


Background
---

In this practical, we carry out four exercise that will go through a range of analyses that incorporate phylogenetic trees to ask biological and epidemiological questions. We will carry out a phylodynamic analysis using BEAST2 to infer the past population demographics of a TB outbreak and then conduct a phylogeographic analysis to trace the movements of the P1 SARS-CoV-2 variant across the Pacific northwest. Finally, we will identify sites under selection in a TB data before looking for sites that are significantly associated with a given phenotype using GWAS.

Phylodynamics is a specialized field that combines phylogenetics and epidemiology to study the evolutionary dynamics of pathogens over time. BEAST enables the integration of molecular sequence data, demographic information, and temporal aspects to reconstruct the evolutionary history of pathogens. By employing Bayesian methods, BEAST facilitates the estimation of key parameters such as the rates of evolutionary change, the times of divergence, and demographic fluctuations within populations. Phylodynamic analysis can be particularly valuable for tracking the transmission patterns of infectious agents, understanding the impact of population dynamics on pathogen evolution, and unraveling the epidemiological factors influencing the spread of diseases. 

Phylogeography can explore the spatial and temporal dynamics of pathogens, shedding light on their evolutionary history, transmission patterns, and geographic spread. By analyzing genetic sequences sampled from infected individuals or host species across different locations and time points, phylogeographic studies reveal the relationships among pathogen strains and their geographic origins. This approach enables researchers to track the movement of pathogens between regions, identify transmission routes and hotspots, and infer the role of human mobility, environmental factors, and host population dynamics in shaping disease spread.

Identifying sites under selection is a crucial aspect of molecular evolution studies, aiming to pinpoint genomic regions where natural selection has acted, leading to variations in nucleotide or amino acid sequences. Various computational methods are employed to detect such sites, and these approaches typically rely on comparing the rates of synonymous and nonsynonymous substitutions or evaluating the distribution of genetic variation across populations. One such analysis is to identify homoplasies, which are sites with evidence of . Additionally, Genome-Wide Association Studies (GWAS) represent a powerful and widely used approach in genetics and genomics to identify genetic variations associated with complex traits and diseases. In GWAS, researchers analyze the entire genome of individuals to pinpoint single nucleotide polymorphisms (SNPs) or other genetic markers that exhibit statistical associations with particular traits or diseases. By comparing the genetic makeup of individuals with and without the trait of interest, GWAS aims to identify specific genomic regions that contribute to the observed phenotypic variation. 


## Resources for further reading

### [Taming the BEAST](https://taming-the-beast.org)

### [SISMID](https://jessicastockdale.github.io/SISMID2023-transmission-genomics/)


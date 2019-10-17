# Metagenomicspractical
This reposistory contains a practical for learning a metagenomics workflow.
These lessons are aimed at Masters Students in Life Sciences with no or minimal bioinformatics experience.
This practical starts by discussing a metagenomics workflow from a biological context, acquiring sequencing data and genome assembly.
Then, you as a student take over.
You'll extract individual microbial genomes from the metagenome assembly, check their quality, and annotate genes coded in these genomes.
This practical includes the following steps (and depends on the following tools):
* backmapping (bwa+samtools)
* binning (MetaBAT)
* quality control of bins (CheckM)
* taxonomy of bins (BAT)
* annotation (Prokka)
* phylogeny reconstruction (IQTree)

## Installation
If you do this practical without any supervision, you will likely need to install the software needed, and download the data.
I recommend, especially to beginners, to install these tools via conda.
If you have not installed conda, please refer to [the guide for miniconda installation on linux](https://docs.conda.io/projects/conda/en/latest/user-guide/install/linux.html).
Once conda is installed, make sure you have cloned this git repository to your local linux system and navigate to that specific folder in a terminal.

```
git clone https://github.com/lauralwd/metagenomicspractical.git
cd metagenomicspractical
```

Then, you may create an environment with all software required via the following command:

`conda env create --file conda-environment.yml`

You activate the environment by typing:

`conda avtivate metagenomics_practical`

Make sure you learn about how conda works, it is definitely worth your time. You may open the interactive jupyter notebook pages by typing:

`jupyter-notebook jupyter-notebook m1-jupyter_and_bash_basics.ipynb`

This opens a webbrowser showing you a jupyter notebook, if you need to download the data needed for the practical, make sure you follow the commands in `mprepare_download_and_subset_reads.ipynb`


# Learning goals of this practical
After this practical, you can name and explain the steps of a simple metagenomics workflow. Starting at acquiring sequencing data, all the way to annotation of individual draft genomes.
* You can highlight the differences between ‘regular’ genome sequencing data and assemblies versus metagenomic sequencing data and assemblies.
* You can replicate the workflow taken during the practical.
* You can explain the workflow from biological and technical perspectives when either one or both are appropriate. 
* You can design similar workflows for different metagenomic questions.
* You can explain what binning signals are, why they are used and how you used them during the practical.
If not already, you will understand the basics of the bash computer language and be able to run bio-informatic programmes in loops.

# Credits and references
Original practical (version 2017) was made By Margo Schuller and Laura Dijkhuizen. Current version was improved thereupon by [Laura Dijkhuizen](https://www.uu.nl/medewerkers/LWDijkhuizen). The practical is based on a subset of published data, the original paper is published open-access in New Phytologist: 
>Dijkhuizen, L. W., Brouwer, P., Bolhuis, H., Reichart, G. J., Koppers, N., Huettel, B., ... & Wong, G. K. S. (2018). Is there foul play in the leaf pocket? The metagenome of floating fern Azolla reveals endophytes that do not fix N2 but may denitrify. New Phytologist, 217(1), 453-466.

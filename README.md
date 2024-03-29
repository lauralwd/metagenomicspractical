# Metagenomicspractical
This repository contains a practical for learning a metagenomics workflow.
These lessons are aimed at Master's students in Life Sciences with minimal experience in bioinformatics and bachelor level experience in (micro)biology.
This practical starts by discussing a metagenomics workflow from a biological context, acquiring sequencing data and genome assembly.
Metagenome assembly is rather a resource- and time-intensive process; hence I have done this for you already.
Then, you, as a student, take over.
You'll extract individual microbial genomes from the metagenome assembly, check their quality, and annotate genes coded in these genomes.
This practical includes the following steps (and depends on the following tools):
* backmapping (bwa+samtools)
* binning (MetaBAT)
* quality control of bins (CheckM)
* optional: taxonomy of bins (BAT)
* annotation (Prokka)
* phylogeny reconstruction (IQTree)

Answers/prefilled code are available in a separate branch of this github repository called 'example'. 
Renders of the empty and pre-filled workflow are available as a github pages website in the 'gh-pages' branch and online [here](https://lauralwd.github.io/metagenomicspractical/).

## Installation
If you do this practical without any supervision, you will likely need to install the software required and download the data.
I recommend, especially to beginners, to install these tools via conda.
If you have not installed conda, please refer to [the guide for miniconda installation on linux](https://docs.conda.io/projects/conda/en/latest/user-guide/install/linux.html).
For windows users can install conda too on the windows sublayer for linux.
I made a [youtube video](https://youtu.be/ZWQMADZjMGc) on how to do that for interns in our lab, it may help you to get conda running as well.
I encourage you to learn more about how conda works; it is definitely worth your time. 
Once conda is installed, make sure you have cloned this git repository to your local Linux system.
Next, navigate to that specific folder in a terminal.
If you do not have git installed, you can do so via your system package manager (i.e. `apt install git`) or via conda (`conda install git`). 
Alternativelly, download the whole practical as a zip file by clicking the green 'code' button on GitHub.

```
git clone https://github.com/lauralwd/metagenomicspractical.git
cd metagenomicspractical
```

Next, you can create an environment with all software required via the following command:

`conda env create`

The previous command reads the `environment.yml` file to install the exact combination of software I use when teaching this practical.
You activate the environment by typing:

`conda activate metagenomics_practical`

Now you installed all of the software you need and made it ready for use!

Make sure you are in the `metagenomicspractical` folder, and then you may open the interactive Jupyter notebook pages by typing:

`jupyter-notebook`

This opens a web browser showing you an overview of the `metagenomicspractical` folder.
Here you can open any of the Jupyter notebooks. 
If you need to download the required data for the practical, make sure you follow the commands in `m00-prepare_download_and_subset_reads.ipynb`

In some cases, your software installed in conda is not available in the JuPyter notebook environment.
As far as I'm concerned, this is abug of the bash_kernel installed in the JuPyter environment; the python3 kernel does find the executables from the conda environment.
A possible fix is the following.
First, identify in a terminal the path where your conda environment is installed.
This is likely in your home directory: `/home/your-name/miniconda2/envs/metagenomics_practical/bin`
To double check, activate your conda environment like above and find out where any of the software tools we use are situated.
Doing this for metabat2 this looks like so: `which metabat2`.
Next, we take that path to the `bin`  directory, and add it the the `$PATH` system variable. 
Make sure to adapt the next command to your situation: 

```
export PATH=/home/laura/miniconda3/envs/metagenomics_practical/bin:$PATH
```

Next, re-install the bash kernel with this command:
```
python3 -m bash_kernel.install
```

Now run `jupyter notebook` again and check if the software is available to you.
If the problem returns after you closed your terminal, run the former of these two commands again and start JuPyter after.

# Help along the way
When teaching this course during the corona pandemic, I decided to record walkthroughs of the entire practical and post these on youtube.
You can find all video's used for this particular practical in a [youtube playlist](https://www.youtube.com/playlist?list=PLWmKspMOX1oHOzXmJ1wI2eZinzfGqmu90).
The quality of these video's is not great and the content isn't always as brief as it could be, but I hope this helps you along in case you get stuck.

# Learning goals of this practical
After this practical, you can name and explain the steps of a simple metagenomics workflow. 
Starting at acquiring sequencing data, all the way to annotating individual draft genomes.
* You can highlight the differences between 'regular' genome sequencing data and assemblies versus metagenomic sequencing data and assemblies (lecture).
* You can explain parts of the workflow and their interdependencies from biological and technical perspectives.
* You can replicate the workflow taken during the practical on new data sets.
* You can design similar workflows for different metagenomic questions.
* You can explain what binning signals are (lecture), why they are used and how you used them during the practical.
If not already, you will understand the basics of the bash computer language and be able to run bio-informatic programmes in loops.

# Credits and references
Original practical (version 2017) was made By Margo Schuller and Laura Dijkhuizen. 
The current version was improved thereupon by [Laura Dijkhuizen](https://www.lauradijkhuizen.com). 
The practical is based on a subset of published data. 
The original paper is published open-access in New Phytologist: 
>Dijkhuizen, L. W., Brouwer, P., Bolhuis, H., Reichart, G. J., Koppers, N., Huettel, B., ... & Wong, G. K. S. (2018). Is there foul play in the leaf pocket? The metagenome of floating fern Azolla reveals endophytes that do not fix N2 but may denitrify. New Phytologist, 217(1), 453-466. [https://doi.org/10.1111/nph.14843](https://doi.org/10.1111/nph.14843)

The continuation of this project is documented also on github, find more details here: [github.com/lauralwd/azolla_genus_metagenome](https://github.com/lauralwd/azolla_genus_metagenome)

# Bonus exercise: Phylogeny of your bins

Congratulations! You completed the practical and are brave enough to try a bonus! In this exercise, you will:

1. Extract Single Copy Marker Genes from your CheckM run on the Bins you created.
2. Align these SCMGs in a multiple-sequence alignment
  * using MAFFT
  * and using JalView to visualise and check your alignment
3. Create a phylogenetic tree using
  * Fast-tree (quick and dirty)
  * IQ-TREE propper but slower
4. Inspect the tree
  * online via iTOL
  
The entire exercise takes place in a terminal, not in a jupy notebook. So keep this instruction, and open up a terminal!
## Install software
If IQ-TREE and MAFFT need to be installed, install them via conda. I'm assuming you already have CheckM running since it was part of the practical.
  
Check like this:
`iqtree`
 
`mafft -h`
  
If you need to install some software, create a new conda environment Named 'phylogenetics' using the Channel' bioconda'. Install the software you need in this environment.
  
`conda create -n phylogenetics -c bioconda mafft iqtree fasttree`

## Collect SCMG
Now we will collect the single-copy marker genes from checkm.

Adapt the paths according to your situation

`checkm qa data/checkm_outputfolder/Bacteria.ms data/checkm_outputfolder -o 9 -f data/marker_genes.fa`

This file contains many marker genes. Let's have a look at the headers of this fasta. It should look like this:

`>bin.1 NODE_107_length_52641_cov_303.322_ID_32256592 geneId=45;start=49177;end=49635;strand=-1;protlen=153 marker=PF02367.12;mstart=12;mend=135`

There are many different marker genes. We will select one that is present in multiple bins with the following line of bash code. Dissect it to see what each part does

`egrep 'marker=[A-Z0-9.]+' data/marker_genes.fa -o | cut -f 2 -d '=' | sort | uniq -c`

Let's continue with marker `PF01668.13`, which is present in all six bins.  

Extract the sequences of marker `PF01668.13` with grep (read the grep manual and use the `-A' option.
Write the output to the new file `PF01668.13.fasta`.
 
## Align and inspect
Now we will align the protein sequences we have just acquired! 
Use MAFFT (command `mafft -h`) on automatic settings, write your alignment to `PF01668.13.mafft.fasta`

Alignments can differ in quality. Go to [Jalview online](http://www.jalview.org/jalview-js/JalviewJS.shtml) to visualise your alignment.
If an alignment has many gaps, you may need to edit it. 
You will learn more about alignments later in the Introduction to bioinformatics course! 
For now, we will continue with this result.

## Create a tree
We are working with a small alignment, so both Fasttree and IQ-TREE will be very fast. However, if you have large alignments (either long sequences or many sequences), you may want to try Fasttree before investing a long calculation time in IQ-TREE.

### Fasttree
Use the `fasttree` command on default settings to create a tree; this should be near-instantaneous. 

### IQ-TREE
Now use `iqtree` to make another tree

use automatic model selection (no extra options needed

Use iqtree' ultra fast bootstrapping' with 1000 bootstraps.

Note that IQ-TREE generates many output files; you may want to create a new directory, move in there and then run IQ-TREE like this: `iqtree -s ../PF01668.13.mafft.fasta -....` 

## Inspect the tree
Find both tree files, and upload them to [iTOL](https://itol.embl.de). 
Create an account if you haven't yet. You will need it later in the Introduction to bioinformatics course.

Visualise the trees. Have you determined the taxonomy of the Bins with CAT/BAT before? Then you can update the names in the tree. 

Are the trees similar or dissimilar? If they are not, what could you do to be more sure of the phylogeny of these bins?


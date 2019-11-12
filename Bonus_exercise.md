# Bonus exercise: Phylogeny of your bins

Congratualations! You completed the practial and are brave enough to try a bonus! In this exercise you will:

1. Extract Single Copy Marker Genes from your CheckM run on the Bins you created.
2. Allign these SCMGs in a multple-sequence alignment
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
  
If you need to install some sofware, then lets create a new conda environment Named 'phylogenetics' using the Channel 'bioconda', and installing into this environment mafft and iqtree.
  
`conda create -n phylogenetics -c bioconda mafft iqtree`

## Collect SCMG
Now we will collect the single copy marker genes from checkm.

Adapt the paths according to your situation

`checkm qa data/checkm_outputfolder/Bacteria.ms data/checkm_outputfolder -o 9 -f data/marker_genes.fa`

This file contains many marker genes. Lets have a look at the headers of this fasta. It should look like this

`>bin.1 NODE_107_length_52641_cov_303.322_ID_32256592 geneId=45;start=49177;end=49635;strand=-1;protlen=153 marker=PF02367.12;mstart=12;mend=135`

There is many different marker genes, we will select one that is present in multiple bins with the following line of bash code. Disect it to see what each part does

`egrep 'marker=[A-Z0-9.]+' data/marker_genes.fa -o | cut -f 2 -d '=' | sort | uniq -c`

Let's continue with marker `PF01668.13` for it is present in all 6 bins.  

 Extract the sequences of marker `PF01668.13` with grep (read the grep manual and use the `-A`option.
 Write the output to the new file `PF01668.13.fasta`.
 
## Allign and inspect
  
## Create a tree
  
### Fasttree
  
### IQ-TREE
  
## Inspect tree

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


## Allign and inspect
  
## Create a tree
  
### Fasttree
  
### IQ-TREE
  
## Inspect tree

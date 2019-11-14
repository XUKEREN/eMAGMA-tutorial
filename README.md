# eMAGMA-TUTORIAL

This tutorial is a step by step guide on how to use eMAGMA, an approach to conducting eQTL informed gene-based tests by assigning SNPs to tissue-specific eGenes as presented in Gerring et al., 2019a, Gerring et al., 2019b. Here we provide the scripts and files to use the eMAGMA methodology which generates a list of disease-associated eGenes using genome-wide summary statistics. In this tutorial, we will show how to apply eMAGMA using GWAS summary statistics of Major Depression Disorder (MDD) as example data; these summary statistics are publicly available from the Psychiatric Genomic Consortium (PGC) website.

The tutorial is divided into two parts. Part 1 conducts eMAGMA gene-based analysis, this analysis integrates SNP-gene associations from an eQTL reference dataset with GWAS summary statistics. We generated annotation files in which SNPs are assigned to genes based on their association with gene expression.   The SNP-gene associations are tissue specific; hence we can estimate what genes are more highly associated with a disease at the tissue level. Part 2 conducts eMAGMA gene-set analysis, testing for the enrichment of association in co-expression networks. The aim of this analysis is to identify modules (sets of highly correlated genes) that are highly associated with disease risk. Tissue-specific annotation files and co-expression network files (for 48 tissues) are shared as part of this tutorial.   Explanation of the methods and resources used in this tutorial are provided in the publication accompanying this tutorial, Gerring et al., 2009a.


**Requirements** 

This tutorial is executable in Unix, it is assumed that users are familiar with the Unix environment and command line. You can type or copy paste the commands or re-structure them as you wish. This is a hands-on tutorial with minimum theoretical explanations. It is essential that the user reads through the publications that accompany the tutorial (Gerring et al. 2019a, Gerring et al., 2019b) as they provide the theoretical background for the analyses. Knowledge of GWAS and GWA-summary analysis is required. We have previously generated a tutorial on the execution of GWAS analysis through another Github  repository https://github.com/MareesAT/GWA_tutorial (Marees et al., 2018).

*************************************



**Setting Up**


Start by creating an eMAGMA folder with all the files we will use throughout the tutorial.
       
       cd /path/to-yourworking folder
        mkdir eMAGMA
        cd eMAGMA
        
The analysis is done using MAGMA v1.07b (de Leeuw, Neale, Heskes, & Posthuma, 2016). MAGMA and auxiliary files can be downloaded from the program website: https://ctg.cncr.nl/software/magma. Two auxiliary files are required: a file with gene locations for protein-coding genes from NCBI and a genome reference file. For this tutorial we use build 37(hg19) that matches the build of the summary data (MDD2018_excluding23andMe) and the reference file for the European population. Gene location files for build 36, 37, & 38 are available from the MAGMA website. You can use wget o curl to import the files directly into your directory, for example:



*MAGMA*
    
    wget https:// https://ctg.cncr.nl/software/MAGMA/prog/magma_v1.07b_static.zip

*Auxiliary files for 37(hg19)*
        
    wget https://ctg.cncr.nl/software/MAGMA/aux_files/NCBI37.3.zip

*Reference data*
    
    wget https://ctg.cncr.nl/software/MAGMA/ref_data/g1000_eur.zip

*GWAS summary = MDD2018_ex23andMe from PGC web site*
        
        wget https://www.med.unc.edu/pgc/results-and-downloads/mdd/
        
        

Notice: If you are using your own data, make sure to download the auxiliary files that correspond to the genome build of your data.

This tutorial provides gene annotation and co-expression networks for 48 tissues, including 13 brain tissues and whole blood. At the end of the tutorial you will be able to apply the eMAGMA approach to your own data using these files.



****************************************************
**LIST OF FILES SHARED WITH THIS TUTORIAL:**



**eMAGMA Annotation files (for 48 tissues) are distributes in the following 6 folders**

*Batch1.annotation*

*Batch2.annotation*

*Batch3.annotation*

*Batch4.annotation*

*Batch5.annotation*

*Batch5.annotation*

**eMAGMA Co-expression network files (for 48 tissues)**

*network_files.zip*

**Tutorial Output files**

*Amygdala_outputs*


*************************************

Now that you have all the necessary files go to **Part 1** to begin the analysis.




****************************************



**References**

**a** eMAGMA: An eQTL-informed method to identify risk genes using genome-wide association study summary statistics.

**b** Gerring ZF, Gamazon ER, Derks EM, for the Major Depressive Disorder Working Group of the Psychiatric Genomics Consortium (2019) A gene co-expression network-based analysis of multiple brain tissues reveals novel genes and molecular pathways underlying major depression. PLOS Genetics 15(7): e1008245. https://doi.org/10.1371/journal.pgen.1008245*

Marees, AT, de Kluiver, H, Stringer, S, et al. A tutorial on conducting genome‐wide association studies: Quality control and statistical analysis. Int J Methods Psychiatr Res. 2018; 27:e1608. https://doi.org/10.1002/mpr.1608

de Leeuw C, Mooij J, Heskes T, Posthuma D (2015): MAGMA: Generalized gene-set analysis of GWAS data. PLoS Comput Biol 11(4): e1004219. doi:10.1371/journal.pcbi.1004219 

RNAseq
===========================


## Table of Contents  

* [General](#General)
    * [Duplicates](#duplicates)


# General

### Duplicates

 Duplicate reads are defined as originating from a single fragment of DNA. Duplicates can arise during sample preparation e.g. library construction using PCR (PCR duplication artifacts); single amplification cluster, incorrectly detected as multiple clusters by the optical sensor of the sequencing instrument (optical duplicates).
 [Intereting reading](https://training.galaxyproject.org/archive/2022-02-01/topics/introduction/tutorials/galaxy-intro-ngs-data-managment/tutorial.html)

   * PCR duplicate artifacts
   Should we remove them. Short answer: **NO** excepted when using UMIs (e.g. deep sequencing / single cell / etc)  
   [details here](https://dnatech.genomecenter.ucdavis.edu/faqs/should-i-remove-pcr-duplicates-from-my-rna-seq-data/)


   * optical duplicates  
    Optical, or more broadly Sequencing, duplicates are duplicates that appear clustered together spatially during sequencing and can arise from optical/imagine-processing artifacts or from bio-chemical processes during clonal amplification and sequencing

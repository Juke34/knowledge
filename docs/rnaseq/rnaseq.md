## Library types

 Here a figure describing the different RNA-seq library types:

 <img align="center" src="../library_types.jpg"  />

If you don't know the library type of your data you can use [GUESSmyLT](https://github.com/NBISweden/GUESSmyLT)

## Library prep methods:

| kit | Description | Paired | Stranded | Strand according to mRNA | Strand according to `first strand`|
| --- | --- | --- | --- | --- | ---
| TruSeq RNA Sample Prep kit  | | yes | No | | fr-unstranded |
| SMARTer ultralow RNA protocol | | yes | No | | fr-unstranded |
| All dUTP methods, NSR, NNSR | | yes | Yes | RF | fr-firststrand
| TruSeq Stranded Total RNA Sample Prep Kit | | yes | Yes | RF | fr-firststrand
| TruSeq Stranded mRNA Sample Prep Kit | | yes | Yes | RF | fr-firststrand
| NEB Ultra Directional RNA Library Prep Kit | | yes | Yes | RF | fr-firststrand
| Agilent SureSelect Strand-Specific | | yes | Yes | RF | fr-firststrand
| Directional Illumina (Ligation) | | yes | Yes | FR | fr-secondstrand
| Standard SOLiD | | Yes | yes | FR | fr-secondstrand
| ScriptSeq v2 RNA-Seq Library Preparation Kit | | yes | Yes | FR | fr-secondstrand
| SMARTer Stranded Total RNA | | yes | Yes | FR | fr-secondstrand
| Encore Complete RNA-Seq Library Systems  | | yes | Yes | FR | fr-secondstrand
| NuGEN SoLo  | | yes | Yes | FR | fr-secondstrand
| Illumina ScriptSeq| |  yes | Yes | FR | fr-secondstrand
| SOLiD mate-pair protocol | | | | | ff

--rf orientation are produced using the Illumina mate-pair protocol?

## Duplicates

 Duplicate reads are defined as originating from a single fragment of DNA. Duplicates can arise during sample preparation e.g. library construction using PCR (PCR duplication artifacts); single amplification cluster, incorrectly detected as multiple clusters by the optical sensor of the sequencing instrument (optical duplicates).
 [Intereting reading](https://training.galaxyproject.org/archive/2022-02-01/topics/introduction/tutorials/galaxy-intro-ngs-data-managment/tutorial.html)

   * PCR duplicate artifacts
   Should we remove them. Short answer: **NO** excepted when using UMIs (e.g. deep sequencing / single cell / etc)  
   [details here](https://dnatech.genomecenter.ucdavis.edu/faqs/should-i-remove-pcr-duplicates-from-my-rna-seq-data/)


   * optical duplicates  
    Optical, or more broadly Sequencing, duplicates are duplicates that appear clustered together spatially during sequencing and can arise from optical/imagine-processing artifacts or from bio-chemical processes during clonal amplification and sequencing


Tool to perform duplicates analysis (mark, remove): [MarkDuplicates (Picard)](https://gatk.broadinstitute.org/hc/en-us/articles/360037052812-MarkDuplicates-Picard-)  
Merge read and remove duplicates? [See here](https://www.biostars.org/p/347514/)

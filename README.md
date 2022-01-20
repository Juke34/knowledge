
Knowledge: collection of cheat Sheets / overviews / summaries 
===========================


## Table of Contents  

* [Programming](#programming)
    * [Git](git.md)
    * [Bash](#bash)
    * [Perl](#perl)
    * [Python](#python)
    * [R](r.md)
* [Cluster](#cluster)
    * [Schedulers: LSF,Torque,SGE,Slurm,etc](#schedulers-lsftorquesgeslurmetc)
    * [Slurm](#slurm)
    * [Rackham](#rackham)
    * [Screen](#screen) 
* [File format](#file-format)
    * [SUGAR](sugar.md)
    * [VULGAR](vulgar.md)  
    * [CIGAR](cigar.md)  
    * [GFF and GTF](gxf.md)
    * [BAM and SAM](https://samtools.github.io/hts-specs/SAMv1.pdf)  
    * MD tag in bam format  
      * [MD Tags in BAM Files](https://github.com/vsbuffalo/devnotes/wiki/The-MD-Tag-in-BAM-Files)   
      * [The history the MD tag and the CIGAR X operator](http://lh3.github.io/2018/03/27/the-history-the-cigar-x-operator-and-the-md-tag)
    * Markdown syntax
      * [Git Markdown](https://guides.github.com/features/mastering-markdown/)
      * [Anchors in Git Markdown](anchors-in-markdown.md)
    * Wiki syntax
      * [textile](https://textile-lang.com) - Used by Redmine
    * External ressource about many different formats
* [Converting](#converting)
    * [gff to gtf](#gff-to-gtf)
    * [gff to bed](#gff-to-bed)
* [Statistics](#statistics)
    * [general](statistics.md)
* [Others](#others)
    * [MinHash](#minhash)
    * [Annotation tools](#annotation-tools)
        * [Genome (protein coding genes)](#genome-protein-coding-genes)
        * [Mitochondrion](#mitochondrion)
        * [Chloroplast](#chloroplast)
        * [Plasmid](#plasmid)
    * [Overview of RNA-seq library types](#overview-of-rna-seq-library-types)
    * [Taxonomic classification](taxonomic-classification)
    * [Variant Annotation](variant-annotation)
 * [Blogs](#blogs)
 * [Knowledge bank](#knowledge-bank)
 * [Data visualisation](#data-visualisation )
 
# Programming

### [Git](git.md)

### BASH  
 * Cheat Sheets:  
    * [Cheat Sheet Level1](https://github.com/NBISweden/GAAS/blob/master/annotation/knowledge/Bash_cheat_sheet_level1.pdf)
    * [Cheat Sheet Level2](https://github.com/NBISweden/GAAS/blob/master/annotation/knowledge/Bash_cheat_sheet_level2.pdf) 
    * [Cheat Sheet Level3](https://github.com/NBISweden/GAAS/blob/master/annotation/knowledge/Bash_cheat_sheet_level3.pdf)   
 * [course](https://github.com/NBISweden/GAAS/blob/master/annotation/knowledge/Bash_lecture.pdf)  
 * [others](bash_other.md)  
 * one-liners:  
    * [Stephen is Turner](https://github.com/stephenturner/oneliners)
    * [Bonnie I-Man Ng](https://github.com/onceupon/Bash-Oneliner)

### Perl  
 * [Perl code profiler](perl_code_profiler.md)

### Python
 * [Create a package on PyPI](pypi.md)

### R
 * [R](r.md)

# Cluster
 
### [Schedulers: LSF,Torque,SGE,Slurm,etc](pictures/scheduler_rosetta.pdf)

### [Slurm](slurm.md)

### [Rackham](rackham.md)

### [Screen](screen.md)

# File format

 * [BAM and SAM](https://samtools.github.io/hts-specs/SAMv1.pdf)  
 * [CIGAR](cigar.md)  
 * [GFF and GTF](gxf.md)  
 * MD tag in bam format  
   * [MD Tags in BAM Files](https://github.com/vsbuffalo/devnotes/wiki/The-MD-Tag-in-BAM-Files)   
   * [The history the MD tag and the CIGAR X operator](http://lh3.github.io/2018/03/27/the-history-the-cigar-x-operator-and-the-md-tag)
 * Markdown syntax
   * [Git Markdown](https://guides.github.com/features/mastering-markdown/)
   * [Anchors in Git Markdown](anchors-in-markdown.md)
 * [SUGAR](sugar.md)
 * [VULGAR](vulgar.md)
 * Wiki syntax
   * [textile](https://textile-lang.com) - Used by Redmine
 * External ressource about many different formats
   * [UCONN - University of Connecticut](https://bioinformatics.uconn.edu/resources-and-events/tutorials-2/file-formats-tutorial/)
   * [lastz README](http://www.bx.psu.edu/~rsharris/lastz/newer/README.lastz-1.02.40.html#ex_cigar)
   * [UCSC - University of California, Santa Cruz](https://genome.ucsc.edu/FAQ/FAQformat.html)

# Converting

  * [gff to gtf](gff_to_gtf.md)
  * [gff to bed](gff_to_bed.md)

# Statistics  
 * [general](statistics.md)
 * [seeing-theory](https://seeing-theory.brown.edu)
 * [Modern Statistics for Modern Biology](https://www.huber.embl.de/msmb/)
 * [Scientists rise up against statistical significance](https://www.nature.com/articles/d41586-019-00857-9)
 * [methodologie - fr](https://fr.slideshare.net/bachelet/methodologie-mesurer-testerdeshypotheses)
 * [bioinfo-fr - fr](https://bioinfo-fr.net/tests-statistiques-suivez-lguide)
 * [Introduction aux Statistiques - fr](http://www.cons-dev.org/elearning/stat/index.html)

# Others

### MinHash  
 * [sourmash](http://joss.theoj.org/papers/10.21105/joss.00027)
 * [Kmer-db](https://github.com/refresh-bio/kmer-db)
 * [Applying MinHash to cluster RNAseq samples](http://ivory.idyll.org/blog/2016-sourmash.html)
 * [http://ivory.idyll.org/blog/2016-sourmash-sbt.html] (http://ivory.idyll.org/blog/2016-sourmash-sbt.html)

### Annotation tools
 * #### [Genome (Protein coding genes)](annotation_tools_genome.md)
 * #### [Mitochondrion](annotation_tools_mitome.md)
 * #### [Chloroplast](annotation_tools_plastome.md)
 * #### [Plasmid](annotation_tools_plasmidome.md)

### [Overview of RNA-seq library types](rnaseq_library_types.md)

### [Taxonomic classification](taxonomic_classification.md)

### Variant Annotation

3 main tools exists, Annovar, snpEff and VEP. [Choice of transcripts and software has a large effect on variant annotation](https://genomemedicine.biomedcentral.com/articles/10.1186/gm543), so choice in tool or reference annotation can be hard to do. Here a nice blog providing good insights: https://blog.goldenhelix.com/the-sate-of-variant-annotation-a-comparison-of-annovar-snpeff-and-vep/  
A new tool entered in the game called [openCRAVAT](https://www.biorxiv.org/content/10.1101/794297v1). Official doc is [here](https://open-cravat.readthedocs.io/en/latest/index.html) and the github account is [here](https://github.com/KarchinLab/open-cravat). Extra information can be found [here](https://hpc.nih.gov/apps/OpenCRAVAT.html).

# Blogs
 * [Bioinformatics I/O](http://bioinformatics.cvr.ac.uk/blog/)  
 * [Living in an Ivory Basement](http://ivory.idyll.org/blog/)  
   From C. Titus Brown
 * [The Genome Factory](https://thegenomefactory.blogspot.com)  
   From Torsten Seemann
 * [avrilomics](http://avrilomics.blogspot.com)  
   From Avril Coghlan
 * [OPINIOMICS](http://www.opiniomics.org)  
   From Mick Watson
 * [Omics! Omics!](http://www.omicsomics.blogspot.com)  
   From Keith Robison
 * [DNA Zoo](https://www.dnazoo.org)  
   From Aiden lab  
 * [NBIS](https://nbis.se/blog/)
 * [List from biostars](https://www.biostars.org/p/243961/)
 * [Bioinformatics Workbook](https://bioinformaticsworkbook.org)
 * [infoplatter](https://infoplatter.wordpress.com/2013/10/20/what-makes-you-a-good-bioinformatician/)

# Knowledge bank
 * [ecSeq Bioinformatics](https://www.ecseq.com/support/)  
 
# Data visualisation  
 
 * [Orange: Data Mining Fruitful and Fun](https://orange.biolab.si)
 
 * Data Visualization Type Catalogs (from Yuri Engelhardt)
    * [Classic](https://datavizcatalogue.com)
    * [Thorough](http://datavizproject.com)
    * [R](https://www.r-graph-gallery.com)
    * [Python](https://python-graph-gallery.com)
    * [FT Vocab](http://ft.com/vocabulary)
    * [Searched](http://visualizationuniverse.com/charts)
    * [Tools](http://chartmaker.visualisingdata.com)
    * [Weird](https://xeno.graphics)

 * Some blog posts on specific data types (from James Scott-Brown):
    * [Distributions (16 ways)](http://www.darkhorseanalytics.com/blog/visualizing-distributions-3?es_p=3278620)
    * [Graphs (6 ways)](https://www.twosixlabs.com/6-ways-visualize-graphs)
    * [Two numbers (45 ways)](https://www.scribblelive.com/blog/2012/07/27/45-ways-to-communicate-two-quantities/)
    * [Proportions (9 ways)](http://flowingdata.com/2009/11/25/9-ways-to-visualize-proportions-a-guide/)
    * [Change over time (11 ways)](http://flowingdata.com/2010/01/07/11-ways-to-visualize-changes-over-time-a-guide/)

 * Circular plots
    * [circlize: circular visualization in R](https://github.com/jokergoo/circlize)
    * [circos plots](https://medium.com/@Marianattestad/a-treatise-on-making-circos-plots-from-genomic-data-7ff496849e0)
    
 * [ClustVis a web tool for visualizing clustering of multivariate data](https://biit.cs.ut.ee/clustvis/)

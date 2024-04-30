## GNN

* framework: Pytorch Geometric 
    - Supports Homogeneous and heterogeneous GNNs
    - Multiple GNN blocks available
    - Explainability pipelines included
    - Well-documented

* LEarning Ressources
    - Basics of GNNs : [Sanchez-Lengeling et al. A Gentle Introduction to Graph Neural Networks"; Distill 2021](https://distill.pub/2021/gnn-intro/)
    - Bioinformatics Applications : [Zhang et al. "Graph Neural Netorks and their current applications in bioinformatics", Front. Genet. 2021](https://www.frontiersin.org/journals/genetics/articles/10.3389/fgene.2021.690049/full)
    - Network Biology : [Zitnil et al. "Current and future directions in network biology" 2023](https://arxiv.org/abs/2309.08478)


## Shapiro / Wilcoxon / Student


One common activity in statistics is to test if two independant samples are different between each other.  

* First we must check if the distribution follow the Normal distribution with `Shapiro` test. Depending this result we will not apply the same test.  
* If test is significant => does not follow the Normal distribution, we must then use the `Wilcoxon` test.
* If test not significant => the data follow normal distribution, we must use the `Student` test. (N>=20)  

## General Ressources

 * [seeing-theory - A visual introduction to probability and statistics](https://seeing-theory.brown.edu)
 * [Modern Statistics for Modern Biology](https://www.huber.embl.de/msmb/)
 * [Scientists rise up against statistical significance](https://www.nature.com/articles/d41586-019-00857-9)
 * [methodologie - fr](https://fr.slideshare.net/bachelet/methodologie-mesurer-testerdeshypotheses)
 * [bioinfo-fr - fr](https://bioinfo-fr.net/tests-statistiques-suivez-lguide)
 * [Introduction aux Statistiques - fr](http://www.cons-dev.org/elearning/stat/index.html)
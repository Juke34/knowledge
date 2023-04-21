## Shapiro / Wilcoxon / Student


One common activity in statistics is to test if two independant samples are different between each other.  

* First we must check if the distribution follow the Normal distribution with `Shapiro` test. Depending this result we will not apply the same test.  
* If test is significant => does not follow the Normal distribution, we must then use the `Wilcoxon` test.
* If test not significant => the data follow normal distribution, we must use the `Student` test. (N>=20)  

## Ressources

 * [seeing-theory - A visual introduction to probability and statistics](https://seeing-theory.brown.edu)
 * [Modern Statistics for Modern Biology](https://www.huber.embl.de/msmb/)
 * [Scientists rise up against statistical significance](https://www.nature.com/articles/d41586-019-00857-9)
 * [methodologie - fr](https://fr.slideshare.net/bachelet/methodologie-mesurer-testerdeshypotheses)
 * [bioinfo-fr - fr](https://bioinfo-fr.net/tests-statistiques-suivez-lguide)
 * [Introduction aux Statistiques - fr](http://www.cons-dev.org/elearning/stat/index.html)
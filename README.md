# share
## 1) PPI_coexpression_plot.ipynb
There are many scripts available for visualizing protein-protein interaction (PPI) and pathway enrichment analysis results simultanously. However, most of these approachs assume that a single gene can only belong to one pathway, which is not the case in most scenarios. Often, a gene can be associated with multiple pathways. 

Here are some common challenges you might encounter:
(1) Cannot visualize a gene's association with multiple pathways affectively:
PPI%2Bcoexpression_example1.png
(2) Cannot cluster based on the similarity of pathways:
Below is a plot drawed by R, I hope to separate the gene class A and class B into the right and left of the panel respectively. Then, clustering them based on the similarity of pathway, but there are always overlape when the gene count is huge. This is due to the cluster method a used is based on Jaccard similarity, that is length(intersect(x, y)) / length(union(x, y)). Therefore, it could consider the semantic information. For example, there are total 5 pathway, the Jaccard value of gene A which belongs to pathwayA and pathwayB and gene B which belongs to pathwayC and pathwayD. Their Jaccard values are equal. If this problem can be solved, may be we can develop a plugin like Cluego in Cytoscape. Cluego can cluster same single pathway or a gene belongs to multiple pathway but using it need a license which abtaining page has been unwork. 
PPI%2Bcoexpression_example2.png
(3) Manually adjusting the chart is too tiring, and you need to redo it when you have new data.
Just like this, when I was adjusting it for the second version, I felt eye pain, so the flag "I love automation" came again!
PPI%2Bcoexpression_example3.png
(4) The protein protein interaction and pathway note are different source or you want to add some new such as co expression. For instance, this plot require cluster through PPI firstly, then annotating each cluster though pathway enrichment analysis. 
PPI%2Bcoexpression_example3.png

Here it something I hope to help you solve~
(1) mark multiple pathways which a gene belong as difffernt blocks of a bar represent the multiple pathways this gene belong
(2) noting gene class as the bold edge represent classA while general edge represent classB
(3) noting different interaction, like "--" represent PPI, ':'represent coexpression, and "——" represent PPI_coexpression.
PPI%2Bcoexpression_example4.png

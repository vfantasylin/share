# share
## 1) PPI_coexpression_plot.ipynb
There are many scripts available for visualizing protein-protein interaction (PPI) and pathway enrichment analysis results simultanously. However, most of these approachs assume that a single gene can only belong to one pathway, which is not the case in most scenarios. Often, a gene can be associated with multiple pathways. 

Here are some common challenges you might encounter:
(1) Cannot visualize a gene's association with multiple pathways affectively:
[PPI_coexpression_example1.png](https://github.com/vfantasylin/share/blob/main/PPI_coexpression_example/PPI_coexpression_example1.png)
Drawing code: https://schochastics.github.io/R4SNA/enhance-viz.html
(2) Cannot cluster based on the similarity of pathways:
In the eample below, creating using R, I aim to separate gene classes A and B into the right and left sides of the panel, respectively, and then cluster them based on pathway similarity. However, overlaping often occuers when dealing with a large number of genes. This is due to the cluster method used relies on Jaccard similarity, defined as length(intersect(x, y)) / length(union(x, y)). While effective for some cases, it does not account for semantic information. For example, if there are five pathways, the Jaccard similarity value for gene A (associated with pathways A and B) and gene B(associated with Pathways C and D) might be the same. Their Jaccard values are equal. Addressing this limitation could pave the way for a plugin like ClueGO in Cytoscape. While ClueGO can handle such cases, it requires a license, and its licensing page has become inaccessible.
[PPI_coexpression_example2.png](https://github.com/vfantasylin/share/blob/main/PPI_coexpression_example/PPI_coexpression_example2.png)
(3) Manually adjusting the chart is time-consuming and error-prone, especially when new data requires redoing the visualization.
when I was adjusting the plot for the second version, it casued significant eye strain, reigniting my desire for automation! 
[PPI_coexpression_example3.png](https://github.com/vfantasylin/share/blob/main/PPI_coexpression_example/PPI_coexpression_example3.png)
(4) PPI data and pathway annotations often come from different sources, and integrating them can be challenging. For instance, creating the plot below required clustering based on PPI first, followed by annotating each cluster though pathway enrichment analysis. Therefore, you can't perform PPI&coexpression and gene enrichment analysis separately, nor can you customize the input data. 
[PPI_coexpression_example4.png](https://github.com/vfantasylin/share/blob/main/PPI_coexpression_example/PPI_coexpression_example4.png)
Drawing code: https://zhuanlan.zhihu.com/p/374836002

Here it something I hope to help you solve~
(1) Represent a gene's association with multiple pathways as different blocks in a bar chart, where each block corresponds to one pathway.
(2) Distinguish gene classes by edge style: use bold edges for Class A genes and general edges for Class B genes.
(3) Use different line styles to represent interaction types:
Dashed lines (--) for PPI.
Dotted lines (:) for co-expression.
Solid lines (——) for combined PPI and co-expression.
[PPI_coexpression_example5.png](https://github.com/vfantasylin/share/blob/main/PPI_coexpression_example/PPI_coexpresssion_example5.png)

# FusionPathway

Understanding the molecular effects of a fusion is important in determining its biological function in oncogenesis and in developing therapeutic strategies for cancer patients with the fusion, especially if the fusion is undruggable. However, the molecular mechanisms have been elucidated for only a few fusions, in part because of the labor-intensive nature of the required functional assays. Therefore, we developed a domain-based network approach to infer the pathways that are functionally associated with a fusion and identify potential therapeutic targets in these pathways. The FusionPathway package provides the functionalities for implementing the developed domain-based network approach. 

Our proposed domain-based network approach is illustrated in the figure below. First, a fusion protein consists of the domains of its parental proteins, therefore we hypothesized that the fusion protein retains some of the molecular interactions of its parental proteins. Given the fusion’s domain composition, we can predict the protein-protein or protein-DNA interactions of the fusion (panel a in the figure). Second, we reasoned that genes that are functionally associated with these predicted molecular interactions are also functionally associated with the fusion (panel b in the figure). Therefore, we used the network “guilt-by-association” method, which has been used to prioritize novel disease genes and annotate gene function, to calculate the functional association of each gene with the fusion. Third, we considered pathways that enrich genes with high fusion-association scores are also functionally associated with the fusion (panel c in the figure). We ranked all the genes on the basis of their fusion-association scores. Gene set enrichment analysis (GSEA), which can evaluate the genes of a pathway for their distribution in the ordered gene list, was then used to identify pathways functionally associated with a fusion (termed GSEA association analysis). Forth, by leveraging gene expression data from samples that have or lack a fusion, we can identify pathways that are deregulated by the fusion (panel d in the figure). The deregulation level of an associated pathway can be also determined using GSEA (termed GSEA deregulation analysis). The truncated product method (Zaykin et al., 2002) was used to combine the p values of each pathway generated from the GSEA association and GSEA deregulation analyses to identify pathways that are both highly associated with the fusion and significantly deregulated by it in a specific cellular condition.

![figure1](https://user-images.githubusercontent.com/14062661/30707054-ded42b02-9ebf-11e7-872e-6d50b13302c7.jpg)

# Installation
install.packages("devtools") <br />
library("devtools") <br />
devtools::install_github("perwu/FusionPathway") <br />

# Scripts for the three fusions
This packages also contain scripts for the three examples mentioned in our paper, BCR-ABL1, EWSR1-FLI1, and FUS-DDIT3. The scripts can be accessed in the subfolder "scripts" under the package folder. <br />

file.edit("/Users/cwu9/Library/R/3.3/library/FusionPathway/scripts/Example_Fusion_BCR-ABL1.r") <br />
file.edit("/Users/cwu9/Library/R/3.3/library/FusionPathway/scripts/Example_Fusion_EWS_FLI1.r") <br />
file.edit("/Users/cwu9/Library/R/3.3/library/FusionPathway/scripts/Example_Fusion_FUS-DDIT3.r") <br />



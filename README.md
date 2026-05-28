# The Not-So-Great Speciator: Systematics and Species Limits in the Asiatic White-Eye Complex (*Zosterops* spp.)

This repository hosts the analysis documentation and workflows for a study of the systematics and species limits of the Asiatic white-eye complex, focusing on *Zosterops japonicus*, *Z. montanus*, and related taxa across East Asia and the Philippines. The project integrates RADseq-derived single nucleotide polymorphism (SNP) data, Sanger-sequenced loci, and linear morphometrics from museum specimens to resolve longstanding questions about species boundaries in this complex group.

The companion website for this project can be found at: **https://hermmays.github.io/Zosterops1/**

---

## Authors

- Herman L. Mays Jr. *(corresponding author)*, Marshall University, USA
- Bailey D. McKay, American Museum of Natural History, USA
- Isao Nishiumi, National Museum of Nature and Science, Japan
- Cheng-Te Yao, Taiwan Biodiversity Research Institute, Taiwan
- Fa-Sheng Zou, Guangdong Academy of Sciences, China
- Madeline Boyd, Marshall University, USA
- Devon DeRaad, University of California Los Angeles, USA
- Ruey-Shing Lin, Taiwan Biodiversity Research Institute, Taiwan
- Kazuto Kawakami, Forestry and Forest Products Research Institute, Japan
- Chang-Hoe Kim, National Institute of Ecology, Republic of Korea
- Laura Kubatko, The Ohio State University, USA
- Robert Moyle, University of Kansas, USA

---

## Site Pages

### [Title and Authors](https://hermmays.github.io/Zosterops1/index.html)
Land here to learn who the authors are in this study and where to find them.

### [Introduction](https://hermmays.github.io/Zosterops1/about.html)
What is this project all about? The often confusing and always fascinating story of White-eyes (Genus: Zosterops)! Here you can glean a brief introduction to the study system and get some flavor for the spectacular vistas of East Asia in addition to the cold reality of lab benches and dusty museum cabinets. Here I set the stage for the analyses to come. Also in this section I gratefully acknolwedge the funding for this project, recognize the invaluable contributions of museums, and offer enormous gratitude to ornithologists who have paved the way for this wrok .

### [Sampling Maps](https://hermmays.github.io/Zosterops1/ZosteropsMaps.html)

*Where in the world?*

An R-based workflow for mapping all sampling localities for both the SNP and Sanger sequencing datasets. Includes maps of the full native range, the Ryukyu Islands, the Ogasawara and Volcano Islands, and the Philippines, using the R packages `ggplot2`, `maps`, and `sf`.

### [Sanger Sequencing Summary Statistics and Trees](https://hermmays.github.io/Zosterops1/Summary_Sanger.html)

*Red, yellow, green, and blue!*

Summary statistics and phylogenetic trees derived from the Sanger-sequenced multi-locus dataset. Documents the allele-based approach, sequence diversity metrics, and resulting gene trees.

### [StarBEAST2](https://hermmays.github.io/Zosterops1/Zosterops_StarBEAST2.html)

*Tackling a BEAST.*

Bayesian multispecies coalescent analysis using StarBEAST2. This page documents the configuration and results of the species tree estimation from the Sanger data.

### [BPP and GDI-Based Species Delimitation](https://hermmays.github.io/Zosterops1/ZosteropsBPP.html)

*BPP and GDI.*

Species delimitation analyses using the Bayesian Phylogenetics and Phylogeography (BPP) program and the Genealogical Divergence Index (GDI). These methods evaluate support for species boundaries under the multispecies coalescent model using the Sanger-sequenced loci.

### [Distance Trees, PCA, UMAP, and DAPC Analyses](https://hermmays.github.io/Zosterops1/ZosteropsSNPs_analysis.html)

*Bring on the SNPs!*

Exploratory and population-level analyses of the RADseq SNP dataset. Includes distance-based trees, principal component analysis (PCA), Uniform Manifold Approximation and Projection (UMAP), and Discriminant Analysis of Principal Components (DAPC) to visualize genetic structure among taxa.

### [Genetic Differentiation and Biogeographic Breaks](https://hermmays.github.io/Zosterops1/Zosterops_SNPFst.html)

*Island hopping.*

Analysis of genetic differentiation (F-statistics) across populations to identify potential biogeographic barriers within the Asiatic white-eye complex. Here genetics are explicitly placed in a geographic context with special emphasis on islands. 

### [Species Trees and Delimitation with SVDQuartets, PICL, and DELINEATE](https://hermmays.github.io/Zosterops1/Zosterops_SVDQ.html)

*Finally some decent trees!*

Species tree inference and delimitation from the SNP dataset using SVDQuartets, the PICL model, and the DELINEATE software. These coalescent-based approaches provide independent estimates of species boundaries and relationships to compare with results from the Sanger-based analyses.

### [Linear Morphometrics](https://hermmays.github.io/Zosterops1/ZosteropsMorphometrics.html)

*Legs, wings, beaks, and tails.*

Analysis of phenotypic variation using linear measurements from museum study skins. Specimens were accessed from the American Museum of Natural History, Cincinnati Museum Center, The Field Museum, and the Smithsonian National Museum of Natural History. Results are integrated with the genetic data to provide a more complete picture of species limits.

---

## Built With

This website was built using [Quarto](https://quarto.org/docs/websites) and R (v4.4.2). Analyses were conducted in RStudio (v2024.09.1).

## Contact

Questions about these analyses and the broader research program are welcomed and should be directed to Herman L. Mays Jr. at maysh [at] marshall.edu or maysher[at] gmail.com. Additional information can be found at [monofilia.org](https://www.monofilia.org).

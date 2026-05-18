::: {#quarto-search-results}
:::

::: {.navbar-container .container-fluid}
::: {#quarto-search title="Search"}
:::

[]{.navbar-toggler-icon}

::: {#navbarCollapse .collapse .navbar-collapse}
-   [[Title and authors]{.menu-text}](./index.html){.nav-link}
-   [[Introduction]{.menu-text}](./about.html){.nav-link}
-   [[Sampling Maps]{.menu-text}](./ZosteropsMaps.html){.nav-link}
-   [[Sanger sequencing summary statistics and
    trees]{.menu-text}](./Summary_Sanger.html){.nav-link}
-   [[StarBEAST2]{.menu-text}](./Zosterops_StarBEAST2.html){.nav-link}
-   [[BPP and GDI based species
    delimitation]{.menu-text}](./ZosteropsBPP.html){.nav-link}
-   [[MSN, Distance trees, PCA, UMAP, and DAPC
    analyses]{.menu-text}](./ZosteropsSNPs_analysis.html){.nav-link}
-   [[Genetic differentiation and biogeographic
    breaks]{.menu-text}](./Zosterops_SNPFst.html){.nav-link}
-   [[Species trees and delimitation with SVDQuartets, PICL, and
    DELINEATE]{.menu-text}](./Zosterops_SVDQ.html){.nav-link}
-   [[Linear
    morphometrics]{.menu-text}](./ZosteropsMorphometrics.html){.nav-link
    .active}
:::

::: {.quarto-navbar-tools}
:::
:::

::: {#quarto-content .quarto-container .page-columns .page-rows-contents .page-layout-article .page-navbar}
::: {#quarto-margin-sidebar .sidebar .margin-sidebar}
## On this page {#toc-title}

-   [Goals](#goals){#toc-goals .nav-link .active}
-   [Getting started](#getting-started){#toc-getting-started .nav-link}
-   [General methods
    summary](#general-methods-summary){#toc-general-methods-summary
    .nav-link}
-   [Packages](#packages){#toc-packages .nav-link}
-   [Data files](#data-files){#toc-data-files .nav-link}
    -   [Final morphometric
        dataset](#final-morphometric-dataset){#toc-final-morphometric-dataset
        .nav-link}
-   [Principal component analyses
    (PCA)](#principal-component-analyses-pca){#toc-principal-component-analyses-pca
    .nav-link}
    -   [PCA for species](#pca-for-species){#toc-pca-for-species
        .nav-link}
    -   [PCA for
        subspecies](#pca-for-subspecies){#toc-pca-for-subspecies
        .nav-link}
-   [Box-and-whisker plots and pairwise
    tests](#box-and-whisker-plots-and-pairwise-tests){#toc-box-and-whisker-plots-and-pairwise-tests
    .nav-link}
    -   [Species plots and
        summaries](#species-plots-and-summaries){#toc-species-plots-and-summaries
        .nav-link}
    -   [Taxonomic/biogeographic group plots, summaries, and
        t-tests](#taxonomicbiogeographic-group-plots-summaries-and-t-tests){#toc-taxonomicbiogeographic-group-plots-summaries-and-t-tests
        .nav-link}
-   [Close log](#close-log){#toc-close-log .nav-link}
:::

::: {#quarto-document-content .content role="main"}
::: {.quarto-title}
:::

::: {.quarto-title-meta}
:::

::: {#goals .section .level2}
## Goals {#goals .anchored anchor-id="goals"}

Included here is are analyses of morphological phenotypes in East Asian
Zosterops taken from linear measurements of museum skins at the
Cincinnati Museum Center, National Museum of Natural History at the
Smithsonian, the American Museum of Natural History, and the Field
Museum of Natural History.
:::

::: {#getting-started .section .level2}
## Getting started {#getting-started .anchored anchor-id="getting-started"}

We are using R version 4.4.2, RStudio version 2024.09.1 for the
analysis. Quarto version 1.6.39 for Mac OS was used to document the
workflow. Set the working directory in RStudio to one where the
`Zosterops_linear_measurements.csv` data file is accessible.
:::

::: {#general-methods-summary .section .level2}
## General methods summary {#general-methods-summary .anchored anchor-id="general-methods-summary"}

Linear morphometric data including culmen length, nares-to-tip bill
length, bill depth, bill width, tarsus length, wing cord, and tail
length were collected from 388 round museum skins for all the Zosterops
taxa in this study from the American Museum of Natural History (New
York, NY, USA), Cincinnati Museum Center (Cincinnati, OH, USA), The
Field Museum (Chicago, IL, USA), and the Smithsonian National Museum of
Natural History (Washington DC, USA). All measurements were recorded by
the same researcher (HLM) in mm using either digital calipers or a wing
rule. Culmen length was measured as exposed culmen from the tip of the
bill to the point where the bill meets the forehead plumage. Bill length
from nares-to-tip was measured from the distal end of the right nare to
the tip of the bill. Bill depth and width were measured at the nares.
Tarsus (tarsometatarsus) length was measured from the base of the
phalanges to the tibiotarsal joint. Wing cord was measured unflattened
with a wing rule. Tail length was measured from the body to the tip of
the longest rectrix by placing the same wing rule in the center of the
tail. Skins where poor condition or positioning prevented accurate
measurements for one or more traits were excluded from analysis making
the final analyzed dataset 354 individual specimens.

A PCA was conducted using the `prcomp` function and plotted for PC1-2
and for PC1-3 using *plotly* in R with specimens grouped solely
according to species. Specimens were further divided into 11 groups for
pairwise statistics including a 'continental' group of *Z. japonicus*
specimens from the main islands of Japan, the Ryukyu Archipelago, and
the Korean Peninsula and surrounding islands, a 'oceanic' *Z. japonicus*
group including those subspecies *stejnegeri* and *alani* on oceanic
islands in the Pacific (Izu, Ogasawara, and Volcano Islands), two *Z.
montanus* groups including a northern Philippine group on the islands of
Luzon and Mindoro, and a southern *Z. montanus* group in the central and
southern Philippines and Indonesia, and the *Z. nigrorum catarmanensis*
subspecies on the Philippine island of Camiguin South. The remaining
samples, *Z. erythropleurus*, *Z. everetti*, *Z. meyeni*, *Z. nigrorum*
(excluding *catarmanesnis*), *Z. palpebrosus*, and *Z. simplex*, were
each grouped according to species. Box-and-whisker plots were generated
for both grouping schemas, solely by species and by a combination of
geography and species, tests for normality were conducted, and pairwise
Wilcoxon tests were conducted for each pair of groups.
:::

::: {#packages .section .level2}
## Packages {#packages .anchored anchor-id="packages"}

Set the working directory to one where the file
`Zosterops_linear_measurements.csv` is accessible. Install the following
packages.

-   logr [([Bosak 2024](#ref-logr))]{.citation cites="logr"} Optional if
    you wish to create a log file for the analysis.

-   ggplot2 [([Wickham 2016](#ref-ggplot2))]{.citation cites="ggplot2"}

-   plotly [([Sievert 2020](#ref-plotly))]{.citation cites="plotly"}

-   dplyr [([Wickham et al. 2023](#ref-dplyr))]{.citation cites="dplyr"}

-   tidyr [([Wickham, Vaughan, and Girlich 2024](#ref-tidyr))]{.citation
    cites="tidyr"}

-   gt [([Iannone et al. 2024](#ref-gt))]{.citation cites="gt"}

-   factoextra [([Kassambara and Mundt
    2020](#ref-factoextra))]{.citation cites="factoextra"}

-   broom [([Robinson, Hayes, and Couch 2024](#ref-broom))]{.citation
    cites="broom"}

-   readr [([Wickham, Hester, and Bryan 2024](#ref-readr))]{.citation
    cites="readr"}

-   gridExtra [([Auguie 2017](#ref-gridExtra))]{.citation
    cites="gridExtra"}

-   htmlwidgets [([Vaidyanathan et al.
    2023](#ref-htmlwidgets))]{.citation cites="htmlwidgets"}

Load the package libraries.

::: {.cell}
::: {#cb1 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
# Load necessary libraries
library(logr)
```
:::

::: {.cell-output .cell-output-stderr}
    Loading required package: common
:::

::: {#cb3 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
library(ggplot2)
```
:::

::: {.cell-output .cell-output-stderr}
    Warning: package 'ggplot2' was built under R version 4.4.3
:::

::: {#cb5 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
library(plotly)
```
:::

::: {.cell-output .cell-output-stderr}
    Attaching package: 'plotly'
:::

::: {.cell-output .cell-output-stderr}
    The following object is masked from 'package:ggplot2':

        last_plot
:::

::: {.cell-output .cell-output-stderr}
    The following object is masked from 'package:stats':

        filter
:::

::: {.cell-output .cell-output-stderr}
    The following object is masked from 'package:graphics':

        layout
:::

::: {#cb10 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
library(dplyr)
```
:::

::: {.cell-output .cell-output-stderr}
    Attaching package: 'dplyr'
:::

::: {.cell-output .cell-output-stderr}
    The following objects are masked from 'package:stats':

        filter, lag
:::

::: {.cell-output .cell-output-stderr}
    The following objects are masked from 'package:base':

        intersect, setdiff, setequal, union
:::

::: {#cb14 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
library(tidyr)
library(gt)
library(factoextra)
```
:::

::: {.cell-output .cell-output-stderr}
    Welcome! Want to learn more? See two factoextra-related books at https://goo.gl/ve3WBa
:::

::: {#cb16 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
library(broom)
library(readr)
library(gridExtra)
```
:::

::: {.cell-output .cell-output-stderr}
    Attaching package: 'gridExtra'
:::

::: {.cell-output .cell-output-stderr}
    The following object is masked from 'package:dplyr':

        combine
:::

::: {#cb19 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
library(grid)
library(htmlwidgets)
```
:::
:::

Restart R in the Session/Restart R drop-down in R Studio and create a
`log` file for the analysis (optional).

::: {.cell}
::: {#cb20 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
log_open(file_name = "ZosteropsMorphometrics.log")
```
:::

::: {.cell-output .cell-output-stdout}
    [1] "./log/ZosteropsMorphometrics.log"
:::
:::
:::

::: {#data-files .section .level2}
## Data files {#data-files .anchored anchor-id="data-files"}

::: {#final-morphometric-dataset .section .level3}
### Final morphometric dataset {#final-morphometric-dataset .anchored anchor-id="final-morphometric-dataset"}

Morphological data for this analysis is in the comma delimited file
titled `Zosterops_linear_measurements2.csv`. Import the morphological
dataset using `read.csv` and summarize. In total 388 individual
specimens were measured. Measurements for 354 skins were retained for
analysis.

::: {.cell}
::: {#cb22 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
# Import data from CSV file
ZosteropsMorph <- read.csv('./Data/Morphometrics/Zosterops_linear_measurements2.csv')
summary(ZosteropsMorph)
```
:::

::: {.cell-output .cell-output-stdout}
        Museum          Catalog.number        Genus             Species         
     Length:354         Length:354         Length:354         Length:354        
     Class :character   Class :character   Class :character   Class :character  
     Mode  :character   Mode  :character   Mode  :character   Mode  :character  
                                                                                
                                                                                
                                                                                
      Subspecies           Locale              Name              Group          
     Length:354         Length:354         Length:354         Length:354        
     Class :character   Class :character   Class :character   Class :character  
     Mode  :character   Mode  :character   Mode  :character   Mode  :character  
                                                                                
                                                                                
                                                                                
       BillCulmen     BillNareTip       BillDepth       BillWidth    
     Min.   : 7.72   Min.   : 5.070   Min.   :2.400   Min.   :2.200  
     1st Qu.: 9.70   1st Qu.: 7.100   1st Qu.:2.882   1st Qu.:2.900  
     Median :10.30   Median : 7.500   Median :3.100   Median :3.100  
     Mean   :10.44   Mean   : 7.563   Mean   :3.088   Mean   :3.127  
     3rd Qu.:11.07   3rd Qu.: 8.000   3rd Qu.:3.300   3rd Qu.:3.400  
     Max.   :15.50   Max.   :10.700   Max.   :4.390   Max.   :4.000  
         Tarsus           Wing            Tail      
     Min.   :12.60   Min.   :49.00   Min.   :29.00  
     1st Qu.:16.30   1st Qu.:54.00   1st Qu.:37.00  
     Median :17.39   Median :56.00   Median :40.00  
     Mean   :17.46   Mean   :56.46   Mean   :39.74  
     3rd Qu.:18.40   3rd Qu.:59.00   3rd Qu.:42.00  
     Max.   :23.20   Max.   :64.00   Max.   :50.00  
:::
:::

Create a table displaying all the data in the file
`Zosterops_linear_measurements2.csv`.

::: {.cell}
::: {#cb24 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
ZosteropsMorph %>%
   gt(auto_align = FALSE)
```
:::

::: {.cell-output-display}
::: {#zdzdsqppwo style="padding-left:0px;padding-right:0px;padding-top:10px;padding-bottom:10px;overflow-x:auto;overflow-y:auto;width:auto;height:auto;"}
  Museum                               Catalog.number   Genus       Species          Subspecies      Locale            Name                         Group                   BillCulmen   BillNareTip   BillDepth   BillWidth   Tarsus   Wing   Tail
  ------------------------------------ ---------------- ----------- ---------------- --------------- ----------------- ---------------------------- ----------------------- ------------ ------------- ----------- ----------- -------- ------ ------
  Cincinnati Museum Center             B39029           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.79        7.77          3.00        3.09        17.20    61.5   36
  Cincinnati Museum Center             B37675           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          11.04        7.70          3.06        3.31        18.19    55.0   34
  Cincinnati Museum Center             B37676           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.13        7.66          2.95        3.21        18.22    57.0   35
  Cincinnati Museum Center             B37376           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.66        7.68          3.39        3.53        20.94    57.5   36
  Cincinnati Museum Center             B35538           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          9.01         6.63          3.15        3.48        17.90    52.0   33
  Cincinnati Museum Center             B37674           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.44        7.25          3.18        2.96        17.55    57.0   35
  Cincinnati Museum Center             B35539           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.69        8.54          3.22        2.87        16.26    55.5   36
  Cincinnati Museum Center             B35541           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          9.56         7.13          3.64        3.54        16.43    52.0   32
  Cincinnati Museum Center             B35543           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.29        7.48          2.82        3.22        15.76    55.0   38
  Cincinnati Museum Center             B35540           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          9.43         7.21          3.13        3.48        15.71    53.0   34
  Cincinnati Museum Center             B35626           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          9.92         7.76          3.26        2.93        17.34    52.0   38
  Cincinnati Museum Center             B36301           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.69        7.21          3.06        3.45        18.15    54.0   34
  Cincinnati Museum Center             B35836           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.08        7.28          2.91        3.58        17.95    58.5   34
  Cincinnati Museum Center             B36302           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.97        7.71          2.99        3.41        16.24    53.5   33
  Cincinnati Museum Center             B35837           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          9.95         7.58          3.10        3.79        17.15    58.5   29
  Cincinnati Museum Center             B35838           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.92        7.97          2.78        3.24        15.86    58.0   35
  Cincinnati Museum Center             B38163           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          11.11        8.58          3.24        3.76        16.74    59.0   36
  Cincinnati Museum Center             B36897           Zosterops   montanus         ssp             PANAY             Z montanus ssp               montanus SOUTH          11.55        8.36          3.46        3.49        17.48    51.0   35
  Cincinnati Museum Center             B39200           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          9.86         7.22          3.61        3.30        16.28    57.0   33
  Cincinnati Museum Center             B39198           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.16        7.71          3.13        3.60        17.17    54.5   34
  Cincinnati Museum Center             B36817           Zosterops   montanus         ssp             PANAY             Z montanus ssp               montanus SOUTH          11.08        8.03          3.03        3.72        17.41    54.0   37
  Cincinnati Museum Center             B36895           Zosterops   montanus         ssp             PANAY             Z montanus ssp               montanus SOUTH          11.44        8.48          3.28        3.08        19.16    53.0   34
  Cincinnati Museum Center             B36818           Zosterops   montanus         ssp             PANAY             Z montanus ssp               montanus SOUTH          11.77        8.70          3.60        3.80        16.34    55.0   35
  Cincinnati Museum Center             B36615           Zosterops   montanus         whiteheadi      LUZON             Z montanus whiteheadi        montanus NORTH          11.28        8.25          3.16        3.43        18.47    55.0   37
  Cincinnati Museum Center             B36616           Zosterops   montanus         whiteheadi      LUZON             Z montanus whiteheadi        montanus NORTH          10.66        7.72          2.89        3.37        17.68    56.0   36
  Cincinnati Museum Center             B39201           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.63        7.59          3.14        3.49        18.52    56.0   35
  Cincinnati Museum Center             B36894           Zosterops   montanus         ssp             PANAY             Z montanus ssp               montanus SOUTH          11.34        8.30          3.20        3.26        19.02    55.0   35
  Cincinnati Museum Center             B36898           Zosterops   montanus         ssp             PANAY             Z montanus ssp               montanus SOUTH          11.30        8.09          3.16        3.22        16.70    54.0   36
  Cincinnati Museum Center             B36896           Zosterops   montanus         ssp             PANAY             Z montanus ssp               montanus SOUTH          11.37        8.63          3.01        3.28        17.72    54.0   35
  Cincinnati Museum Center             B37023           Zosterops   montanus         pectoralis      NEGROS            Z montanus pectoralis        montanus SOUTH          11.03        8.57          3.22        3.57        18.84    58.0   38
  Cincinnati Museum Center             B37041           Zosterops   montanus         pectoralis      NEGROS            Z montanus pectoralis        montanus SOUTH          11.23        8.17          3.17        3.23        19.28    59.0   38
  Cincinnati Museum Center             B37042           Zosterops   montanus         pectoralis      NEGROS            Z montanus pectoralis        montanus SOUTH          10.42        7.99          2.81        3.19        17.06    56.5   35
  Cincinnati Museum Center             B37043           Zosterops   montanus         pectoralis      NEGROS            Z montanus pectoralis        montanus SOUTH          10.59        8.23          3.15        3.71        17.54    58.0   36
  Cincinnati Museum Center             B37052           Zosterops   montanus         pectoralis      NEGROS            Z montanus pectoralis        montanus SOUTH          11.05        8.38          3.15        3.51        17.79    60.0   40
  Cincinnati Museum Center             B37053           Zosterops   montanus         pectoralis      NEGROS            Z montanus pectoralis        montanus SOUTH          11.24        8.65          3.23        3.24        17.94    61.5   37
  Cincinnati Museum Center             B37054           Zosterops   montanus         pectoralis      NEGROS            Z montanus pectoralis        montanus SOUTH          10.90        8.15          2.88        3.46        17.54    60.5   38
  Cincinnati Museum Center             B37073           Zosterops   montanus         pectoralis      NEGROS            Z montanus pectoralis        montanus SOUTH          11.22        8.05          3.23        3.64        17.39    61.5   39
  Cincinnati Museum Center             B36991           Zosterops   montanus         halconensis     MINDORO           Z montanus halconensis       montanus NORTH          10.76        7.81          2.74        3.40        16.74    55.0   35
  Cincinnati Museum Center             B36979           Zosterops   montanus         halconensis     MINDORO           Z montanus halconensis       montanus NORTH          10.85        7.82          2.94        3.15        17.29    53.0   36
  Cincinnati Museum Center             B36617           Zosterops   montanus         whiteheadi      LUZON             Z montanus whiteheadi        montanus NORTH          11.27        8.67          3.03        3.76        17.37    56.0   36
  Cincinnati Museum Center             B36819           Zosterops   montanus         ssp             PANAY             Z montanus ssp               montanus SOUTH          11.39        8.38          3.14        3.31        17.24    56.0   37
  Cincinnati Museum Center             B33359           Zosterops   meyeni           batanis         BATAN             Z meyeni batanis             meyeni                  11.18        8.84          3.61        3.54        17.30    58.0   38
  Cincinnati Museum Center             B33961           Zosterops   everetti         boholensis      BILIRAN           Z everetti boholensis        everetti                10.05        7.39          4.39        3.57        18.52    55.0   38
  Cincinnati Museum Center             B35474           Zosterops   everetti         basilanicus     MINDANAO          Z everetti basilanicus       everetti                10.25        7.34          3.05        3.07        16.81    56.0   40
  Cincinnati Museum Center             B35475           Zosterops   everetti         basilanicus     MINDANAO          Z everetti basilanicus       everetti                10.47        7.53          3.53        3.69        17.44    56.0   37
  Cincinnati Museum Center             B35473           Zosterops   everetti         basilanicus     MINDANAO          Z everetti basilanicus       everetti                11.10        7.90          3.55        3.58        16.19    55.5   34
  Cincinnati Museum Center             B35476           Zosterops   everetti         basilanicus     MINDANAO          Z everetti basilanicus       everetti                11.73        8.45          3.04        3.79        17.43    56.0   37
  Cincinnati Museum Center             B38321           Zosterops   nigrorum         innominatus     LUZON             Z nigrorum innominatus       nigrorum                9.82         7.22          3.17        3.00        15.44    53.0   34
  Cincinnati Museum Center             B36816           Zosterops   nigrorum         nigrorum        PANAY             Z nigrorum nigrorum          nigrorum                9.95         6.76          2.76        2.76        16.52    54.0   37
  Cincinnati Museum Center             B38322           Zosterops   nigrorum         innominatus     LUZON             Z nigrorum innominatus       nigrorum                9.29         6.63          2.87        2.95        15.80    50.0   35
  Cincinnati Museum Center             B38226           Zosterops   nigrorum         innominatus     LUZON             Z nigrorum innominatus       nigrorum                8.96         6.67          2.57        2.80        15.89    51.0   34
  Cincinnati Museum Center             B38227           Zosterops   nigrorum         innominatus     LUZON             Z nigrorum innominatus       nigrorum                8.77         6.83          2.74        2.92        16.47    49.5   32
  Cincinnati Museum Center             B38228           Zosterops   nigrorum         innominatus     LUZON             Z nigrorum innominatus       nigrorum                8.71         6.42          2.71        2.54        16.42    49.0   34
  National Museum                      535697           Zosterops   erythropleurus   monotypic       THAILAND          Z erythropleurus             erythropleurus          10.16        7.11          2.66        2.64        16.67    60.5   29
  National Museum                      535698           Zosterops   erythropleurus   monotypic       THAILAND          Z erythropleurus             erythropleurus          9.64         7.30          2.73        3.19        15.55    60.0   35
  National Museum                      535699           Zosterops   erythropleurus   monotypic       THAILAND          Z erythropleurus             erythropleurus          9.11         6.67          2.90        2.37        16.35    59.5   38
  National Museum                      535696           Zosterops   erythropleurus   monotypic       THAILAND          Z erythropleurus             erythropleurus          9.39         6.58          2.92        3.23        15.59    61.0   39
  National Museum                      335147           Zosterops   erythropleurus   monotypic       SICHUAN           Z erythropleurus             erythropleurus          9.53         7.22          2.80        2.93        15.08    62.5   39
  National Museum                      91558            Zosterops   japonicus        japonicus       HONSHU            Z japonicus japonicus        japonicus CONTINENTAL   10.50        8.07          3.30        3.28        16.68    60.0   37
  National Museum                      606567           Zosterops   meyeni           batanis         LANYU             Z meyeni batanis             meyeni                  10.60        7.33          3.69        3.64        20.79    56.0   38
  National Museum                      606561           Zosterops   meyeni           batanis         LANYU             Z meyeni batanis             meyeni                  10.66        7.67          3.21        3.48        18.08    59.0   39
  National Museum                      606570           Zosterops   meyeni           batanis         GREENISLAND       Z meyeni batanis             meyeni                  10.85        8.07          3.52        3.34        19.65    58.0   41
  National Museum                      582854           Zosterops   meyeni           batanis         BATAN             Z meyeni batanis             meyeni                  11.67        8.41          3.68        3.68        18.17    57.5   39
  National Museum                      582853           Zosterops   meyeni           batanis         BATAN             Z meyeni batanis             meyeni                  10.41        7.19          3.16        3.53        17.68    55.5   41
  National Museum                      582852           Zosterops   meyeni           batanis         BATAN             Z meyeni batanis             meyeni                  11.09        8.00          3.51        3.68        18.88    55.0   34
  National Museum                      582851           Zosterops   meyeni           batanis         BATAN             Z meyeni batanis             meyeni                  10.15        6.95          3.10        3.60        16.90    55.0   40
  National Museum                      627873           Zosterops   japonicus        daitoensis      KITADAITOJIMA     Z japonicus daitoensis       japonicus CONTINENTAL   11.04        7.98          3.15        3.49        17.47    58.5   44
  National Museum                      383201           Zosterops   japonicus        alani           IWOTO             Z japonicus alani            japonicus OCEANIC       12.36        7.88          3.42        3.33        20.56    61.0   46
  National Museum                      383202           Zosterops   japonicus        alani           IWOTO             Z japonicus alani            japonicus OCEANIC       11.12        7.63          3.33        3.33        19.94    61.5   44
  National Museum                      111658           Zosterops   japonicus        stejnegeri      OSHIMA            Z japonicus stejnegeri       japonicus OCEANIC       12.39        9.10          3.69        2.98        19.34    62.5   45
  National Museum                      96110            Zosterops   japonicus        japonicus       HOKKAIDO          Z japonicus japonicus        japonicus CONTINENTAL   10.98        7.53          2.82        2.66        16.68    57.0   39
  National Museum                      405525           Zosterops   japonicus        loochooensis    OKINAWA           Z japonicus loochooensis     japonicus CONTINENTAL   11.20        7.61          2.95        3.25        18.17    58.5   40
  National Museum                      405522           Zosterops   japonicus        loochooensis    OKINAWA           Z japonicus loochooensis     japonicus CONTINENTAL   10.08        7.18          3.08        3.02        17.79    59.5   37
  National Museum                      405521           Zosterops   japonicus        loochooensis    OKINAWA           Z japonicus loochooensis     japonicus CONTINENTAL   9.72         7.05          3.04        3.03        17.65    56.0   39
  National Museum                      405520           Zosterops   japonicus        loochooensis    OKINAWA           Z japonicus loochooensis     japonicus CONTINENTAL   9.55         7.17          3.07        3.43        16.46    60.5   41
  National Museum                      86143            Zosterops   simplex          simplex         HONGKONG          Z simplex simplex            simplex                 7.72         5.07          2.89        3.37        16.13    55.0   37
  National Museum                      86144            Zosterops   simplex          simplex         HONGKONG          Z simplex simplex            simplex                 9.17         6.97          2.86        2.76        15.88    55.5   36
  National Museum                      86145            Zosterops   simplex          simplex         HONGKONG          Z simplex simplex            simplex                 9.06         7.32          2.69        3.14        16.10    54.5   37
  National Museum                      578008           Zosterops   everetti         boholensis      LEYTE             Z everetti boholensis        everetti                10.25        7.84          3.65        3.29        15.62    54.5   35
  National Museum                      578004           Zosterops   everetti         boholensis      LEYTE             Z everetti boholensis        everetti                10.10        7.17          3.60        3.56        15.70    53.5   41
  National Museum                      578001           Zosterops   everetti         boholensis      LEYTE             Z everetti boholensis        everetti                10.63        7.26          3.42        3.30        15.59    61.0   38
  National Museum                      211094           Zosterops   everetti         boholensis      BOHOL             Z everetti boholensis        everetti                10.02        6.89          3.22        3.21        16.30    55.0   41
  National Museum                      315717           Zosterops   everetti         mandibularis    SULU              Z everetti mandibularis      everetti                9.86         7.15          3.08        3.55        15.50    53.0   40
  National Museum                      485424           Zosterops   everetti         tahanensis      BORNEO            Z everetti tahanensis        everetti                8.26         5.79          2.48        3.22        13.82    52.5   31
  National Museum                      581661           Zosterops   everetti         basilanicus     MINDANAO          Z everetti basilanicus       everetti                8.86         6.93          3.29        3.30        17.31    62.0   40
  National Museum                      581677           Zosterops   everetti         basilanicus     MINDANAO          Z everetti basilanicus       everetti                9.90         6.57          3.22        2.95        16.11    54.5   42
  National Museum                      192697           Zosterops   nigrorum         richmondi       CAGAYANCILLO      Z nigrorum richmondi         nigrorum                11.03        7.70          3.26        3.40        16.36    58.5   46
  National Museum                      607560           Zosterops   nigrorum         aureiloris      LUZON             Z nigrorum aureiloris        nigrorum                10.00        6.73          2.93        2.94        14.49    52.0   35
  National Museum                      192696           Zosterops   nigrorum         richmondi       CAGAYANCILLO      Z nigrorum richmondi         nigrorum                11.16        8.03          3.54        3.64        19.05    58.5   43
  National Museum                      582068           Zosterops   montanus         pectoralis      NEGROS            Z montanus pectoralis        montanus SOUTH          10.35        7.20          3.18        3.52        19.00    53.0   40
  National Museum                      582067           Zosterops   montanus         pectoralis      NEGROS            Z montanus pectoralis        montanus SOUTH          10.41        7.46          2.85        3.28        17.26    56.5   38
  National Museum                      192701           Zosterops   nigrorum         nigrorum        MASBATE           Z nigrorum nigrorum          nigrorum                9.74         7.60          3.12        3.82        15.64    55.0   42
  National Museum                      315706           Zosterops   nigrorum         nigrorum        PANAY             Z nigrorum nigrorum          nigrorum                10.06        7.27          3.26        3.39        13.84    52.0   38
  National Museum                      192202           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.01        7.39          2.97        3.23        17.40    59.0   41
  National Museum                      192203           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          11.08        7.99          3.33        3.57        16.82    62.0   38
  National Museum                      202406           Zosterops   montanus         halconensis     MINDORO           Z montanus halconensis       montanus NORTH          10.16        7.74          2.88        3.48        16.11    55.0   39
  American Museum of Natural History   699708           Zosterops   erythropleurus   monotypic       YUNNAN            Z erythropleurus             erythropleurus          9.30         6.80          2.70        2.80        16.50    61.5   41
  American Museum of Natural History   699707           Zosterops   erythropleurus   monotypic       YUNNAN            Z erythropleurus             erythropleurus          10.00        6.90          2.60        3.00        14.60    59.0   37
  American Museum of Natural History   699704           Zosterops   erythropleurus   monotypic       YUNNAN            Z erythropleurus             erythropleurus          10.20        7.60          2.80        2.70        15.20    62.0   39
  American Museum of Natural History   699705           Zosterops   erythropleurus   monotypic       YUNNAN            Z erythropleurus             erythropleurus          9.90         7.20          2.80        3.00        15.50    59.0   38
  American Museum of Natural History   699706           Zosterops   erythropleurus   monotypic       YUNNAN            Z erythropleurus             erythropleurus          10.00        6.90          3.10        2.90        15.50    60.0   38
  American Museum of Natural History   699709           Zosterops   erythropleurus   monotypic       YUNNAN            Z erythropleurus             erythropleurus          10.00        6.50          2.80        2.80        15.60    60.5   38
  American Museum of Natural History   699714           Zosterops   erythropleurus   monotypic       BEIJING           Z erythropleurus             erythropleurus          9.40         7.00          3.10        2.80        16.70    59.5   45
  American Museum of Natural History   699710           Zosterops   erythropleurus   monotypic       SHANGHAI          Z erythropleurus             erythropleurus          10.10        6.50          3.30        2.80        14.90    61.5   44
  American Museum of Natural History   699712           Zosterops   erythropleurus   monotypic       BEIJING           Z erythropleurus             erythropleurus          9.70         6.10          2.90        2.80        16.40    57.5   41
  American Museum of Natural History   418687           Zosterops   erythropleurus   monotypic       SHANDONG          Z erythropleurus             erythropleurus          9.80         6.70          2.90        2.80        15.60    63.5   41
  American Museum of Natural History   418686           Zosterops   erythropleurus   monotypic       SHANDONG          Z erythropleurus             erythropleurus          9.10         6.30          2.50        2.70        15.90    51.0   42
  American Museum of Natural History   699713           Zosterops   erythropleurus   monotypic       BEIJING           Z erythropleurus             erythropleurus          9.70         6.30          2.90        2.90        18.90    54.0   37
  American Museum of Natural History   699716           Zosterops   erythropleurus   monotypic       BEIJING           Z erythropleurus             erythropleurus          10.30        6.40          2.80        2.60        15.00    61.2   42
  American Museum of Natural History   699711           Zosterops   erythropleurus   monotypic       BEIJING           Z erythropleurus             erythropleurus          9.10         6.60          2.60        2.60        16.80    59.5   40
  American Museum of Natural History   418685           Zosterops   erythropleurus   monotypic       SHANDONG          Z erythropleurus             erythropleurus          9.60         5.70          2.70        3.10        16.20    62.0   39
  American Museum of Natural History   418688           Zosterops   erythropleurus   monotypic       SHANDONG          Z erythropleurus             erythropleurus          8.10         5.80          2.50        2.80        14.80    57.5   41
  American Museum of Natural History   418684           Zosterops   erythropleurus   monotypic       SHANDONG          Z erythropleurus             erythropleurus          9.20         6.40          2.90        2.80        17.20    59.5   41
  American Museum of Natural History   418690           Zosterops   erythropleurus   monotypic       NOLOCALE          Z erythropleurus             erythropleurus          9.40         6.80          2.50        2.60        16.00    62.5   40
  American Museum of Natural History   418689           Zosterops   erythropleurus   monotypic       SHANDONG          Z erythropleurus             erythropleurus          9.60         6.60          2.70        2.70        16.90    61.0   44
  American Museum of Natural History   699715           Zosterops   erythropleurus   monotypic       BEIJING           Z erythropleurus             erythropleurus          9.10         6.20          2.50        2.40        18.30    59.5   40
  American Museum of Natural History   839413           Zosterops   japonicus        japonicus       TSUSHIMA          Z japonicus japonicus        japonicus CONTINENTAL   10.40        7.30          3.00        2.50        17.50    58.0   43
  American Museum of Natural History   839425           Zosterops   japonicus        japonicus       TSUSHIMA          Z japonicus japonicus        japonicus CONTINENTAL   12.80        8.00          3.20        3.10        17.10    61.5   49
  American Museum of Natural History   839434           Zosterops   japonicus        japonicus       TSUSHIMA          Z japonicus japonicus        japonicus CONTINENTAL   11.30        8.50          3.10        3.20        18.60    60.0   42
  American Museum of Natural History   839406           Zosterops   japonicus        japonicus       TSUSHIMA          Z japonicus japonicus        japonicus CONTINENTAL   11.70        8.30          3.00        3.00        17.90    60.0   45
  American Museum of Natural History   785303           Zosterops   japonicus        japonicus       KOREA             Z japonicus japonicus        japonicus CONTINENTAL   12.00        8.10          2.80        2.80        18.60    59.5   43
  American Museum of Natural History   785314           Zosterops   japonicus        stejnegeri      IZUISLANDS        Z japonicus stejnegeri       japonicus OCEANIC       10.30        7.90          2.80        2.80        19.50    60.5   44
  American Museum of Natural History   785340           Zosterops   japonicus        japonicus       HONSHU            Z japonicus japonicus        japonicus CONTINENTAL   10.80        7.70          2.60        2.50        17.40    58.5   43
  American Museum of Natural History   461440           Zosterops   japonicus        stejnegeri      HACHIJOJIMA       Z japonicus stejnegeri       japonicus OCEANIC       13.60        9.90          3.10        3.20        22.60    62.0   47
  American Museum of Natural History   785324           Zosterops   japonicus        stejnegeri      IZUISLANDS        Z japonicus stejnegeri       japonicus OCEANIC       14.40        10.10         3.20        3.20        21.20    60.0   46
  American Museum of Natural History   703552           Zosterops   japonicus        stejnegeri      MIYAKEJIMA        Z japonicus stejnegeri       japonicus OCEANIC       13.60        9.70          3.30        3.40        19.30    63.0   48
  American Museum of Natural History   785311           Zosterops   japonicus        stejnegeri      IZUISLANDS        Z japonicus stejnegeri       japonicus OCEANIC       13.40        9.60          3.70        3.70        18.80    61.0   40
  American Museum of Natural History   703551           Zosterops   japonicus        stejnegeri      MIYAKEJIMA        Z japonicus stejnegeri       japonicus OCEANIC       14.10        10.10         3.60        3.50        20.10    63.0   48
  American Museum of Natural History   461439           Zosterops   japonicus        stejnegeri      MIYAKEJIMA        Z japonicus stejnegeri       japonicus OCEANIC       14.60        9.60          3.20        3.30        19.60    63.5   50
  American Museum of Natural History   699764           Zosterops   japonicus        insularis       YAKUSHIMA         Z japonicus insularis        japonicus CONTINENTAL   12.50        8.30          2.80        3.20        22.10    60.5   50
  American Museum of Natural History   785316           Zosterops   japonicus        stejnegeri      IZUISLANDS        Z japonicus stejnegeri       japonicus OCEANIC       15.50        10.70         3.30        3.30        19.60    62.0   42
  American Museum of Natural History   699739           Zosterops   japonicus        alani           IWOTO             Z japonicus alani            japonicus OCEANIC       11.80        7.90          3.40        3.20        20.40    59.0   46
  American Museum of Natural History   699786           Zosterops   japonicus        insularis       TANEGASHIMA       Z japonicus insularis        japonicus CONTINENTAL   11.40        7.90          3.10        3.10        17.70    58.0   46
  American Museum of Natural History   699738           Zosterops   japonicus        alani           IWOTO             Z japonicus alani            japonicus OCEANIC       12.50        8.10          3.80        3.50        22.20    62.0   45
  American Museum of Natural History   699740           Zosterops   japonicus        alani           IWOTO             Z japonicus alani            japonicus OCEANIC       11.90        8.40          3.50        3.60        20.30    61.5   44
  American Museum of Natural History   699742           Zosterops   japonicus        alani           IWOTO             Z japonicus alani            japonicus OCEANIC       12.50        8.50          3.30        3.20        18.50    60.5   47
  American Museum of Natural History   699744           Zosterops   japonicus        alani           IWOTO             Z japonicus alani            japonicus OCEANIC       12.80        7.90          3.50        3.60        20.30    62.0   46
  American Museum of Natural History   699746           Zosterops   japonicus        alani           IWOTO             Z japonicus alani            japonicus OCEANIC       12.70        8.20          3.60        3.30        20.20    61.0   44
  American Museum of Natural History   699743           Zosterops   japonicus        alani           IWOTO             Z japonicus alani            japonicus OCEANIC       11.90        7.50          3.70        3.40        18.70    60.0   48
  American Museum of Natural History   699745           Zosterops   japonicus        alani           IWOTO             Z japonicus alani            japonicus OCEANIC       12.30        7.70          3.40        3.30        21.10    60.5   47
  American Museum of Natural History   699789           Zosterops   japonicus        loochooensis    ISHIGAKI          Z japonicus loochooensis     japonicus CONTINENTAL   11.40        7.90          2.90        3.10        18.10    58.0   45
  American Museum of Natural History   699809           Zosterops   japonicus        loochooensis    AMAMI             Z japonicus loochooensis     japonicus CONTINENTAL   10.60        7.80          2.80        2.40        17.90    57.0   45
  American Museum of Natural History   699826           Zosterops   japonicus        loochooensis    AMAMI             Z japonicus loochooensis     japonicus CONTINENTAL   10.90        7.20          2.80        3.00        17.70    55.5   45
  American Museum of Natural History   699816           Zosterops   japonicus        loochooensis    AMAMI             Z japonicus loochooensis     japonicus CONTINENTAL   10.00        7.20          2.80        3.00        19.60    57.0   41
  American Museum of Natural History   699819           Zosterops   japonicus        loochooensis    AMAMI             Z japonicus loochooensis     japonicus CONTINENTAL   10.20        7.60          2.70        2.80        17.10    55.0   48
  American Museum of Natural History   699823           Zosterops   japonicus        loochooensis    AMAMI             Z japonicus loochooensis     japonicus CONTINENTAL   10.60        7.40          3.00        3.10        19.30    55.0   43
  American Museum of Natural History   699815           Zosterops   japonicus        loochooensis    AMAMI             Z japonicus loochooensis     japonicus CONTINENTAL   11.00        7.70          3.00        3.10        18.20    57.5   44
  American Museum of Natural History   785351           Zosterops   japonicus        daitoensis      DAITOISLANDS      Z japonicus daitoensis       japonicus OCEANIC       10.70        7.60          3.10        2.90        17.20    61.0   41
  American Museum of Natural History   115079           Zosterops   simplex          simplex         SHANDONG          Z simplex simplex            simplex                 8.00         6.30          2.70        2.80        15.80    59.0   43
  American Museum of Natural History   699889           Zosterops   simplex          simplex         JIUJIANG          Z simplex simplex            simplex                 8.80         6.40          2.80        2.90        16.10    55.5   44
  American Museum of Natural History   115084           Zosterops   simplex          simplex         SHANDONG          Z simplex simplex            simplex                 9.80         7.40          2.70        2.60        15.20    58.0   43
  American Museum of Natural History   115085           Zosterops   simplex          simplex         NOLOCALE          Z simplex simplex            simplex                 8.70         7.10          2.70        2.90        16.30    57.0   39
  American Museum of Natural History   699854           Zosterops   simplex          simplex         YUNNAN            Z simplex simplex            simplex                 9.60         7.00          2.70        2.90        17.50    56.0   44
  American Museum of Natural History   204017           Zosterops   simplex          simplex         NOLOCALE          Z simplex simplex            simplex                 10.00        7.10          2.70        2.40        16.00    55.0   46
  American Museum of Natural History   418694           Zosterops   simplex          simplex         SHANDONG          Z simplex simplex            simplex                 9.40         6.60          2.40        2.70        15.40    60.0   39
  American Museum of Natural History   699876           Zosterops   simplex          simplex         XIAMEN            Z simplex simplex            simplex                 10.00        7.60          2.90        3.20        15.00    55.5   43
  American Museum of Natural History   699856           Zosterops   simplex          simplex         YUNNAN            Z simplex simplex            simplex                 9.60         6.70          2.50        2.90        16.90    56.0   38
  American Museum of Natural History   418701           Zosterops   simplex          simplex         GUANGDONG         Z simplex simplex            simplex                 9.10         6.80          3.00        2.80        16.10    55.0   39
  American Museum of Natural History   785346           Zosterops   simplex          simplex         TAIWAN            Z simplex simplex            simplex                 9.60         7.30          2.70        3.10        15.80    51.5   37
  American Museum of Natural History   699918           Zosterops   simplex          simplex         TAIWAN            Z simplex simplex            simplex                 9.20         6.90          2.60        2.70        16.40    54.5   41
  American Museum of Natural History   699919           Zosterops   simplex          simplex         TAIWAN            Z simplex simplex            simplex                 10.90        7.50          2.90        2.80        16.70    53.0   40
  American Museum of Natural History   699916           Zosterops   simplex          simplex         TAIWAN            Z simplex simplex            simplex                 9.90         7.10          2.50        3.10        16.70    51.0   37
  American Museum of Natural History   699906           Zosterops   simplex          simplex         TAIWAN            Z simplex simplex            simplex                 9.10         7.00          3.00        3.00        16.10    50.5   35
  American Museum of Natural History   699923           Zosterops   simplex          simplex         TAIWAN            Z simplex simplex            simplex                 9.00         7.20          2.70        2.90        15.90    54.0   42
  American Museum of Natural History   839397           Zosterops   meyeni           batanis         LANYU             Z meyeni batanis             meyeni                  11.10        7.90          3.00        3.50        18.40    56.0   38
  American Museum of Natural History   839399           Zosterops   meyeni           batanis         LANYU             Z meyeni batanis             meyeni                  9.90         7.70          3.00        3.50        17.60    56.5   39
  American Museum of Natural History   839394           Zosterops   meyeni           batanis         LANYU             Z meyeni batanis             meyeni                  11.40        8.10          3.50        3.90        17.40    59.5   41
  American Museum of Natural History   839395           Zosterops   meyeni           batanis         LANYU             Z meyeni batanis             meyeni                  10.20        7.20          3.00        3.20        17.60    60.0   45
  American Museum of Natural History   839396           Zosterops   meyeni           batanis         LANYU             Z meyeni batanis             meyeni                  10.70        7.60          3.20        3.40        17.90    58.0   41
  American Museum of Natural History   839402           Zosterops   meyeni           batanis         LANYU             Z meyeni batanis             meyeni                  10.30        7.40          3.20        3.20        17.90    55.0   38
  American Museum of Natural History   839397           Zosterops   meyeni           batanis         LANYU             Z meyeni batanis             meyeni                  10.30        7.90          2.90        3.30        19.30    55.0   37
  American Museum of Natural History   810380           Zosterops   meyeni           batanis         LANYU             Z meyeni batanis             meyeni                  10.60        7.60          3.20        3.30        18.50    54.5   43
  American Museum of Natural History   700146           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          9.90         7.10          3.20        3.50        15.50    55.5   43
  American Museum of Natural History   416949           Zosterops   montanus         whiteheadi      LUZON             Z montanus whiteheadi        montanus NORTH          9.90         7.10          3.10        2.70        16.40    55.0   40
  American Museum of Natural History   488892           Zosterops   montanus         pectoralis      NEGROS            Z montanus pectoralis        montanus SOUTH          9.30         7.20          3.00        2.60        17.10    52.5   37
  American Museum of Natural History   488896           Zosterops   montanus         pectoralis      NEGROS            Z montanus pectoralis        montanus SOUTH          9.80         7.10          2.80        3.00        17.00    54.5   40
  American Museum of Natural History   459968           Zosterops   montanus         pectoralis      NEGROS            Z montanus pectoralis        montanus SOUTH          10.30        7.40          3.20        2.60        18.80    57.0   42
  American Museum of Natural History   346385           Zosterops   montanus         montanus        TIMOR             Z montanus montanus          montanus SOUTH          9.70         6.90          3.00        3.00        15.40    59.5   42
  American Museum of Natural History   346390           Zosterops   montanus         montanus        TIMOR             Z montanus montanus          montanus SOUTH          9.70         7.10          2.70        3.00        15.70    56.0   42
  American Museum of Natural History   346386           Zosterops   montanus         montanus        TIMOR             Z montanus montanus          montanus SOUTH          9.30         6.90          2.80        2.80        17.10    59.5   44
  Field Museum                         74154            Zosterops   japonicus        alani           MINAMITORISHIMA   Z japonicus alani            japonicus OCEANIC       12.50        8.60          3.70        3.50        20.60    61.0   42
  Field Museum                         74153            Zosterops   japonicus        alani           IWOTO             Z japonicus alani            japonicus OCEANIC       11.80        8.70          3.50        3.00        21.90    61.0   50
  Field Museum                         74152            Zosterops   japonicus        stejnegeri      MIYAKEJIMA        Z japonicus stejnegeri       japonicus OCEANIC       12.70        8.80          3.30        3.30        19.30    61.5   43
  Field Museum                         246943           Zosterops   japonicus        stejnegeri      OSHIMA            Z japonicus stejnegeri       japonicus OCEANIC       12.80        8.70          3.20        3.30        21.80    60.0   41
  Field Museum                         246944           Zosterops   japonicus        stejnegeri      OSHIMA            Z japonicus stejnegeri       japonicus OCEANIC       13.10        9.40          2.90        3.20        20.70    62.5   49
  Field Museum                         246947           Zosterops   japonicus        stejnegeri      MIYAKEJIMA        Z japonicus stejnegeri       japonicus OCEANIC       13.00        9.70          3.30        3.40        21.70    61.0   46
  Field Museum                         65661            Zosterops   japonicus        stejnegeri      NIIJIMA           Z japonicus stejnegeri       japonicus OCEANIC       13.20        9.50          3.70        3.40        20.00    63.0   44
  Field Museum                         246950           Zosterops   japonicus        stejnegeri      MIYAKEJIMA        Z japonicus stejnegeri       japonicus OCEANIC       13.90        9.30          3.10        4.00        21.50    62.0   43
  Field Museum                         246948           Zosterops   japonicus        stejnegeri      MIYAKEJIMA        Z japonicus stejnegeri       japonicus OCEANIC       14.20        10.10         3.40        3.50        23.20    64.0   45
  Field Museum                         246949           Zosterops   japonicus        stejnegeri      MIYAKEJIMA        Z japonicus stejnegeri       japonicus OCEANIC       13.70        10.30         3.60        3.30        22.00    64.0   48
  Field Museum                         246946           Zosterops   japonicus        stejnegeri      OSHIMA            Z japonicus stejnegeri       japonicus OCEANIC       13.80        9.00          3.40        3.50        20.90    61.0   42
  Field Museum                         246945           Zosterops   japonicus        stejnegeri      OSHIMA            Z japonicus stejnegeri       japonicus OCEANIC       12.10        8.50          3.20        3.40        22.80    61.5   44
  Field Museum                         74151            Zosterops   japonicus        japonicus       HONSHU            Z japonicus japonicus        japonicus CONTINENTAL   11.00        7.10          2.70        3.00        20.50    59.0   45
  Field Museum                         74150            Zosterops   japonicus        japonicus       HONSHU            Z japonicus japonicus        japonicus CONTINENTAL   11.70        8.10          2.90        3.00        19.50    60.0   44
  Field Museum                         65667            Zosterops   japonicus        japonicus       HONSHU            Z japonicus japonicus        japonicus CONTINENTAL   11.00        7.80          2.60        3.10        19.30    58.0   44
  Field Museum                         257081           Zosterops   japonicus        japonicus       KOREA             Z japonicus japonicus        japonicus CONTINENTAL   12.30        7.50          3.00        2.90        18.20    58.0   45
  Field Museum                         257082           Zosterops   japonicus        japonicus       KOREA             Z japonicus japonicus        japonicus CONTINENTAL   12.10        7.90          3.40        2.80        20.40    60.0   42
  Field Museum                         186366           Zosterops   meyeni           batanis         BATAN             Z meyeni batanis             meyeni                  11.20        8.70          3.50        3.50        18.00    55.5   41
  Field Museum                         219896           Zosterops   meyeni           batanis         BATAN             Z meyeni batanis             meyeni                  10.80        8.40          3.30        4.00        18.30    59.5   44
  Field Museum                         186367           Zosterops   meyeni           batanis         BATAN             Z meyeni batanis             meyeni                  11.20        7.90          3.40        3.30        19.70    58.5   44
  Field Museum                         219895           Zosterops   meyeni           batanis         BATAN             Z meyeni batanis             meyeni                  11.20        8.20          3.50        3.40        19.40    56.0   42
  Field Museum                         20250            Zosterops   meyeni           meyeni          BANTON            Z meyeni meyeni              meyeni                  10.80        7.40          3.20        2.80        18.20    55.5   40
  Field Museum                         20749            Zosterops   meyeni           meyeni          BANTON            Z meyeni meyeni              meyeni                  11.40        8.80          3.20        3.80        19.50    56.5   43
  Field Museum                         24058            Zosterops   meyeni           meyeni          CALAYAN           Z meyeni meyeni              meyeni                  10.60        7.80          3.00        3.40        18.90    55.0   41
  Field Museum                         24059            Zosterops   meyeni           meyeni          CALAYAN           Z meyeni meyeni              meyeni                  10.60        8.30          3.00        3.10        20.60    55.0   38
  Field Museum                         76221            Zosterops   simplex          simplex         VIETNAM           Z simplex simplex            simplex                 9.30         7.10          3.00        2.70        14.60    55.5   39
  Field Museum                         76219            Zosterops   simplex          simplex         VIETNAM           Z simplex simplex            simplex                 9.30         7.60          2.40        2.60        16.00    53.0   37
  Field Museum                         80318            Zosterops   simplex          simplex         VIETNAM           Z simplex simplex            simplex                 9.10         6.80          2.90        2.70        18.80    54.0   44
  Field Museum                         80309            Zosterops   simplex          simplex         VIETNAM           Z simplex simplex            simplex                 9.30         7.20          2.90        2.30        19.50    55.0   42
  Field Museum                         80307            Zosterops   simplex          simplex         VIETNAM           Z simplex simplex            simplex                 9.30         7.80          2.90        2.80        17.10    56.0   43
  Field Museum                         80317            Zosterops   simplex          simplex         VIETNAM           Z simplex simplex            simplex                 10.00        7.30          2.70        3.10        17.50    56.0   39
  Field Museum                         80311            Zosterops   simplex          simplex         VIETNAM           Z simplex simplex            simplex                 9.00         7.50          2.80        2.50        14.90    56.5   39
  Field Museum                         80312            Zosterops   simplex          simplex         VIETNAM           Z simplex simplex            simplex                 9.40         6.80          2.70        2.30        16.30    55.0   37
  Field Museum                         59474            Zosterops   simplex          simplex         FUJIAN            Z simplex simplex            simplex                 9.90         7.40          2.70        3.00        18.70    54.5   36
  Field Museum                         109065           Zosterops   simplex          simplex         SICHUAN           Z simplex simplex            simplex                 10.10        6.70          2.90        3.00        16.40    57.0   38
  Field Museum                         275481           Zosterops   everetti         basilanicus     MINDANAO          Z everetti basilanicus       everetti                9.80         7.10          3.00        3.00        16.30    56.5   45
  Field Museum                         279662           Zosterops   everetti         basilanicus     MINDANAO          Z everetti basilanicus       everetti                9.70         7.50          3.40        3.10        19.30    55.0   43
  Field Museum                         279658           Zosterops   everetti         basilanicus     MINDANAO          Z everetti basilanicus       everetti                10.10        8.30          3.50        3.40        17.60    56.5   43
  Field Museum                         284302           Zosterops   everetti         basilanicus     MINDANAO          Z everetti basilanicus       everetti                9.70         8.20          3.60        3.60        19.60    54.5   46
  Field Museum                         279653           Zosterops   everetti         basilanicus     MINDANAO          Z everetti basilanicus       everetti                9.40         7.00          3.30        3.40        16.90    54.0   38
  Field Museum                         227802           Zosterops   everetti         basilanicus     MINDANAO          Z everetti basilanicus       everetti                10.60        9.00          3.40        3.50        16.80    58.5   42
  Field Museum                         279667           Zosterops   everetti         basilanicus     MINDANAO          Z everetti basilanicus       everetti                10.20        7.20          3.00        3.10        18.50    51.0   36
  Field Museum                         275478           Zosterops   everetti         basilanicus     MINDANAO          Z everetti basilanicus       everetti                10.90        7.60          3.10        3.40        16.00    53.5   33
  Field Museum                         248395           Zosterops   everetti         boholensis      SAMAR             Z everetti boholensis        everetti                10.60        7.80          3.30        3.30        18.10    62.5   41
  Field Museum                         248398           Zosterops   everetti         boholensis      SAMAR             Z everetti boholensis        everetti                9.90         7.60          3.10        3.10        15.30    53.0   38
  Field Museum                         248393           Zosterops   everetti         boholensis      SAMAR             Z everetti boholensis        everetti                10.60        7.70          3.50        3.20        16.80    56.0   41
  Field Museum                         284635           Zosterops   everetti         basilanicus     CAMIGUIN          Z everetti basilanicus       everetti                11.20        8.40          3.60        3.40        17.90    58.5   42
  Field Museum                         223710           Zosterops   everetti         boholensis      BOHOL             Z everetti boholensis        everetti                9.90         7.60          3.10        3.30        18.30    55.0   38
  Field Museum                         223709           Zosterops   everetti         boholensis      BOHOL             Z everetti boholensis        everetti                9.70         8.40          3.20        3.30        17.90    54.5   44
  Field Museum                         223705           Zosterops   everetti         boholensis      BOHOL             Z everetti boholensis        everetti                10.10        8.00          3.30        3.00        21.10    55.0   41
  Field Museum                         223707           Zosterops   everetti         boholensis      BOHOL             Z everetti boholensis        everetti                10.40        7.90          3.50        3.30        19.60    55.0   42
  Field Museum                         223721           Zosterops   everetti         boholensis      BOHOL             Z everetti boholensis        everetti                10.00        7.70          3.40        3.60        17.90    57.5   41
  Field Museum                         223718           Zosterops   everetti         boholensis      BOHOL             Z everetti boholensis        everetti                9.60         7.60          3.30        3.10        17.40    53.5   39
  Field Museum                         223719           Zosterops   everetti         boholensis      BOHOL             Z everetti boholensis        everetti                10.50        7.70          3.30        3.00        17.90    57.0   40
  Field Museum                         223713           Zosterops   everetti         boholensis      BOHOL             Z everetti boholensis        everetti                9.70         7.30          3.20        3.10        17.40    57.5   43
  Field Museum                         223720           Zosterops   everetti         boholensis      BOHOL             Z everetti boholensis        everetti                10.00        8.10          3.30        3.20        16.60    53.5   41
  Field Museum                         276657           Zosterops   everetti         boholensis      LEYTE             Z everetti boholensis        everetti                10.60        7.70          3.40        3.20        17.70    55.0   47
  Field Museum                         276661           Zosterops   everetti         boholensis      LEYTE             Z everetti boholensis        everetti                10.80        7.60          3.10        3.40        18.30    58.0   41
  Field Museum                         276674           Zosterops   everetti         boholensis      LEYTE             Z everetti boholensis        everetti                10.60        7.00          3.30        3.10        17.10    56.0   39
  Field Museum                         276664           Zosterops   everetti         boholensis      LEYTE             Z everetti boholensis        everetti                10.50        7.20          3.40        3.40        17.00    55.5   41
  Field Museum                         276671           Zosterops   everetti         boholensis      LEYTE             Z everetti boholensis        everetti                10.30        7.00          3.60        3.10        16.40    58.0   42
  Field Museum                         276667           Zosterops   everetti         boholensis      LEYTE             Z everetti boholensis        everetti                11.50        8.10          3.30        3.30        16.90    55.5   40
  Field Museum                         276668           Zosterops   everetti         boholensis      LEYTE             Z everetti boholensis        everetti                10.60        7.30          3.10        3.10        16.60    59.0   41
  Field Museum                         217590           Zosterops   everetti         siquijorensis   SIQUIJOR          Z everetti siquijorensis     everetti                9.90         8.30          3.30        2.90        15.90    50.0   38
  Field Museum                         217593           Zosterops   everetti         siquijorensis   SIQUIJOR          Z everetti siquijorensis     everetti                9.20         7.00          2.90        3.00        17.30    53.0   37
  Field Museum                         222859           Zosterops   everetti         siquijorensis   SIQUIJOR          Z everetti siquijorensis     everetti                10.60        8.30          3.40        3.60        17.80    57.0   37
  Field Museum                         219262           Zosterops   everetti         siquijorensis   SIQUIJOR          Z everetti siquijorensis     everetti                10.50        8.00          3.20        3.30        17.50    54.5   43
  Field Museum                         219261           Zosterops   everetti         siquijorensis   SIQUIJOR          Z everetti siquijorensis     everetti                9.70         7.30          3.20        3.30        16.90    57.0   43
  Field Museum                         257408           Zosterops   nigrorum         aureiloris      LUZON             Z nigrorum aureiloris        nigrorum                9.70         6.90          3.00        2.70        16.70    50.0   37
  Field Museum                         254260           Zosterops   nigrorum         aureiloris      LUZON             Z nigrorum aureiloris        nigrorum                9.90         6.90          3.10        3.00        16.70    52.0   37
  Field Museum                         257406           Zosterops   nigrorum         aureiloris      LUZON             Z nigrorum aureiloris        nigrorum                9.50         6.80          3.20        2.70        17.80    53.0   37
  Field Museum                         254263           Zosterops   nigrorum         aureiloris      LUZON             Z nigrorum aureiloris        nigrorum                8.70         6.40          3.10        2.80        15.30    50.5   40
  Field Museum                         254303           Zosterops   nigrorum         aureiloris      LUZON             Z nigrorum aureiloris        nigrorum                10.00        7.30          2.90        3.10        17.00    54.0   38
  Field Museum                         254270           Zosterops   nigrorum         aureiloris      LUZON             Z nigrorum aureiloris        nigrorum                10.00        7.10          3.10        2.70        17.60    52.0   38
  Field Museum                         257414           Zosterops   nigrorum         aureiloris      LUZON             Z nigrorum aureiloris        nigrorum                9.10         7.20          3.40        2.50        17.10    53.0   35
  Field Museum                         184515           Zosterops   nigrorum         aureiloris      LUZON             Z nigrorum aureiloris        nigrorum                9.30         6.30          2.40        2.20        16.70    51.5   38
  Field Museum                         184570           Zosterops   nigrorum         aureiloris      LUZON             Z nigrorum aureiloris        nigrorum                9.30         8.10          2.90        2.80        16.90    50.5   37
  Field Museum                         266569           Zosterops   nigrorum         luzonicus       LUZON             Z nigrorum luzonicus         nigrorum                10.00        7.30          3.40        3.10        16.30    56.0   41
  Field Museum                         266577           Zosterops   nigrorum         luzonicus       LUZON             Z nigrorum luzonicus         nigrorum                9.20         7.20          3.10        2.80        17.90    51.5   41
  Field Museum                         266570           Zosterops   nigrorum         luzonicus       LUZON             Z nigrorum luzonicus         nigrorum                10.30        7.70          3.30        3.20        17.00    49.0   36
  Field Museum                         266571           Zosterops   nigrorum         luzonicus       LUZON             Z nigrorum luzonicus         nigrorum                9.90         7.70          3.10        3.00        17.40    53.0   39
  Field Museum                         20060            Zosterops   nigrorum         nigrorum        TICAO             Z nigrorum nigrorum          nigrorum                9.50         7.80          3.00        3.30        19.20    55.5   41
  Field Museum                         20251            Zosterops   nigrorum         nigrorum        TICAO             Z nigrorum nigrorum          nigrorum                10.10        8.70          2.90        3.00        16.60    56.0   34
  Field Museum                         246424           Zosterops   nigrorum         nigrorum        NEGROS            Z nigrorum nigrorum          nigrorum                10.40        7.20          3.10        3.20        18.50    53.5   43
  Field Museum                         191348           Zosterops   nigrorum         nigrorum        NEGROS            Z nigrorum nigrorum          nigrorum                9.30         7.00          3.70        3.00        16.10    51.5   38
  Field Museum                         191341           Zosterops   nigrorum         nigrorum        NEGROS            Z nigrorum nigrorum          nigrorum                10.20        7.40          3.20        3.30        16.70    53.0   37
  Field Museum                         251501           Zosterops   nigrorum         nigrorum        NEGROS            Z nigrorum nigrorum          nigrorum                10.20        7.80          3.70        3.00        17.80    54.5   43
  Field Museum                         259878           Zosterops   nigrorum         innominatus     LUZON             Z nigrorum innominatus       nigrorum                8.90         7.50          2.90        2.80        17.50    53.0   38
  Field Museum                         259894           Zosterops   nigrorum         innominatus     LUZON             Z nigrorum innominatus       nigrorum                9.30         7.10          2.80        2.70        16.80    49.5   41
  Field Museum                         259893           Zosterops   nigrorum         innominatus     LUZON             Z nigrorum innominatus       nigrorum                10.10        7.90          3.10        2.90        18.30    52.5   36
  Field Museum                         259899           Zosterops   nigrorum         innominatus     LUZON             Z nigrorum innominatus       nigrorum                10.30        7.20          2.90        3.00        17.70    52.0   35
  Field Museum                         20247            Zosterops   nigrorum         richmondi       CAGAYANCILLO      Z nigrorum richmondi         nigrorum                11.10        8.70          3.40        3.60        17.90    57.0   46
  Field Museum                         20248            Zosterops   nigrorum         richmondi       CAGAYANCILLO      Z nigrorum richmondi         nigrorum                10.50        8.00          3.10        3.40        20.80    57.0   38
  Field Museum                         286516           Zosterops   nigrorum         catarmanensis   CAMIGUIN          Z nigrorum catarmanensis     nigrorum CS             11.10        7.90          3.70        3.30        18.80    58.0   42
  Field Museum                         286521           Zosterops   nigrorum         catarmanensis   CAMIGUIN          Z nigrorum catarmanensis     nigrorum CS             11.10        7.70          3.80        3.30        18.80    57.5   38
  Field Museum                         286523           Zosterops   nigrorum         catarmanensis   CAMIGUIN          Z nigrorum catarmanensis     nigrorum CS             10.80        8.30          3.80        3.60        18.60    59.0   39
  Field Museum                         284611           Zosterops   nigrorum         catarmanensis   CAMIGUIN          Z nigrorum catarmanensis     nigrorum CS             11.60        8.00          3.50        3.60        19.40    60.0   44
  Field Museum                         284595           Zosterops   nigrorum         catarmanensis   CAMIGUIN          Z nigrorum catarmanensis     nigrorum CS             10.80        8.40          3.20        3.30        19.90    61.0   39
  Field Museum                         284587           Zosterops   nigrorum         catarmanensis   CAMIGUIN          Z nigrorum catarmanensis     nigrorum CS             11.40        8.40          3.40        3.30        17.80    60.0   40
  Field Museum                         284609           Zosterops   nigrorum         catarmanensis   CAMIGUIN          Z nigrorum catarmanensis     nigrorum CS             10.40        7.90          3.10        3.60        19.90    59.0   43
  Field Museum                         284612           Zosterops   nigrorum         catarmanensis   CAMIGUIN          Z nigrorum catarmanensis     nigrorum CS             11.20        8.20          3.40        3.10        19.20    63.0   45
  Field Museum                         284622           Zosterops   nigrorum         catarmanensis   CAMIGUIN          Z nigrorum catarmanensis     nigrorum CS             11.10        8.20          3.60        3.50        18.50    61.0   42
  Field Museum                         284592           Zosterops   nigrorum         catarmanensis   CAMIGUIN          Z nigrorum catarmanensis     nigrorum CS             11.00        8.30          3.60        3.20        20.10    58.0   40
  Field Museum                         284621           Zosterops   nigrorum         catarmanensis   CAMIGUIN          Z nigrorum catarmanensis     nigrorum CS             11.10        8.80          3.90        3.50        19.70    60.0   43
  Field Museum                         284613           Zosterops   nigrorum         catarmanensis   CAMIGUIN          Z nigrorum catarmanensis     nigrorum CS             10.90        8.00          3.70        3.40        19.50    59.0   34
  Field Museum                         284615           Zosterops   nigrorum         catarmanensis   CAMIGUIN          Z nigrorum catarmanensis     nigrorum CS             11.40        8.40          3.20        3.40        18.40    56.0   41
  Field Museum                         429299           Zosterops   montanus         whiteheadi      LUZON             Z montanus whiteheadi        montanus NORTH          9.80         6.40          2.40        2.90        17.20    56.0   39
  Field Museum                         449785           Zosterops   montanus         whiteheadi      LUZON             Z montanus whiteheadi        montanus NORTH          10.20        7.40          3.00        2.80        15.90    51.0   34
  Field Museum                         252895           Zosterops   montanus         whiteheadi      LUZON             Z montanus whiteheadi        montanus NORTH          9.70         6.90          2.90        2.80        18.60    54.5   37
  Field Museum                         19747            Zosterops   montanus         whiteheadi      LUZON             Z montanus whiteheadi        montanus NORTH          10.10        7.00          2.50        2.70        17.10    53.0   38
  Field Museum                         254259           Zosterops   montanus         whiteheadi      LUZON             Z montanus whiteheadi        montanus NORTH          10.60        6.90          3.40        2.80        17.80    54.0   36
  Field Museum                         19746            Zosterops   montanus         whiteheadi      LUZON             Z montanus whiteheadi        montanus NORTH          10.00        7.00          2.80        3.00        15.80    53.0   38
  Field Museum                         184493           Zosterops   montanus         whiteheadi      LUZON             Z montanus whiteheadi        montanus NORTH          10.60        7.10          2.60        3.00        14.60    51.0   33
  Field Museum                         184494           Zosterops   montanus         whiteheadi      LUZON             Z montanus whiteheadi        montanus NORTH          10.10        6.90          2.90        3.10        17.90    52.0   35
  Field Museum                         275471           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          9.30         7.10          2.80        3.30        18.50    53.0   36
  Field Museum                         279646           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          9.80         7.50          3.00        3.40        16.70    56.0   40
  Field Museum                         275472           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          9.50         7.10          3.30        3.10        17.50    53.5   36
  Field Museum                         279637           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          9.70         6.80          2.90        2.90        17.20    56.0   38
  Field Museum                         279633           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          9.70         7.30          3.10        3.20        16.70    56.5   39
  Field Museum                         279640           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          9.60         6.90          2.60        3.10        17.50    55.0   37
  Field Museum                         279649           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.40        7.10          3.20        3.40        18.40    54.0   41
  Field Museum                         217460           Zosterops   montanus         pectoralis      NEGROS            Z montanus pectoralis        montanus SOUTH          9.50         7.40          3.00        2.30        17.10    56.5   39
  Field Museum                         217458           Zosterops   montanus         pectoralis      NEGROS            Z montanus pectoralis        montanus SOUTH          10.40        7.80          3.00        2.80        17.40    54.0   38
  Field Museum                         257249           Zosterops   montanus         pectoralis      NEGROS            Z montanus pectoralis        montanus SOUTH          11.70        8.80          3.10        3.10        18.00    59.0   42
  Field Museum                         257259           Zosterops   montanus         pectoralis      NEGROS            Z montanus pectoralis        montanus SOUTH          11.20        7.90          3.00        3.00        17.40    58.0   42
  Field Museum                         257257           Zosterops   montanus         pectoralis      NEGROS            Z montanus pectoralis        montanus SOUTH          11.30        7.50          3.30        2.70        18.00    57.5   40
  Field Museum                         257264           Zosterops   montanus         pectoralis      NEGROS            Z montanus pectoralis        montanus SOUTH          11.30        8.00          3.60        2.80        18.30    58.0   40
  Field Museum                         257252           Zosterops   montanus         pectoralis      NEGROS            Z montanus pectoralis        montanus SOUTH          11.80        8.60          3.60        3.60        17.90    56.5   42
  Field Museum                         257250           Zosterops   montanus         pectoralis      NEGROS            Z montanus pectoralis        montanus SOUTH          10.80        8.10          3.10        2.90        17.60    56.0   42
  Field Museum                         191359           Zosterops   montanus         pectoralis      NEGROS            Z montanus pectoralis        montanus SOUTH          9.90         7.80          3.10        3.00        17.60    55.0   32
  Field Museum                         187918           Zosterops   montanus         pectoralis      NEGROS            Z montanus pectoralis        montanus SOUTH          10.20        7.50          3.10        2.90        18.70    54.5   38
  Field Museum                         219515           Zosterops   montanus         pectoralis      NEGROS            Z montanus pectoralis        montanus SOUTH          10.00        7.50          2.90        3.20        17.30    52.0   33
  Field Museum                         227742           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.50        7.50          3.10        3.30        16.90    61.0   41
  Field Museum                         227722           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.10        7.50          3.30        3.10        17.70    55.5   39
  Field Museum                         227716           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.60        8.10          3.10        3.00        18.20    58.5   42
  Field Museum                         227708           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.00        7.30          3.40        3.20        17.10    56.0   39
  Field Museum                         227704           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.90        7.30          3.10        3.20        17.50    53.5   34
  Field Museum                         227719           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.10        6.60          2.70        2.80        17.80    55.0   39
  Field Museum                         227732           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.80        7.80          3.00        3.50        17.10    55.5   41
  Field Museum                         227770           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          11.10        7.80          3.00        3.10        18.50    61.0   41
  Field Museum                         227729           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.40        7.80          3.20        3.30        17.30    55.5   40
  Field Museum                         227744           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          11.10        7.80          3.20        3.10        17.80    54.0   36
  Field Museum                         227717           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          11.00        7.20          3.30        3.40        17.40    56.0   36
  Field Museum                         227731           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.90        8.00          3.00        3.10        15.80    55.0   34
  Field Museum                         227762           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.30        7.90          3.40        3.10        17.00    54.5   37
  Field Museum                         392322           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          9.80         6.80          2.60        2.60        18.10    54.5   40
  Field Museum                         392321           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.40        7.40          2.70        3.20        16.90    55.0   41
  Field Museum                         357634           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          11.50        8.10          3.10        3.60        16.70    55.5   40
  Field Museum                         184500           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          11.40        7.40          2.90        3.00        17.00    56.0   41
  Field Museum                         275462           Zosterops   montanus         vulcani         MINDANAO          Z montanus vulcani           montanus SOUTH          10.40        7.10          3.40        3.20        17.30    56.5   41
  Field Museum                         244036           Zosterops   palpebrosus      palpebrosus     NEPAL             Z palpebrosus palpebrosus    palpebrosus             9.30         6.00          2.50        2.40        13.80    53.0   33
  Field Museum                         244033           Zosterops   palpebrosus      palpebrosus     NEPAL             Z palpebrosus palpebrosus    palpebrosus             9.50         6.40          2.50        2.90        12.60    51.0   36
  Field Museum                         243980           Zosterops   palpebrosus      palpebrosus     NEPAL             Z palpebrosus palpebrosus    palpebrosus             9.40         6.50          2.70        2.80        14.70    52.0   37
  Field Museum                         243987           Zosterops   palpebrosus      palpebrosus     NEPAL             Z palpebrosus palpebrosus    palpebrosus             9.40         6.80          2.80        2.40        14.90    52.0   40
  Field Museum                         243981           Zosterops   palpebrosus      palpebrosus     NEPAL             Z palpebrosus palpebrosus    palpebrosus             8.50         6.30          2.70        2.90        13.70    52.5   34
  Field Museum                         244069           Zosterops   palpebrosus      palpebrosus     ASSAM             Z palpebrosus palpebrosus    palpebrosus             9.70         7.20          2.80        2.90        14.70    53.5   39
  Field Museum                         80337            Zosterops   palpebrosus      williamsoni     LAOS              Z palpebrosus williamsoni    palpebrosus             9.00         6.70          2.60        2.90        15.70    52.0   34
  Field Museum                         80334            Zosterops   palpebrosus      williamsoni     LAOS              Z palpebrosus williamsoni    palpebrosus             9.70         7.00          2.60        2.90        15.10    51.5   37
  Field Museum                         91670            Zosterops   palpebrosus      williamsoni     LAOS              Z palpebrosus williamsoni    palpebrosus             9.70         7.10          3.00        2.40        15.00    54.5   40
  Field Museum                         244021           Zosterops   palpebrosus      nilgiriensis    GHATS             Z palpebrosus nilgiriensis   palpebrosus             9.90         6.90          2.90        2.90        14.70    54.0   43
  Field Museum                         244022           Zosterops   palpebrosus      nilgiriensis    GHATS             Z palpebrosus nilgiriensis   palpebrosus             10.80        7.90          3.00        2.90        16.70    56.0   43
  Field Museum                         244019           Zosterops   palpebrosus      nilgiriensis    GHATS             Z palpebrosus nilgiriensis   palpebrosus             10.90        7.50          3.10        3.00        13.50    56.0   41
  Field Museum                         244012           Zosterops   palpebrosus      nilgiriensis    GHATS             Z palpebrosus nilgiriensis   palpebrosus             11.10        8.20          3.20        3.00        15.30    53.0   42
  Field Museum                         244020           Zosterops   palpebrosus      nilgiriensis    GHATS             Z palpebrosus nilgiriensis   palpebrosus             10.40        7.40          3.40        2.90        15.00    55.0   44
  Field Museum                         243998           Zosterops   palpebrosus      occidentis      KATHIAWAR         Z palpebrosus occidentis     palpebrosus             8.20         6.00          3.10        2.60        15.50    54.0   39
  Field Museum                         243993           Zosterops   palpebrosus      occidentis      KATHIAWAR         Z palpebrosus occidentis     palpebrosus             7.90         5.80          2.80        2.80        15.50    53.5   39
  Field Museum                         243996           Zosterops   palpebrosus      occidentis      KATHIAWAR         Z palpebrosus occidentis     palpebrosus             8.60         6.00          2.80        2.60        15.50    55.0   40
  Field Museum                         243997           Zosterops   palpebrosus      occidentis      KATHIAWAR         Z palpebrosus occidentis     palpebrosus             8.70         6.30          2.90        2.50        14.40    53.5   39
  Field Museum                         244004           Zosterops   palpebrosus      occidentis      KATHIAWAR         Z palpebrosus occidentis     palpebrosus             8.40         6.40          2.80        3.20        16.20    53.0   40
  Field Museum                         244054           Zosterops   palpebrosus      occidentis      NCINDIA           Z palpebrosus occidentis     palpebrosus             8.50         6.50          2.80        3.10        15.00    54.0   39
  Field Museum                         257639           Zosterops   palpebrosus      egregius        SRILANKA          Z palpebrosus egregius       palpebrosus             8.70         6.30          2.60        2.80        15.90    51.5   37
  Field Museum                         257640           Zosterops   palpebrosus      egregius        SRILANKA          Z palpebrosus egregius       palpebrosus             9.00         6.40          2.70        3.00        14.20    56.5   41
  Field Museum                         257645           Zosterops   palpebrosus      egregius        SRILANKA          Z palpebrosus egregius       palpebrosus             8.30         6.00          2.50        2.50        15.40    52.5   39
  Field Museum                         257641           Zosterops   palpebrosus      egregius        SRILANKA          Z palpebrosus egregius       palpebrosus             9.10         6.60          2.60        2.90        14.10    52.0   40
:::
:::
:::
:::
:::

::: {#principal-component-analyses-pca .section .level2}
## Principal component analyses (PCA) {#principal-component-analyses-pca .anchored anchor-id="principal-component-analyses-pca"}

::: {#pca-for-species .section .level3}
### PCA for species {#pca-for-species .anchored anchor-id="pca-for-species"}

Conduct a principal component analysis (PCA) in which the groupings are
species. Plot both the first two principal components (PCs) and the
first three PCs. Create additional plots for three PCs in which the *Z.
japonicus* samples are highlighted in black and different taxonomic
groups are isolated and highlighted in grey for comparison (*Z. meyeni*,
*Z. montanus*, *Z. simplex*, and *Z. palpebrosus*) while keeping all
other taxa as open circles.

::: {.cell}
::: {#cb25 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
# Group data by 'species' and select relevant variables for PCA
ZosteropsMorph_species <- ZosteropsMorph %>% 
  select(Species, BillCulmen, BillNareTip, BillDepth, BillWidth, Tarsus, Wing, Tail) %>%
  group_by(Species)

# Perform PCA on the selected variables
pca_result <- prcomp(ZosteropsMorph_species[, -1], center = TRUE, scale. = TRUE)

# Convert PCA result to a data frame for plotting
pca_data <- as.data.frame(pca_result$x)

# Add 'species' variable to PCA data
pca_data$Species <- ZosteropsMorph_species$Species

# Plot the first two principal components
ColorPal_CUSTOM <- c("#004949", "#DB6D00", "#D82632", "#FED439", "#FA9C88", "#924900", "#8DB6CD", "#008600")
# Create the 2D scatter plot for PC1 and PC2 with outlines
PC2Dplot <- plot_ly(
  x = pca_data$PC1, 
  y = pca_data$PC2, 
  type = "scatter",  # Change to scatter for 2D plot
  mode = 'markers', 
  marker = list(size = 14, 
                line = list(color = 'black', width = 1)),  # Add black outline
  color = pca_data$Species, 
  colors = ColorPal_CUSTOM
) %>%
layout(
  xaxis = list(title = 'PC1'),
  yaxis = list(title = 'PC2'),
  title = "PCA of Zosterops Morphological Measurements"
)
PC2Dplot
```
:::

::: {.cell-output-display}
::: {#htmlwidget-00e94763e6f026eb692a .plotly .html-widget .html-fill-item style="width:100%;height:390px;"}
:::
:::

::: {#cb26 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
# Plot the first three principal components
PC3Dplot <- plot_ly(x = pca_data$PC1, y = pca_data$PC2, z = pca_data$PC3, type = "scatter3d", mode = 'markers', 
        marker = list(size = 14, line = list(color = 'black', width = 1)),
        color = pca_data$Species, 
        colors = ColorPal_CUSTOM) %>%
  layout(scene = list(xaxis = list(title = 'PC1'),
                      yaxis = list(title = 'PC2'),
                      zaxis = list(title = 'PC3')))
PC3Dplot
```
:::

::: {.cell-output-display}
::: {#htmlwidget-d0c16648dba0cb32df9a .plotly .html-widget .html-fill-item style="width:100%;height:390px;"}
:::
:::

::: {#cb27 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
# Plot of 3 PCs highlighting just the Z. japonicus and Z. meyeni taxa
# Define your custom color palette
ColorPal_japo_meye <- c("black", "grey", "transparent")  # Black for japonicus, grey for meyeni, transparent for others

# Create a vector for marker colors
MarkerCol_japo_meye <- ifelse(pca_data$Species == 'japonicus', 'black',
                               ifelse(pca_data$Species == 'meyeni', 'grey', 'transparent'))

# Create the 3D scatter plot
PC3D_japo_meye <- plot_ly(
  x = pca_data$PC1, 
  y = pca_data$PC2, 
  z = pca_data$PC3, 
  type = "scatter3d", 
  mode = 'markers', 
  marker = list(size = 10, color = MarkerCol_japo_meye, line = list(color = 'black', width = 2)),
  text = ifelse(pca_data$Species == 'japonicus', 'Z. japonicus',
                ifelse(pca_data$Species == 'meyeni', 'Z. meyeni', 'Other Species')),
  hoverinfo = "text"  # Show species name on hover
) %>%
layout(
  scene = list(
    xaxis = list(title = 'PC1'),
    yaxis = list(title = 'PC2'),
    zaxis = list(title = 'PC3')
  ),
  legend = list(title = list(text = "Species"))  # Add legend title
)

# Display the plot
PC3D_japo_meye
```
:::

::: {.cell-output-display}
::: {#htmlwidget-b750904b8e745625f749 .plotly .html-widget .html-fill-item style="width:100%;height:390px;"}
:::
:::

::: {#cb28 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
# Plot of 3 PCs highlighting just the Z. japonicus and Z. montanus taxa
# Define your custom color palette
ColorPal_japo_mont <- c("black", "grey", "transparent")  # Black for japonicus, grey for montanus, transparent for others

# Create a vector for marker colors
MarkerCol_japo_mont <- ifelse(pca_data$Species == 'japonicus', 'black',
                               ifelse(pca_data$Species == 'montanus', 'grey', 'transparent'))

# Create the 3D scatter plot
PC3D_japo_mont <- plot_ly(
  x = pca_data$PC1, 
  y = pca_data$PC2, 
  z = pca_data$PC3, 
  type = "scatter3d", 
  mode = 'markers', 
  marker = list(size = 10, color = MarkerCol_japo_mont, line = list(color = 'black', width = 2)),
  text = ifelse(pca_data$Species == 'japonicus', 'Z. japonicus',
                ifelse(pca_data$Species == 'montanus', 'Z. montanus', 'Other Species')),
  hoverinfo = "text"  # Show species name on hover
) %>%
layout(
  scene = list(
    xaxis = list(title = 'PC1'),
    yaxis = list(title = 'PC2'),
    zaxis = list(title = 'PC3')
  ),
  legend = list(title = list(text = "Species"))  # Add legend title
)

# Display the plot
PC3D_japo_mont
```
:::

::: {.cell-output-display}
::: {#htmlwidget-2a15c4f2f8863c714505 .plotly .html-widget .html-fill-item style="width:100%;height:390px;"}
:::
:::

::: {#cb29 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
# Plot of 3 PCs highlighting just the Z. japonicus and Z. simplex taxa
# Define your custom color palette
ColorPal_japo_simp <- c("black", "grey", "transparent")  # Black for japonicus, grey for simplex, transparent for others

# Create a vector for marker colors
MarkerCol_japo_simp <- ifelse(pca_data$Species == 'japonicus', 'black',
                               ifelse(pca_data$Species == 'simplex', 'grey', 'transparent'))

# Create the 3D scatter plot
PC3D_japo_simp <- plot_ly(
  x = pca_data$PC1, 
  y = pca_data$PC2, 
  z = pca_data$PC3, 
  type = "scatter3d", 
  mode = 'markers', 
  marker = list(size = 10, color = MarkerCol_japo_simp, line = list(color = 'black', width = 2)),
  text = ifelse(pca_data$Species == 'japonicus', 'Z. japonicus',
                ifelse(pca_data$Species == 'simplex', 'Z. simplex', 'Other Species')),
  hoverinfo = "text"  # Show species name on hover
) %>%
layout(
  scene = list(
    xaxis = list(title = 'PC1'),
    yaxis = list(title = 'PC2'),
    zaxis = list(title = 'PC3')
  ),
  legend = list(title = list(text = "Species"))  # Add legend title
)

# Display the plot
PC3D_japo_simp
```
:::

::: {.cell-output-display}
::: {#htmlwidget-3e679486969e18cb6a45 .plotly .html-widget .html-fill-item style="width:100%;height:390px;"}
:::
:::

::: {#cb30 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
# Plot of 3 PCs highlighting just the Z. japonicus and Z. palpebrosus taxa
# Define your custom color palette
ColorPal_japo_palp <- c("black", "grey", "transparent")  # Black for japonicus, grey for palpebrosus, transparent for others

# Create a vector for marker colors
MarkerCol_japo_palp <- ifelse(pca_data$Species == 'japonicus', 'black',
                               ifelse(pca_data$Species == 'palpebrosus', 'grey', 'transparent'))

# Create the 3D scatter plot
PC3D_japo_palp <- plot_ly(
  x = pca_data$PC1, 
  y = pca_data$PC2, 
  z = pca_data$PC3, 
  type = "scatter3d", 
  mode = 'markers', 
  marker = list(size = 10, color = MarkerCol_japo_palp, line = list(color = 'black', width = 2)),
  text = ifelse(pca_data$Species == 'japonicus', 'Z. japonicus',
                ifelse(pca_data$Species == 'palpebrosus', 'Z. palpebrosus', 'Other Species')),
  hoverinfo = "text"  # Show species name on hover
) %>%
layout(
  scene = list(
    xaxis = list(title = 'PC1'),
    yaxis = list(title = 'PC2'),
    zaxis = list(title = 'PC3')
  ),
  legend = list(title = list(text = "Species"))  # Add legend title
)

# Display the plot
PC3D_japo_palp
```
:::

::: {.cell-output-display}
::: {#htmlwidget-f8c8182744504ad8b12e .plotly .html-widget .html-fill-item style="width:100%;height:390px;"}
:::
:::

::: {#cb31 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
# Export PC3Dplots as html using the htmlWidgets package or from the menu in the RStudio viewer.
saveWidget(ggplotly(PC3Dplot), file = "Zosterops3DPCAplot_morph_ALL.html")
saveWidget(ggplotly(PC3D_japo_meye), file = "Zosterops3DPCAplot_morph_japo_meye.html")
saveWidget(ggplotly(PC3D_japo_mont), file = "Zosterops3DPCAplot_morph_japo_mont.html")
saveWidget(ggplotly(PC3D_japo_simp), file = "Zosterops3DPCAplot_morph_japo_simp.html")
saveWidget(ggplotly(PC3D_japo_palp), file = "Zosterops3DPCAplot_morph_japo_palp.html")
```
:::
:::

For PCs 1 -3 calculate the centroids and Euclidean distances for
pairwise comparisons between species.

::: {.cell}
::: {#cb32 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
# Initialize an empty data frame to store centroids
ZosteropsMorph_PCAcentroids <- data.frame(Group = character(), PC1 = numeric(), PC2 = numeric(), PC3 = numeric(), stringsAsFactors = FALSE)

# Loop through each unique species to calculate centroids
for (species in unique(pca_data$Species)) {
  group_scores <- pca_data[pca_data$Species == species, 1:3]  # Select PCA scores for the species
  centroid <- colMeans(group_scores, na.rm = TRUE)  # Calculate the centroid
  ZosteropsMorph_PCAcentroids <- rbind(ZosteropsMorph_PCAcentroids, 
                                        data.frame(Group = species, 
                                                   PC1 = centroid[1], 
                                                   PC2 = centroid[2], 
                                                   PC3 = centroid[3]))
}

# Print the centroids
print(ZosteropsMorph_PCAcentroids)
```
:::

::: {.cell-output .cell-output-stdout}
                  Group        PC1        PC2         PC3
    PC1        montanus  0.1466660 -0.5700858  0.25869647
    PC11         meyeni -1.1456456 -0.6333216 -0.17548308
    PC12       everetti -0.1796836 -0.5869601 -0.55563320
    PC13       nigrorum  0.2795344 -0.4716253  0.04205548
    PC14 erythropleurus  1.4899116  1.3071677 -0.53885532
    PC15      japonicus -2.4002728  1.0220466  0.29559118
    PC16        simplex  1.7614089  0.7106016  0.12306285
    PC17    palpebrosus  2.5407472  0.3162725 -0.21581544
:::

::: {#cb34 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
# Calculate the Euclidean distances between centroids
ZosteropsMorph_PCAdistance_matrix <- as.matrix(dist(ZosteropsMorph_PCAcentroids[, 2:4]))  # Exclude the Group column
ZosteropsMorph_PCAdistance_df <- as.data.frame(ZosteropsMorph_PCAdistance_matrix)

# Set row and column names for the distance data frame
rownames(ZosteropsMorph_PCAdistance_df) <- ZosteropsMorph_PCAcentroids$Group
colnames(ZosteropsMorph_PCAdistance_df) <- ZosteropsMorph_PCAcentroids$Group

# Print the distance data frame
print(ZosteropsMorph_PCAdistance_df)
```
:::

::: {.cell-output .cell-output-stdout}
                    montanus   meyeni  everetti  nigrorum erythropleurus japonicus
    montanus       0.0000000 1.364764 0.8774518 0.2725469      2.4422282  3.003855
    meyeni         1.3647637 0.000000 1.0391083 1.4507263      3.2929774  2.129846
    everetti       0.8774518 1.039108 0.0000000 0.7625057      2.5249851  2.871324
    nigrorum       0.2725469 1.450726 0.7625057 0.0000000      2.2285813  3.078425
    erythropleurus 2.4422282 3.292977 2.5249851 2.2285813      0.0000000  3.988876
    japonicus      3.0038548 2.129846 2.8713240 3.0784253      3.9888757  0.000000
    simplex        2.0654180 3.216555 2.4314881 1.8974126      0.9315243  4.176884
    palpebrosus    2.5966165 3.806947 2.8865288 2.4083944      1.4800282  5.017303
                     simplex palpebrosus
    montanus       2.0654180   2.5966165
    meyeni         3.2165548   3.8069472
    everetti       2.4314881   2.8865288
    nigrorum       1.8974126   2.4083944
    erythropleurus 0.9315243   1.4800282
    japonicus      4.1768838   5.0173033
    simplex        0.0000000   0.9368576
    palpebrosus    0.9368576   0.0000000
:::
:::

For the PCA produced from the SNP data Euclidean distances were also
calculated between species (see *Distance trees, PCA, UMAP, and DAPC
analyses*). Compare the genetic distances with those from the
morphometric dataset using Spearman's ⍴. Because different groupings
were used in the genetic versus morphometric PCAs in some cases we are
using the mean genetic distance. For example, in the genetic PCA *Z.
montanus* was divided into north, south, and Palawan groups. Here we are
taking the mean from the genetic distances between those groups and
using that in pairwise comparisons of genetic distance between *Z.
montanus* and other species. Below is the data manually entered into a
comma delimited (`csv`) `txt` file (`Zosterops_genetic_morpho_dist.csv`)
used in analyses of correlation between genetic and morphological
pairwise distances.

    pairwise_comp,genetic_dist,morpho_dist
    MONT_MEYE,1.60,1.36
    MONT_EVER,36.23,0.88
    MONT_NIGR,28.42,0.27
    MONT_ERYT,18.93,2.44
    MONT_JAPO,4.37,3.00
    MONT_SIMP,26.40,2.07
    MONT_PALP,35.81,2.60
    MEYE_EVER,37.13,1.04
    MEYE_NIGR,29.33,1.45
    MEYE_ERYT,20.43,3.29
    MEYE_JAPO,2.75,2.13
    MEYE_SIMP,27.33,3.22
    MEYE_PALP,37.22,3.81
    EVER_NIGR,7.82,0.76
    EVER_ERYT,28.28,2.52
    EVER_JAPO,38.43,2.87
    EVER_SIMP,37.80,2.43
    EVER_PALP,39.36,2.89
    NIGR_ERYT,21.81,2.23
    NIGR_JAPO,30.69,3.08
    NIGR_SIMP,32.50,1.90
    NIGR_PALP,35.39,2.41
    ERYT_JAPO,22.96,3.99
    ERYT_SIMP,25.85,0.93
    ERYT_PALP,18.54,1.48
    JAPO_SIMP,29.36,4.18
    JAPO_PALP,39.66,5.02
    SIMP_PALP,39.09,0.94

Correlation analysis using Spearman's ⍴ between pairwise comparisons for
genetic and morphological distance was calculated as follows. A plot of
morphological and genetic distances was produced and pairwise
comparisons involving *Z. japonicus* were highlighted (black points and
dashed line) from the remaining pairwise comparisons (open points and
solid line).

::: {.cell}
::: {#cb37 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
# Read the data from a CSV file
Zosterops_distance_data <- read.csv("Data/Morphometrics/Zosterops_genetic_morpho_dist.csv")

# Calculate the correlation for all comparisons using Spearman
correlation_all <- cor(Zosterops_distance_data$genetic_dist, Zosterops_distance_data$morpho_dist, method = "spearman")
print(paste("Correlation coefficient (all comparisons):", round(correlation_all, 3)))
```
:::

::: {.cell-output .cell-output-stdout}
    [1] "Correlation coefficient (all comparisons): 0.178"
:::

::: {#cb39 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
# Perform a statistical significance test for all comparisons using Spearman
cor_test_all <- cor.test(Zosterops_distance_data$genetic_dist, Zosterops_distance_data$morpho_dist, method = "spearman")
print(cor_test_all)
```
:::

::: {.cell-output .cell-output-stdout}
        Spearman's rank correlation rho

    data:  Zosterops_distance_data$genetic_dist and Zosterops_distance_data$morpho_dist
    S = 3004, p-value = 0.3635
    alternative hypothesis: true rho is not equal to 0
    sample estimates:
          rho 
    0.1778872 
:::

::: {#cb41 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
# Filter data for JAPO comparisons
Zosterops_JAPO_data <- Zosterops_distance_data[grepl("JAPO", Zosterops_distance_data$pairwise_comp), ]

# Calculate the correlation for JAPO comparisons using Spearman
correlation_JAPO <- cor(Zosterops_JAPO_data$genetic_dist, Zosterops_JAPO_data$morpho_dist, method = "spearman")
print(paste("Correlation coefficient (JAPO comparisons):", round(correlation_JAPO, 3)))
```
:::

::: {.cell-output .cell-output-stdout}
    [1] "Correlation coefficient (JAPO comparisons): 0.536"
:::

::: {#cb43 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
# Perform a statistical significance test for JAPO comparisons using Spearman
cor_test_JAPO <- cor.test(Zosterops_JAPO_data$genetic_dist, Zosterops_JAPO_data$morpho_dist, method = "spearman")
print(cor_test_JAPO)
```
:::

::: {.cell-output .cell-output-stdout}
        Spearman's rank correlation rho

    data:  Zosterops_JAPO_data$genetic_dist and Zosterops_JAPO_data$morpho_dist
    S = 26, p-value = 0.2357
    alternative hypothesis: true rho is not equal to 0
    sample estimates:
          rho 
    0.5357143 
:::

::: {#cb45 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
# Fit linear models for R-squared calculation
lm_model_all <- lm(morpho_dist ~ genetic_dist, data = Zosterops_distance_data)
r_squared_all <- summary(lm_model_all)$r.squared

lm_model_JAPO <- lm(morpho_dist ~ genetic_dist, data = Zosterops_JAPO_data)
r_squared_JAPO <- summary(lm_model_JAPO)$r.squared

# Plot the data
Zosterops_correlation_plot <- ggplot(Zosterops_distance_data, aes(x = genetic_dist, y = morpho_dist)) +
  geom_point(aes(shape = ifelse(grepl("JAPO", pairwise_comp), "filled", "open")), size = 3, color = "black", show.legend = FALSE) +  # Points based on shape, no legend
  scale_shape_manual(values = c("open" = 1, "filled" = 16)) +  # Open circles and filled circles
  labs(
       x = "Genetic Distance",
       y = "Morphological Distance") +
  theme_minimal() +
  theme(legend.position = "none")

# Display the plot
print(Zosterops_correlation_plot)
```
:::

::: {.cell-output-display}
<div>

![](ZosteropsMorphometrics_files/figure-html/Correlations%20between%20genetic%20and%20morphometric%20Euclidean%20distances.-1.png){.img-fluid
.figure-img width="672"}

</div>
:::
:::
:::

::: {#pca-for-subspecies .section .level3}
### PCA for subspecies {#pca-for-subspecies .anchored anchor-id="pca-for-subspecies"}

Conduct a PCA in which the groupings are subspecies. Only show a single
plot for two PCs and all subspecies.

::: {.cell}
::: {#cb46 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
# Group data by 'Name' (subspecies) and select relevant variables for PCA
ZosteropsMorph_subspecies <- ZosteropsMorph %>%
  select(Name, BillCulmen, BillNareTip, BillDepth, BillWidth, Tarsus, Wing, Tail) %>%
  group_by(Name)

# Perform PCA on the selected variables
pca_result <- prcomp(ZosteropsMorph_subspecies[, -1], center = TRUE, scale. = TRUE)

# Convert PCA result to a data frame for plotting
pca_data <- as.data.frame(pca_result$x)

# Add 'Name' variable to PCA data for coloring
pca_data$Name <- ZosteropsMorph_subspecies$Name

# Plot the first two principal components
ggplot(pca_data, aes(x = PC1, y = PC2, color = Name)) +
  geom_point(size = 3) + 
  labs(title = "PCA of Zosterops Morphological Measurements",
       x = "Principal Component 1",
       y = "Principal Component 2") +
  theme_minimal() +
  theme(legend.title = element_blank())
```
:::

::: {.cell-output-display}
<div>

![](ZosteropsMorphometrics_files/figure-html/PCA%20for%20subspecies-1.png){.img-fluid
.figure-img width="672"}

</div>
:::
:::
:::
:::

::: {#box-and-whisker-plots-and-pairwise-tests .section .level2}
## Box-and-whisker plots and pairwise tests {#box-and-whisker-plots-and-pairwise-tests .anchored anchor-id="box-and-whisker-plots-and-pairwise-tests"}

::: {#species-plots-and-summaries .section .level3}
### Species plots and summaries {#species-plots-and-summaries .anchored anchor-id="species-plots-and-summaries"}

Define color values for box plots to match prior color schemes.

::: {.cell}
::: {#cb47 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
species_colors <- c("#004949", "#DB6D00", "#D82632", "#FED439", "#FA9C88", "#924900", "#8DB6CD", "#008600")
```
:::
:::

Create box-and-whisker plots for each individual trait and every
species.

::: {.cell}
::: {#cb48 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
# Define a function to create boxplots for each trait
create_boxplot <- function(ZosteropsMorph_species, trait) {
  ggplot(ZosteropsMorph_species, aes_string(x = "Species", y = trait)) + 
    geom_boxplot(outlier.shape = NA) + # Boxplot without outliers
    geom_jitter(width = 0.2, aes(color = Species), size = 2, alpha = 0.5) + # Add jitter for individual points
    labs(title = paste("Boxplot of", trait, "by Species"), x = "Species", y = trait) + 
    scale_color_manual(values = species_colors) +
    theme_minimal() # Minimal theme for better aesthetics
}
# List of traits to plot
traits <- c("BillCulmen", "BillNareTip", "BillDepth", "BillWidth", "Tarsus", "Wing", "Tail")
# Loop through each trait and create boxplots
for (trait in traits) {
  print(create_boxplot(ZosteropsMorph_species, trait)) # Print each boxplot
}
```
:::

::: {.cell-output .cell-output-stderr}
    Warning: `aes_string()` was deprecated in ggplot2 3.0.0.
    ℹ Please use tidy evaluation idioms with `aes()`.
    ℹ See also `vignette("ggplot2-in-packages")` for more information.
:::

::: {.cell-output-display}
<div>

![](ZosteropsMorphometrics_files/figure-html/Box-and-whisker%20plots%20for%20morphometric%20traits.-1.png){.img-fluid
.figure-img width="672"}

</div>
:::

::: {.cell-output-display}
<div>

![](ZosteropsMorphometrics_files/figure-html/Box-and-whisker%20plots%20for%20morphometric%20traits.-2.png){.img-fluid
.figure-img width="672"}

</div>
:::

::: {.cell-output-display}
<div>

![](ZosteropsMorphometrics_files/figure-html/Box-and-whisker%20plots%20for%20morphometric%20traits.-3.png){.img-fluid
.figure-img width="672"}

</div>
:::

::: {.cell-output-display}
<div>

![](ZosteropsMorphometrics_files/figure-html/Box-and-whisker%20plots%20for%20morphometric%20traits.-4.png){.img-fluid
.figure-img width="672"}

</div>
:::

::: {.cell-output-display}
<div>

![](ZosteropsMorphometrics_files/figure-html/Box-and-whisker%20plots%20for%20morphometric%20traits.-5.png){.img-fluid
.figure-img width="672"}

</div>
:::

::: {.cell-output-display}
<div>

![](ZosteropsMorphometrics_files/figure-html/Box-and-whisker%20plots%20for%20morphometric%20traits.-6.png){.img-fluid
.figure-img width="672"}

</div>
:::

::: {.cell-output-display}
<div>

![](ZosteropsMorphometrics_files/figure-html/Box-and-whisker%20plots%20for%20morphometric%20traits.-7.png){.img-fluid
.figure-img width="672"}

</div>
:::
:::

Descriptive statistics for morphometric traits by species.

::: {.cell}
::: {#cb50 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
ZosteropsMorph_descriptive_stats_species <- ZosteropsMorph_species %>%
  select(Species, BillCulmen, BillNareTip, BillDepth, BillWidth, Tarsus, Wing, Tail) %>%  # Select relevant columns
  group_by(Species) %>%  # Group by 'Group'
  summarise(  # Summarize to get descriptive statistics
    Mean_BillCulmen = mean(BillCulmen, na.rm = TRUE),
    Median_BillCulmen = median(BillCulmen, na.rm = TRUE),
    SD_BillCulmen = sd(BillCulmen, na.rm = TRUE),
    
    Mean_BillNareTip = mean(BillNareTip, na.rm = TRUE),
    Median_BillNareTip = median(BillNareTip, na.rm = TRUE),
    SD_BillNareTip = sd(BillNareTip, na.rm = TRUE),
    
    Mean_BillDepth = mean(BillDepth, na.rm = TRUE),
    Median_BillDepth = median(BillDepth, na.rm = TRUE),
    SD_BillDepth = sd(BillDepth, na.rm = TRUE),
    
    Mean_BillWidth = mean(BillWidth, na.rm = TRUE),
    Median_BillWidth = median(BillWidth, na.rm = TRUE),
    SD_BillWidth = sd(BillWidth, na.rm = TRUE),
    
    Mean_Tarsus = mean(Tarsus, na.rm = TRUE),
    Median_Tarsus = median(Tarsus, na.rm = TRUE),
    SD_Tarsus = sd(Tarsus, na.rm = TRUE),
    
    Mean_Wing = mean(Wing, na.rm = TRUE),
    Median_Wing = median(Wing, na.rm = TRUE),
    SD_Wing = sd(Wing, na.rm = TRUE),
    
    Mean_Tail = mean(Tail, na.rm = TRUE),
    Median_Tail = median(Tail, na.rm = TRUE),
    SD_Tail = sd(Tail, na.rm = TRUE)
  )
# View the descriptive statistics table
print(ZosteropsMorph_descriptive_stats_species)
```
:::

::: {.cell-output .cell-output-stdout}
    # A tibble: 8 × 22
      Species       Mean_BillCulmen Median_BillCulmen SD_BillCulmen Mean_BillNareTip
      <chr>                   <dbl>             <dbl>         <dbl>            <dbl>
    1 erythropleur…            9.58               9.6         0.485             6.65
    2 everetti                10.2               10.1         0.632             7.58
    3 japonicus               12.0               12           1.34              8.35
    4 meyeni                  10.8               10.8         0.452             7.89
    5 montanus                10.5               10.4         0.655             7.63
    6 nigrorum                10.1               10.1         0.808             7.54
    7 palpebrosus              9.28               9.2         0.881             6.68
    8 simplex                  9.36               9.3         0.627             7.02
    # ℹ 17 more variables: Median_BillNareTip <dbl>, SD_BillNareTip <dbl>,
    #   Mean_BillDepth <dbl>, Median_BillDepth <dbl>, SD_BillDepth <dbl>,
    #   Mean_BillWidth <dbl>, Median_BillWidth <dbl>, SD_BillWidth <dbl>,
    #   Mean_Tarsus <dbl>, Median_Tarsus <dbl>, SD_Tarsus <dbl>, Mean_Wing <dbl>,
    #   Median_Wing <dbl>, SD_Wing <dbl>, Mean_Tail <dbl>, Median_Tail <dbl>,
    #   SD_Tail <dbl>
:::

::: {#cb52 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
write.csv(ZosteropsMorph_descriptive_stats_species)
```
:::

::: {.cell-output .cell-output-stdout}
    "","Species","Mean_BillCulmen","Median_BillCulmen","SD_BillCulmen","Mean_BillNareTip","Median_BillNareTip","SD_BillNareTip","Mean_BillDepth","Median_BillDepth","SD_BillDepth","Mean_BillWidth","Median_BillWidth","SD_BillWidth","Mean_Tarsus","Median_Tarsus","SD_Tarsus","Mean_Wing","Median_Wing","SD_Wing","Mean_Tail","Median_Tail","SD_Tail"
    "1","erythropleurus",9.5772,9.6,0.485253541975739,6.6472,6.6,0.457078767828916,2.7844,2.8,0.20236271066248,2.7984,2.8,0.210588065505463,16.0696,15.9,1.04636864122227,59.808,60,2.68497672243169,39.52,40,3.21610530507528
    "2","everetti",10.1930434782609,10.15,0.632476155247391,7.58065217391304,7.6,0.579510913228323,3.30695652173913,3.3,0.275760520623057,3.28652173913043,3.3,0.215779902177137,17.194347826087,17.2,1.29277247662862,55.6739130434783,55.25,2.51267319205031,40,41,3.23178657161089
    "3","japonicus",12.0345762711864,12,1.34391902726356,8.34745762711864,8.07,0.941481944852862,3.18389830508475,3.2,0.311459395422706,3.18135593220339,3.2,0.300301329283396,19.4820338983051,19.5,1.73327752086858,60.1016949152542,60.5,2.16711245395276,44.3050847457627,44,3.03573110712449
    "4","meyeni",10.7879166666667,10.75,0.452461664642447,7.89,7.9,0.518132096636772,3.27416666666667,3.2,0.240179582571163,3.46208333333333,3.49,0.261134301056766,18.5270833333333,18.25,1.022594650309,56.6666666666667,56,1.72995769404584,40.2083333333333,40.5,2.57038597451259
    "5","montanus",10.494693877551,10.43,0.655171660958373,7.62622448979592,7.585,0.551652653501926,3.07091836734694,3.1,0.242946206487756,3.2034693877551,3.205,0.309702557805003,17.3668367346939,17.38,0.971518735528045,55.7908163265306,55.5,2.54234597135819,37.4285714285714,37,2.98103974112126
    "6","nigrorum",10.1263265306122,10.06,0.807817775134423,7.54204081632653,7.6,0.655222543593131,3.1965306122449,3.12,0.341672059024977,3.10326530612245,3.1,0.345304139823999,17.5269387755102,17.5,1.52551385342999,54.5918367346939,53.5,3.7258576604753,38.8571428571429,38,3.46410161513776
    "7","palpebrosus",9.27916666666667,9.2,0.880700890184071,6.675,6.5,0.6243257232372,2.80833333333333,2.8,0.233901998553959,2.8,2.9,0.228416096288064,14.8791666666667,15,0.92123695987074,53.3958333333333,53.25,1.52500296982367,39,39,2.84375746535093
    "8","simplex",9.35689655172414,9.3,0.627267904989999,7.01931034482759,7.1,0.521583653299413,2.75310344827586,2.7,0.166906805653332,2.82655172413793,2.8,0.25992135983888,16.4072413793103,16.1,1.13234553204439,55.1379310344828,55,2.10397816954716,39.7931034482759,39,3.00451220600934
:::

::: {#cb54 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
ZosteropsMorph_descriptive_stats_species %>%
  gt(auto_align = FALSE)
```
:::

::: {.cell-output-display}
::: {#alsxqqlouw style="padding-left:0px;padding-right:0px;padding-top:10px;padding-bottom:10px;overflow-x:auto;overflow-y:auto;width:auto;height:auto;"}
  Species          Mean_BillCulmen   Median_BillCulmen   SD_BillCulmen   Mean_BillNareTip   Median_BillNareTip   SD_BillNareTip   Mean_BillDepth   Median_BillDepth   SD_BillDepth   Mean_BillWidth   Median_BillWidth   SD_BillWidth   Mean_Tarsus   Median_Tarsus   SD_Tarsus   Mean_Wing   Median_Wing   SD_Wing    Mean_Tail   Median_Tail   SD_Tail
  ---------------- ----------------- ------------------- --------------- ------------------ -------------------- ---------------- ---------------- ------------------ -------------- ---------------- ------------------ -------------- ------------- --------------- ----------- ----------- ------------- ---------- ----------- ------------- ----------
  erythropleurus   9.577200          9.60                0.4852535       6.647200           6.600                0.4570788        2.784400         2.80               0.2023627      2.798400         2.800              0.2105881      16.06960      15.90           1.0463686   59.80800    60.00         2.684977   39.52000    40.0          3.216105
  everetti         10.193043         10.15               0.6324762       7.580652           7.600                0.5795109        3.306957         3.30               0.2757605      3.286522         3.300              0.2157799      17.19435      17.20           1.2927725   55.67391    55.25         2.512673   40.00000    41.0          3.231787
  japonicus        12.034576         12.00               1.3439190       8.347458           8.070                0.9414819        3.183898         3.20               0.3114594      3.181356         3.200              0.3003013      19.48203      19.50           1.7332775   60.10169    60.50         2.167112   44.30508    44.0          3.035731
  meyeni           10.787917         10.75               0.4524617       7.890000           7.900                0.5181321        3.274167         3.20               0.2401796      3.462083         3.490              0.2611343      18.52708      18.25           1.0225947   56.66667    56.00         1.729958   40.20833    40.5          2.570386
  montanus         10.494694         10.43               0.6551717       7.626224           7.585                0.5516527        3.070918         3.10               0.2429462      3.203469         3.205              0.3097026      17.36684      17.38           0.9715187   55.79082    55.50         2.542346   37.42857    37.0          2.981040
  nigrorum         10.126327         10.06               0.8078178       7.542041           7.600                0.6552225        3.196531         3.12               0.3416721      3.103265         3.100              0.3453041      17.52694      17.50           1.5255139   54.59184    53.50         3.725858   38.85714    38.0          3.464102
  palpebrosus      9.279167          9.20                0.8807009       6.675000           6.500                0.6243257        2.808333         2.80               0.2339020      2.800000         2.900              0.2284161      14.87917      15.00           0.9212370   53.39583    53.25         1.525003   39.00000    39.0          2.843757
  simplex          9.356897          9.30                0.6272679       7.019310           7.100                0.5215837        2.753103         2.70               0.1669068      2.826552         2.800              0.2599214      16.40724      16.10           1.1323455   55.13793    55.00         2.103978   39.79310    39.0          3.004512
:::
:::
:::
:::

::: {#taxonomicbiogeographic-group-plots-summaries-and-t-tests .section .level3}
### Taxonomic/biogeographic group plots, summaries, and t-tests {#taxonomicbiogeographic-group-plots-summaries-and-t-tests .anchored anchor-id="taxonomicbiogeographic-group-plots-summaries-and-t-tests"}

Define colors for box-and-whisker plots for taxonomic/biogeographic
groups.

::: {.cell}
::: {#cb55 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
group_colors <- c("#004949", "#DB6D00", "#D82632", "#290AD8", "#FED439", "#B66DFF", "#FA9C88", "#924900", "#CDAA7D", "#8DB6CD", "#008600")
```
:::
:::

Test each trait within each taxonomic/biogeographic group for normality.

::: {.cell}
::: {#cb56 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
# Select relevant variables and group by taxonomic group separating montanus into NORTH and SOUTH groups and japonicus into CONTINENTAL and OCEANIC groups and create datasets with the original data and log transformed data. 
ZosteropsMorph_groups <- ZosteropsMorph %>%
  select(Group, BillCulmen, BillNareTip, BillDepth, BillWidth, Tarsus, Wing, Tail) %>%
  group_by(Group)

# Function to perform Kolmogorov-Smirnov test for each variable within each group
perform_ks_test <- function(group_data, variable) {
  # Create a list to store results
  results <- list()
  
  # Get unique groups
  unique_groups <- unique(group_data$Group)
  
  # Iterate over each unique group
  for (i in 1:length(unique_groups)) {
    # Filter data for the specific group
    group_name <- unique_groups[i]
    group_values <- group_data %>% filter(Group == group_name) %>% pull(variable)
    
    # Perform KS test with the first group's data as reference
    if (i == 1) {
      reference_values <- group_values
    } else {
      ks_test_result <- ks.test(group_values, reference_values)
      results[[group_name]] <- ks_test_result
    }
  }
  return(results)
}
```
:::
:::

Box and whisker plots by taxonomic/biogeographic group splitting *Z.
japonicus* into continental and oceanic groups, *Z. montanus* into north
and south groups, and *Z. nigrorum* into the mismatched *Z. nigrorum
catarmanensis* subspecies on Camiguin South and the remaining *Z.
nigrorum* samples.

::: {.cell}
::: {#cb57 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
# Define a function to create boxplots for each trait
create_boxplot <- function(data, trait) {
  ggplot(data, aes_string(x = "Group", y = trait)) +
    geom_boxplot(outlier.shape = NA) + # Boxplot without outliers
    geom_jitter(width = 0.2, aes(color = Group), size = 2, alpha = 0.5) + # Add jitter for individual points
    scale_color_manual(values = group_colors) + # Define colors for groups
    theme_minimal() + # Minimal theme for better aesthetics
    theme(axis.text.x = element_text(angle = 45, hjust = 1)) # Adjust labels on X axis
}

# List of traits to plot
traits <- c("BillCulmen", "BillNareTip", "BillDepth", "BillWidth", "Tarsus", "Wing", "Tail")

# Loop through each trait and create boxplots
for (trait in traits) {
  assign(paste0("boxplot_groups_", trait), create_boxplot(ZosteropsMorph_groups, trait)) # Create and save boxplot as an object named by trait
}
boxplot_groups_BillCulmen
```
:::

::: {.cell-output-display}
<div>

![](ZosteropsMorphometrics_files/figure-html/Box-and-whisker%20plots%20for%20morphometric%20traits%20by%20taxonomic/biogeographic%20group.-1.png){.img-fluid
.figure-img width="672"}

</div>
:::

::: {#cb58 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
boxplot_groups_BillNareTip
```
:::

::: {.cell-output-display}
<div>

![](ZosteropsMorphometrics_files/figure-html/Box-and-whisker%20plots%20for%20morphometric%20traits%20by%20taxonomic/biogeographic%20group.-2.png){.img-fluid
.figure-img width="672"}

</div>
:::

::: {#cb59 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
boxplot_groups_BillDepth
```
:::

::: {.cell-output-display}
<div>

![](ZosteropsMorphometrics_files/figure-html/Box-and-whisker%20plots%20for%20morphometric%20traits%20by%20taxonomic/biogeographic%20group.-3.png){.img-fluid
.figure-img width="672"}

</div>
:::

::: {#cb60 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
boxplot_groups_BillWidth
```
:::

::: {.cell-output-display}
<div>

![](ZosteropsMorphometrics_files/figure-html/Box-and-whisker%20plots%20for%20morphometric%20traits%20by%20taxonomic/biogeographic%20group.-4.png){.img-fluid
.figure-img width="672"}

</div>
:::

::: {#cb61 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
boxplot_groups_Tarsus
```
:::

::: {.cell-output-display}
<div>

![](ZosteropsMorphometrics_files/figure-html/Box-and-whisker%20plots%20for%20morphometric%20traits%20by%20taxonomic/biogeographic%20group.-5.png){.img-fluid
.figure-img width="672"}

</div>
:::

::: {#cb62 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
boxplot_groups_Wing
```
:::

::: {.cell-output-display}
<div>

![](ZosteropsMorphometrics_files/figure-html/Box-and-whisker%20plots%20for%20morphometric%20traits%20by%20taxonomic/biogeographic%20group.-6.png){.img-fluid
.figure-img width="672"}

</div>
:::

::: {#cb63 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
boxplot_groups_Tail
```
:::

::: {.cell-output-display}
<div>

![](ZosteropsMorphometrics_files/figure-html/Box-and-whisker%20plots%20for%20morphometric%20traits%20by%20taxonomic/biogeographic%20group.-7.png){.img-fluid
.figure-img width="672"}

</div>
:::
:::

Isolate just the legend from one of the group box-and-whisker figures.

::: {.cell}
::: {#cb64 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
Zosterops_groups_legend <- cowplot::get_legend(boxplot_groups_Tail + theme(legend.position = "right"))
```
:::

::: {.cell-output .cell-output-stderr}
    Warning in get_plot_component(plot, "guide-box"): Multiple components found;
    returning the first one. To return all, use `return_all = TRUE`.
:::

::: {#cb66 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
ggsave("boxplot_legend.png", plot = Zosterops_groups_legend, width = 1.75, height = 3)
```
:::
:::

Combine plots into a single figure and add the figure legend.

::: {.cell}
::: {#cb67 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
ZosteropsMorph_groups_combined <- grid.arrange(
  # Plot A: Bill Culmen
  boxplot_groups_BillCulmen + 
    theme(legend.position = "none",
          axis.title.x = element_blank(),
          axis.text.x = element_blank(), 
          axis.title.y = element_text(size = 19),
          axis.text.y = element_text(size = 15)) +
    scale_y_continuous(limits = c(7.5, NA), name = "Bill length culmen (mm)") + 
    annotate("text", x = Inf, y = Inf, label = "a.", hjust = 1, vjust = 1.3, size = 12) +
    theme(panel.border = element_rect(colour = "black", fill = NA, size = 1)),
  
  # Plot B: Bill Nare Tip
  boxplot_groups_BillNareTip + 
    theme(legend.position = "none",
          axis.title.x = element_blank(),
          axis.text.x = element_blank(), 
          axis.title.y = element_text(size = 19),
          axis.text.y = element_text(size = 15)) + 
    scale_y_continuous(limits = c(5, NA), name = "Bill length nare-to-tip (mm)") + 
    annotate("text", x = Inf, y = Inf, label = "b.", hjust = 1, vjust = 1.2, size = 12) +
    theme(panel.border = element_rect(colour = "black", fill = NA, size = 1)),
  
  # Plot C: Bill Depth
  boxplot_groups_BillDepth + 
    theme(legend.position = "none",
          axis.title.x = element_blank(),
          axis.text.x = element_blank(), 
          axis.title.y = element_text(size = 19),
          axis.text.y = element_text(size = 15)) +
    scale_y_continuous(limits = c(1.5, NA), name = "Bill depth (mm)") + 
    annotate("text", x = Inf, y = Inf, label = "c.", hjust = 1, vjust = 1.3, size = 12) +
    theme(panel.border = element_rect(colour = "black", fill = NA, size = 1)),
  
  # Plot D: Bill Width
  boxplot_groups_BillWidth + 
    theme(legend.position = "none",
          axis.title.x = element_blank(),
          axis.text.x = element_blank(), 
          axis.title.y = element_text(size = 19),
          axis.text.y = element_text(size = 15)) + 
    scale_y_continuous(limits = c(2, NA), name = "Bill width (mm)") + 
    annotate("text", x = Inf, y = Inf, label = "d.", hjust = 1, vjust = 1.2, size = 12) +
    theme(panel.border = element_rect(colour = "black", fill = NA, size = 1)),
  
  # Plot E: Tarsus
  boxplot_groups_Tarsus + 
    theme(legend.position = "none",
          axis.title.x = element_blank(),
          axis.text.x = element_blank(), 
          axis.title.y = element_text(size = 19),
          axis.text.y = element_text(size = 15)) +
    scale_y_continuous(limits = c(10, NA), name = "Tarsus length (mm)") + 
    annotate("text", x = Inf, y = Inf, label = "e.", hjust = 1, vjust = 1.3, size = 12) +
    theme(panel.border = element_rect(colour = "black", fill = NA, size = 1)),
  
  # Plot F: Wing
  boxplot_groups_Wing + 
    theme(legend.position = "none",
          axis.title.x = element_blank(),
          axis.text.x = element_blank(), 
          axis.title.y = element_text(size = 19),
          axis.text.y = element_text(size = 15)) + 
    scale_y_continuous(limits = c(48, NA), name = "Wing cord length (mm)") + 
    annotate("text", x = Inf, y = Inf, label = "f.", hjust = 1, vjust = 1.2, size = 12) +
    theme(panel.border = element_rect(colour = "black", fill = NA, size = 1)),
  
  # Plot G: Tail
  boxplot_groups_Tail + 
    theme(legend.position = "none",
          axis.title.x = element_blank(),
          axis.text.x = element_blank(), 
          axis.title.y = element_text(size = 19),
          axis.text.y = element_text(size = 15)) +
    scale_y_continuous(limits = c(25, NA), name = "Tail length (mm)") + 
    annotate("text", x = Inf, y = Inf, label = "g.", hjust = 1, vjust = 0.9, size = 12) +
    theme(panel.border = element_rect(colour = "black", fill = NA, size = 1)),
  
  # Add image in 4th row, 2nd column
  grid::rasterGrob(png::readPNG("boxplot_legend.png"), interpolate = TRUE), 
  ncol = 2, 
  layout_matrix = rbind(c(1, 2), 
                        c(3, 4), 
                        c(5, 6), 
                        c(7, 8))
)
```
:::

::: {.cell-output .cell-output-stderr}
    Warning: The `size` argument of `element_rect()` is deprecated as of ggplot2 3.4.0.
    ℹ Please use the `linewidth` argument instead.
:::

::: {.cell-output-display}
<div>

![](ZosteropsMorphometrics_files/figure-html/Combine%20all%20group%20trait%20boxplots%20into%20a%20single%20figure.-1.png){.img-fluid
.figure-img width="1728"}

</div>
:::
:::

Produce descriptive statistics for morphometric traits by
taxonomic/biogeographic group.

::: {.cell}
::: {#cb69 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
ZosteropsMorph_descriptive_stats_groups <- ZosteropsMorph_groups %>%
  select(Group, BillCulmen, BillNareTip, BillDepth, BillWidth, Tarsus, Wing, Tail) %>%  # Select relevant columns
  group_by(Group) %>%  # Group by 'Group'
  summarise(  # Summarize to get descriptive statistics
    Mean_BillCulmen = mean(BillCulmen, na.rm = TRUE),
    Median_BillCulmen = median(BillCulmen, na.rm = TRUE),
    SD_BillCulmen = sd(BillCulmen, na.rm = TRUE),
    
    Mean_BillNareTip = mean(BillNareTip, na.rm = TRUE),
    Median_BillNareTip = median(BillNareTip, na.rm = TRUE),
    SD_BillNareTip = sd(BillNareTip, na.rm = TRUE),
    
    Mean_BillDepth = mean(BillDepth, na.rm = TRUE),
    Median_BillDepth = median(BillDepth, na.rm = TRUE),
    SD_BillDepth = sd(BillDepth, na.rm = TRUE),
    
    Mean_BillWidth = mean(BillWidth, na.rm = TRUE),
    Median_BillWidth = median(BillWidth, na.rm = TRUE),
    SD_BillWidth = sd(BillWidth, na.rm = TRUE),
    
    Mean_Tarsus = mean(Tarsus, na.rm = TRUE),
    Median_Tarsus = median(Tarsus, na.rm = TRUE),
    SD_Tarsus = sd(Tarsus, na.rm = TRUE),
    
    Mean_Wing = mean(Wing, na.rm = TRUE),
    Median_Wing = median(Wing, na.rm = TRUE),
    SD_Wing = sd(Wing, na.rm = TRUE),
    
    Mean_Tail = mean(Tail, na.rm = TRUE),
    Median_Tail = median(Tail, na.rm = TRUE),
    SD_Tail = sd(Tail, na.rm = TRUE)
  )
# View the descriptive statistics table
print(ZosteropsMorph_descriptive_stats_groups)
```
:::

::: {.cell-output .cell-output-stdout}
    # A tibble: 11 × 22
       Group        Mean_BillCulmen Median_BillCulmen SD_BillCulmen Mean_BillNareTip
       <chr>                  <dbl>             <dbl>         <dbl>            <dbl>
     1 erythropleu…            9.58               9.6         0.485             6.65
     2 everetti               10.2               10.1         0.632             7.58
     3 japonicus C…           11.1               11           0.830             7.70
     4 japonicus O…           12.9               12.8         1.14              8.89
     5 meyeni                 10.8               10.8         0.452             7.89
     6 montanus NO…           10.4               10.2         0.503             7.38
     7 montanus SO…           10.5               10.4         0.680             7.67
     8 nigrorum                9.79               9.9         0.642             7.31
     9 nigrorum CS            11.1               11.1         0.309             8.19
    10 palpebrosus             9.28               9.2         0.881             6.68
    11 simplex                 9.36               9.3         0.627             7.02
    # ℹ 17 more variables: Median_BillNareTip <dbl>, SD_BillNareTip <dbl>,
    #   Mean_BillDepth <dbl>, Median_BillDepth <dbl>, SD_BillDepth <dbl>,
    #   Mean_BillWidth <dbl>, Median_BillWidth <dbl>, SD_BillWidth <dbl>,
    #   Mean_Tarsus <dbl>, Median_Tarsus <dbl>, SD_Tarsus <dbl>, Mean_Wing <dbl>,
    #   Median_Wing <dbl>, SD_Wing <dbl>, Mean_Tail <dbl>, Median_Tail <dbl>,
    #   SD_Tail <dbl>
:::

::: {#cb71 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
write.csv(ZosteropsMorph_descriptive_stats_groups)
```
:::

::: {.cell-output .cell-output-stdout}
    "","Group","Mean_BillCulmen","Median_BillCulmen","SD_BillCulmen","Mean_BillNareTip","Median_BillNareTip","SD_BillNareTip","Mean_BillDepth","Median_BillDepth","SD_BillDepth","Mean_BillWidth","Median_BillWidth","SD_BillWidth","Mean_Tarsus","Median_Tarsus","SD_Tarsus","Mean_Wing","Median_Wing","SD_Wing","Mean_Tail","Median_Tail","SD_Tail"
    "1","erythropleurus",9.5772,9.6,0.485253541975739,6.6472,6.6,0.457078767828916,2.7844,2.8,0.20236271066248,2.7984,2.8,0.210588065505463,16.0696,15.9,1.04636864122227,59.808,60,2.68497672243169,39.52,40,3.21610530507528
    "2","everetti",10.1930434782609,10.15,0.632476155247391,7.58065217391304,7.6,0.579510913228323,3.30695652173913,3.3,0.275760520623057,3.28652173913043,3.3,0.215779902177137,17.194347826087,17.2,1.29277247662862,55.6739130434783,55.25,2.51267319205031,40,41,3.23178657161089
    "3","japonicus CONTINENTAL",11.0655555555556,11,0.830043248795986,7.69962962962963,7.7,0.406490434001187,2.94851851851852,3,0.198914432776889,2.99481481481482,3.02,0.263998402826905,18.2814814814815,17.9,1.30742760853783,58.3703703703704,58.5,1.74086954727423,43.2962962962963,44,3.20834027083277
    "4","japonicus OCEANIC",12.8521875,12.75,1.13729938854883,8.8940625,8.75,0.919715451700565,3.3825,3.4,0.243602002216466,3.33875,3.315,0.23322078698922,20.495,20.35,1.36844625809358,61.5625,61.5,1.19643287020343,45.15625,45,2.64098435949492
    "5","meyeni",10.7879166666667,10.75,0.452461664642447,7.89,7.9,0.518132096636772,3.27416666666667,3.2,0.240179582571163,3.46208333333333,3.49,0.261134301056766,18.5270833333333,18.25,1.022594650309,56.6666666666667,56,1.72995769404584,40.2083333333333,40.5,2.57038597451259
    "6","montanus NORTH",10.3986666666667,10.2,0.503457569025954,7.38066666666667,7.1,0.606058303025927,2.88266666666667,2.9,0.256026412327955,3.09266666666667,3,0.327707767610688,16.9973333333333,17.2,1.08673473348025,53.9666666666667,54.5,1.71616959978846,36.6,36,1.95667356208731
    "7","montanus SOUTH",10.5120481927711,10.44,0.680076679744321,7.67060240963855,7.66,0.533155240737471,3.10493975903614,3.1,0.225774404423141,3.22349397590361,3.22,0.304095755678708,17.4336144578313,17.4,0.94094734088843,56.1204819277108,56,2.53462649560648,37.578313253012,38,3.11612831198804
    "8","nigrorum",9.78583333333333,9.9,0.642407858873829,7.30722222222222,7.21,0.588361458925724,3.07583333333333,3.1,0.284809460115756,2.99888888888889,3,0.335335889415611,16.9505555555556,16.75,1.31760376537853,52.875,52.75,2.55056016256373,38.1666666666667,38,3.41843740409478
    "9","nigrorum CS",11.0692307692308,11.1,0.309258832761532,8.19230769230769,8.2,0.290004420832794,3.53076923076923,3.6,0.256205046088139,3.39230769230769,3.4,0.160527975036225,19.1230769230769,19.2,0.698991948158019,59.3461538461538,59,1.79565001444017,40.7692307692308,41,2.91987003574492
    "10","palpebrosus",9.27916666666667,9.2,0.880700890184071,6.675,6.5,0.6243257232372,2.80833333333333,2.8,0.233901998553959,2.8,2.9,0.228416096288064,14.8791666666667,15,0.92123695987074,53.3958333333333,53.25,1.52500296982367,39,39,2.84375746535093
    "11","simplex",9.35689655172414,9.3,0.627267904989999,7.01931034482759,7.1,0.521583653299413,2.75310344827586,2.7,0.166906805653332,2.82655172413793,2.8,0.25992135983888,16.4072413793103,16.1,1.13234553204439,55.1379310344828,55,2.10397816954716,39.7931034482759,39,3.00451220600934
:::

::: {#cb73 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
library(gt)
ZosteropsMorph_descriptive_stats_groups %>%
  gt(auto_align = FALSE)
```
:::

::: {.cell-output-display}
::: {#yroywzdjny style="padding-left:0px;padding-right:0px;padding-top:10px;padding-bottom:10px;overflow-x:auto;overflow-y:auto;width:auto;height:auto;"}
  Group                   Mean_BillCulmen   Median_BillCulmen   SD_BillCulmen   Mean_BillNareTip   Median_BillNareTip   SD_BillNareTip   Mean_BillDepth   Median_BillDepth   SD_BillDepth   Mean_BillWidth   Median_BillWidth   SD_BillWidth   Mean_Tarsus   Median_Tarsus   SD_Tarsus   Mean_Wing   Median_Wing   SD_Wing    Mean_Tail   Median_Tail   SD_Tail
  ----------------------- ----------------- ------------------- --------------- ------------------ -------------------- ---------------- ---------------- ------------------ -------------- ---------------- ------------------ -------------- ------------- --------------- ----------- ----------- ------------- ---------- ----------- ------------- ----------
  erythropleurus          9.577200          9.60                0.4852535       6.647200           6.60                 0.4570788        2.784400         2.8                0.2023627      2.798400         2.800              0.2105881      16.06960      15.90           1.0463686   59.80800    60.00         2.684977   39.52000    40.0          3.216105
  everetti                10.193043         10.15               0.6324762       7.580652           7.60                 0.5795109        3.306957         3.3                0.2757605      3.286522         3.300              0.2157799      17.19435      17.20           1.2927725   55.67391    55.25         2.512673   40.00000    41.0          3.231787
  japonicus CONTINENTAL   11.065556         11.00               0.8300432       7.699630           7.70                 0.4064904        2.948519         3.0                0.1989144      2.994815         3.020              0.2639984      18.28148      17.90           1.3074276   58.37037    58.50         1.740870   43.29630    44.0          3.208340
  japonicus OCEANIC       12.852187         12.75               1.1372994       8.894063           8.75                 0.9197155        3.382500         3.4                0.2436020      3.338750         3.315              0.2332208      20.49500      20.35           1.3684463   61.56250    61.50         1.196433   45.15625    45.0          2.640984
  meyeni                  10.787917         10.75               0.4524617       7.890000           7.90                 0.5181321        3.274167         3.2                0.2401796      3.462083         3.490              0.2611343      18.52708      18.25           1.0225947   56.66667    56.00         1.729958   40.20833    40.5          2.570386
  montanus NORTH          10.398667         10.20               0.5034576       7.380667           7.10                 0.6060583        2.882667         2.9                0.2560264      3.092667         3.000              0.3277078      16.99733      17.20           1.0867347   53.96667    54.50         1.716170   36.60000    36.0          1.956674
  montanus SOUTH          10.512048         10.44               0.6800767       7.670602           7.66                 0.5331552        3.104940         3.1                0.2257744      3.223494         3.220              0.3040958      17.43361      17.40           0.9409473   56.12048    56.00         2.534626   37.57831    38.0          3.116128
  nigrorum                9.785833          9.90                0.6424079       7.307222           7.21                 0.5883615        3.075833         3.1                0.2848095      2.998889         3.000              0.3353359      16.95056      16.75           1.3176038   52.87500    52.75         2.550560   38.16667    38.0          3.418437
  nigrorum CS             11.069231         11.10               0.3092588       8.192308           8.20                 0.2900044        3.530769         3.6                0.2562050      3.392308         3.400              0.1605280      19.12308      19.20           0.6989919   59.34615    59.00         1.795650   40.76923    41.0          2.919870
  palpebrosus             9.279167          9.20                0.8807009       6.675000           6.50                 0.6243257        2.808333         2.8                0.2339020      2.800000         2.900              0.2284161      14.87917      15.00           0.9212370   53.39583    53.25         1.525003   39.00000    39.0          2.843757
  simplex                 9.356897          9.30                0.6272679       7.019310           7.10                 0.5215837        2.753103         2.7                0.1669068      2.826552         2.800              0.2599214      16.40724      16.10           1.1323455   55.13793    55.00         2.103978   39.79310    39.0          3.004512
:::
:::
:::

Conduct Wilcoxon rank-order pairwise tests among
taxnonomic/biogeographic groups for each morphometric trait.

::: {.cell data-label="Nonparametric Wilcoxon pairwise tests."}
::: {#cb74 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
# Conduct a nonparametric Wilcoxon paired test for each measurement. 
WILCOX_BillCulmen <- pairwise.wilcox.test(ZosteropsMorph_groups$BillCulmen, ZosteropsMorph_groups$Group, p.adjust.method="bonferroni", exact = FALSE)
WILCOX_BillNareTip <- pairwise.wilcox.test(ZosteropsMorph_groups$BillNareTip, ZosteropsMorph_groups$Group, p.adjust.method="bonferroni", exact = FALSE)
WILCOX_BillDepth <- pairwise.wilcox.test(ZosteropsMorph_groups$BillDepth, ZosteropsMorph_groups$Group, p.adjust.method="bonferroni", exact = FALSE)
WILCOX_BillWidth <- pairwise.wilcox.test(ZosteropsMorph_groups$BillWidth, ZosteropsMorph_groups$Group, p.adjust.method="bonferroni", exact = FALSE)
WILCOX_Tarsus <- pairwise.wilcox.test(ZosteropsMorph_groups$Tarsus, ZosteropsMorph_groups$Group, p.adjust.method="bonferroni", exact = FALSE)
WILCOX_Wing <- pairwise.wilcox.test(ZosteropsMorph_groups$Wing, ZosteropsMorph_groups$Group, p.adjust.method="bonferroni", exact = FALSE)
WILCOX_Tail <- pairwise.wilcox.test(ZosteropsMorph_groups$Tail, ZosteropsMorph_groups$Group, p.adjust.method="bonferroni", exact = FALSE)
WILCOX_BillCulmen
```
:::

::: {.cell-output .cell-output-stdout}
        Pairwise comparisons using Wilcoxon rank sum test with continuity correction 

    data:  ZosteropsMorph_groups$BillCulmen and ZosteropsMorph_groups$Group 

                          erythropleurus everetti japonicus CONTINENTAL
    everetti              0.00150        -        -                    
    japonicus CONTINENTAL 1.6e-06        0.00130  -                    
    japonicus OCEANIC     7.6e-09        3.6e-11  9.8e-06              
    meyeni                5.4e-07        0.00321  1.00000              
    montanus NORTH        0.00291        1.00000  0.47375              
    montanus SOUTH        2.8e-06        0.89995  0.27823              
    nigrorum              1.00000        0.24517  9.9e-06              
    nigrorum CS           3.3e-05        0.00066  1.00000              
    palpebrosus           1.00000        0.00172  9.3e-06              
    simplex               1.00000        2.5e-05  1.9e-07              
                          japonicus OCEANIC meyeni  montanus NORTH montanus SOUTH
    everetti              -                 -       -              -             
    japonicus CONTINENTAL -                 -       -              -             
    japonicus OCEANIC     -                 -       -              -             
    meyeni                6.7e-07           -       -              -             
    montanus NORTH        1.3e-05           1.00000 -              -             
    montanus SOUTH        1.2e-12           1.00000 1.00000        -             
    nigrorum              2.0e-10           6.9e-06 0.15836        0.00012       
    nigrorum CS           0.00042           1.00000 0.06790        0.24911       
    palpebrosus           2.5e-08           5.2e-05 0.01006        3.8e-06       
    simplex               1.4e-09           2.6e-07 0.00035        1.1e-08       
                          nigrorum nigrorum CS palpebrosus
    everetti              -        -           -          
    japonicus CONTINENTAL -        -           -          
    japonicus OCEANIC     -        -           -          
    meyeni                -        -           -          
    montanus NORTH        -        -           -          
    montanus SOUTH        -        -           -          
    nigrorum              -        -           -          
    nigrorum CS           9.4e-05  -           -          
    palpebrosus           0.46233  0.00031     -          
    simplex               0.63558  2.7e-05     1.00000    

    P value adjustment method: bonferroni 
:::

::: {#cb76 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
WILCOX_BillNareTip
```
:::

::: {.cell-output .cell-output-stdout}
        Pairwise comparisons using Wilcoxon rank sum test with continuity correction 

    data:  ZosteropsMorph_groups$BillNareTip and ZosteropsMorph_groups$Group 

                          erythropleurus everetti japonicus CONTINENTAL
    everetti              1.0e-06        -        -                    
    japonicus CONTINENTAL 1.0e-06        1.00000  -                    
    japonicus OCEANIC     8.4e-09        3.9e-07  6.5e-05              
    meyeni                9.2e-07        1.00000  1.00000              
    montanus NORTH        0.02324        1.00000  1.00000              
    montanus SOUTH        4.5e-09        1.00000  1.00000              
    nigrorum              0.00211        1.00000  0.22983              
    nigrorum CS           3.3e-05        0.01751  0.04335              
    palpebrosus           1.00000        6.2e-05  5.2e-05              
    simplex               0.10937        0.00267  0.00014              
                          japonicus OCEANIC meyeni  montanus NORTH montanus SOUTH
    everetti              -                 -       -              -             
    japonicus CONTINENTAL -                 -       -              -             
    japonicus OCEANIC     -                 -       -              -             
    meyeni                0.00488           -       -              -             
    montanus NORTH        0.00029           0.53464 -              -             
    montanus SOUTH        5.3e-08           1.00000 1.00000        -             
    nigrorum              6.9e-08           0.01842 1.00000        0.09930       
    nigrorum CS           1.00000           1.00000 0.03503        0.03754       
    palpebrosus           6.6e-08           3.2e-05 0.10798        7.0e-07       
    simplex               2.6e-09           3.0e-05 1.00000        3.4e-05       
                          nigrorum nigrorum CS palpebrosus
    everetti              -        -           -          
    japonicus CONTINENTAL -        -           -          
    japonicus OCEANIC     -        -           -          
    meyeni                -        -           -          
    montanus NORTH        -        -           -          
    montanus SOUTH        -        -           -          
    nigrorum              -        -           -          
    nigrorum CS           0.00091  -           -          
    palpebrosus           0.01332  0.00014     -          
    simplex               1.00000  1.9e-05     0.44390    

    P value adjustment method: bonferroni 
:::

::: {#cb78 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
WILCOX_BillDepth
```
:::

::: {.cell-output .cell-output-stdout}
        Pairwise comparisons using Wilcoxon rank sum test with continuity correction 

    data:  ZosteropsMorph_groups$BillDepth and ZosteropsMorph_groups$Group 

                          erythropleurus everetti japonicus CONTINENTAL
    everetti              5.3e-08        -        -                    
    japonicus CONTINENTAL 0.29629        3.1e-06  -                    
    japonicus OCEANIC     1.5e-07        1.00000  2.3e-06              
    meyeni                4.0e-06        1.00000  0.00104              
    montanus NORTH        1.00000        0.00023  1.00000              
    montanus SOUTH        3.3e-06        0.00044  0.07395              
    nigrorum              0.00260        0.01096  1.00000              
    nigrorum CS           5.9e-05        0.41280  0.00011              
    palpebrosus           1.00000        5.2e-07  1.00000              
    simplex               1.00000        3.3e-10  0.02413              
                          japonicus OCEANIC meyeni  montanus NORTH montanus SOUTH
    everetti              -                 -       -              -             
    japonicus CONTINENTAL -                 -       -              -             
    japonicus OCEANIC     -                 -       -              -             
    meyeni                1.00000           -       -              -             
    montanus NORTH        0.00020           0.00332 -              -             
    montanus SOUTH        1.9e-05           0.32589 0.10337        -             
    nigrorum              0.00102           0.44126 1.00000        1.00000       
    nigrorum CS           1.00000           0.50174 0.00134        0.00040       
    palpebrosus           7.1e-07           3.5e-05 1.00000        7.5e-05       
    simplex               5.8e-09           1.0e-07 1.00000        7.9e-09       
                          nigrorum nigrorum CS palpebrosus
    everetti              -        -           -          
    japonicus CONTINENTAL -        -           -          
    japonicus OCEANIC     -        -           -          
    meyeni                -        -           -          
    montanus NORTH        -        -           -          
    montanus SOUTH        -        -           -          
    nigrorum              -        -           -          
    nigrorum CS           0.00268  -           -          
    palpebrosus           0.01605  0.00012     -          
    simplex               4.5e-05  1.4e-05     1.00000    

    P value adjustment method: bonferroni 
:::

::: {#cb80 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
WILCOX_BillWidth
```
:::

::: {.cell-output .cell-output-stdout}
        Pairwise comparisons using Wilcoxon rank sum test with continuity correction 

    data:  ZosteropsMorph_groups$BillWidth and ZosteropsMorph_groups$Group 

                          erythropleurus everetti japonicus CONTINENTAL
    everetti              2.1e-08        -        -                    
    japonicus CONTINENTAL 0.14925        0.00081  -                    
    japonicus OCEANIC     1.8e-07        1.00000  0.00022              
    meyeni                7.4e-07        0.24209  2.2e-05              
    montanus NORTH        0.34908        1.00000  1.00000              
    montanus SOUTH        7.9e-07        1.00000  0.03850              
    nigrorum              0.54659        0.00084  1.00000              
    nigrorum CS           5.1e-05        1.00000  0.00085              
    palpebrosus           1.00000        1.6e-08  0.15955              
    simplex               1.00000        6.3e-08  0.75412              
                          japonicus OCEANIC meyeni  montanus NORTH montanus SOUTH
    everetti              -                 -       -              -             
    japonicus CONTINENTAL -                 -       -              -             
    japonicus OCEANIC     -                 -       -              -             
    meyeni                1.00000           -       -              -             
    montanus NORTH        0.83136           0.07681 -              -             
    montanus SOUTH        1.00000           0.04765 1.00000        -             
    nigrorum              0.00109           0.00012 1.00000        0.01903       
    nigrorum CS           1.00000           1.00000 0.73627        1.00000       
    palpebrosus           4.0e-07           1.3e-06 1.00000        1.6e-06       
    simplex               2.9e-07           5.6e-07 1.00000        2.3e-06       
                          nigrorum nigrorum CS palpebrosus
    everetti              -        -           -          
    japonicus CONTINENTAL -        -           -          
    japonicus OCEANIC     -        -           -          
    meyeni                -        -           -          
    montanus NORTH        -        -           -          
    montanus SOUTH        -        -           -          
    nigrorum              -        -           -          
    nigrorum CS           0.01061  -           -          
    palpebrosus           1.00000  4.6e-05     -          
    simplex               1.00000  6.5e-05     1.00000    

    P value adjustment method: bonferroni 
:::

::: {#cb82 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
WILCOX_Tarsus
```
:::

::: {.cell-output .cell-output-stdout}
        Pairwise comparisons using Wilcoxon rank sum test with continuity correction 

    data:  ZosteropsMorph_groups$Tarsus and ZosteropsMorph_groups$Group 

                          erythropleurus everetti japonicus CONTINENTAL
    everetti              0.00706        -        -                    
    japonicus CONTINENTAL 1.2e-05        0.04931  -                    
    japonicus OCEANIC     1.3e-08        5.3e-10  3.7e-05              
    meyeni                4.1e-06        0.00137  1.00000              
    montanus NORTH        0.43648        1.00000  0.23073              
    montanus SOUTH        6.1e-06        1.00000  0.13332              
    nigrorum              0.14493        1.00000  0.00889              
    nigrorum CS           0.00010        0.00033  0.45087              
    palpebrosus           0.00997        6.0e-08  7.9e-08              
    simplex               1.00000        0.15187  4.5e-05              
                          japonicus OCEANIC meyeni  montanus NORTH montanus SOUTH
    everetti              -                 -       -              -             
    japonicus CONTINENTAL -                 -       -              -             
    japonicus OCEANIC     -                 -       -              -             
    meyeni                0.00015           -       -              -             
    montanus NORTH        7.4e-06           0.01348 -              -             
    montanus SOUTH        6.8e-13           0.00057 1.00000        -             
    nigrorum              2.3e-09           0.00029 1.00000        0.80284       
    nigrorum CS           0.04337           1.00000 0.00184        3.8e-05       
    palpebrosus           1.2e-08           1.7e-07 0.00048        4.1e-11       
    simplex               5.3e-09           1.1e-05 1.00000        0.00030       
                          nigrorum nigrorum CS palpebrosus
    everetti              -        -           -          
    japonicus CONTINENTAL -        -           -          
    japonicus OCEANIC     -        -           -          
    meyeni                -        -           -          
    montanus NORTH        -        -           -          
    montanus SOUTH        -        -           -          
    nigrorum              -        -           -          
    nigrorum CS           0.00027  -           -          
    palpebrosus           3.3e-06  4.1e-05     -          
    simplex               1.00000  0.00019     0.00021    

    P value adjustment method: bonferroni 
:::

::: {#cb84 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
WILCOX_Wing
```
:::

::: {.cell-output .cell-output-stdout}
        Pairwise comparisons using Wilcoxon rank sum test with continuity correction 

    data:  ZosteropsMorph_groups$Wing and ZosteropsMorph_groups$Group 

                          erythropleurus everetti japonicus CONTINENTAL
    everetti              1.4e-05        -        -                    
    japonicus CONTINENTAL 0.19103        0.00022  -                    
    japonicus OCEANIC     0.16097        3.0e-10  1.6e-07              
    meyeni                0.00077        1.00000  0.10199              
    montanus NORTH        0.00023        1.00000  4.3e-05              
    montanus SOUTH        6.8e-06        1.00000  0.00161              
    nigrorum              1.1e-07        0.00034  7.8e-08              
    nigrorum CS           1.00000        0.00102  1.00000              
    palpebrosus           4.1e-06        0.00345  2.4e-07              
    simplex               1.4e-05        1.00000  5.0e-05              
                          japonicus OCEANIC meyeni  montanus NORTH montanus SOUTH
    everetti              -                 -       -              -             
    japonicus CONTINENTAL -                 -       -              -             
    japonicus OCEANIC     -                 -       -              -             
    meyeni                1.8e-08           -       -              -             
    montanus NORTH        2.2e-06           0.00970 -              -             
    montanus SOUTH        1.3e-12           1.00000 0.14655        -             
    nigrorum              7.7e-11           4.3e-05 1.00000        2.0e-06       
    nigrorum CS           0.00923           0.02530 0.00054        0.00395       
    palpebrosus           1.1e-08           3.0e-05 1.00000        9.3e-05       
    simplex               1.4e-09           0.62904 1.00000        1.00000       
                          nigrorum nigrorum CS palpebrosus
    everetti              -        -           -          
    japonicus CONTINENTAL -        -           -          
    japonicus OCEANIC     -        -           -          
    meyeni                -        -           -          
    montanus NORTH        -        -           -          
    montanus SOUTH        -        -           -          
    nigrorum              -        -           -          
    nigrorum CS           2.4e-05  -           -          
    palpebrosus           1.00000  5.4e-05     -          
    simplex               0.02096  0.00032     0.07309    

    P value adjustment method: bonferroni 
:::

::: {#cb86 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
WILCOX_Tail
```
:::

::: {.cell-output .cell-output-stdout}
        Pairwise comparisons using Wilcoxon rank sum test with continuity correction 

    data:  ZosteropsMorph_groups$Tail and ZosteropsMorph_groups$Group 

                          erythropleurus everetti japonicus CONTINENTAL
    everetti              1.0000         -        -                    
    japonicus CONTINENTAL 0.0085         0.0056   -                    
    japonicus OCEANIC     1.9e-06        1.3e-07  1.0000               
    meyeni                1.0000         1.0000   0.0386               
    montanus NORTH        0.0317         0.0078   5.6e-05              
    montanus SOUTH        0.3226         0.0046   2.2e-08              
    nigrorum              1.0000         0.4399   7.8e-05              
    nigrorum CS           1.0000         1.0000   1.0000               
    palpebrosus           1.0000         1.0000   0.0013               
    simplex               1.0000         1.0000   0.0121               
                          japonicus OCEANIC meyeni montanus NORTH montanus SOUTH
    everetti              -                 -      -              -             
    japonicus CONTINENTAL -                 -      -              -             
    japonicus OCEANIC     -                 -      -              -             
    meyeni                9.3e-06           -      -              -             
    montanus NORTH        2.5e-06           0.0061 -              -             
    montanus SOUTH        2.5e-13           0.0319 1.0000         -             
    nigrorum              3.3e-08           0.3902 1.0000         1.0000        
    nigrorum CS           0.0053            1.0000 0.0311         0.0847        
    palpebrosus           4.3e-07           1.0000 0.2727         1.0000        
    simplex               3.9e-06           1.0000 0.0617         0.1704        
                          nigrorum nigrorum CS palpebrosus
    everetti              -        -           -          
    japonicus CONTINENTAL -        -           -          
    japonicus OCEANIC     -        -           -          
    meyeni                -        -           -          
    montanus NORTH        -        -           -          
    montanus SOUTH        -        -           -          
    nigrorum              -        -           -          
    nigrorum CS           0.6331   -           -          
    palpebrosus           1.0000   1.0000      -          
    simplex               1.0000   1.0000      1.0000     

    P value adjustment method: bonferroni 
:::

::: {#cb88 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
# Function to convert test results to a table format
generate_WILCOX_table <- function(test_result) {
  p_values <- format(test_result$p.value, nsmall = 2, digits = 2)
  data.frame(p_values)
}
# Generate tables for each test result
WILCOX_table_BillCulmen <- generate_WILCOX_table(WILCOX_BillCulmen)
WILCOX_table_BillNareTip <- generate_WILCOX_table(WILCOX_BillNareTip)
WILCOX_table_BillDepth <- generate_WILCOX_table(WILCOX_BillDepth)
WILCOX_table_BillWidth <- generate_WILCOX_table(WILCOX_BillWidth)
WILCOX_table_Tarsus <- generate_WILCOX_table(WILCOX_Tarsus)
WILCOX_table_Wing <- generate_WILCOX_table(WILCOX_Wing)
WILCOX_table_Tail <- generate_WILCOX_table(WILCOX_Tail)

WILCOX_table_BillCulmen
```
:::

::: {.cell-output .cell-output-stdout}
                          erythropleurus everetti japonicus.CONTINENTAL
    everetti                     1.5e-03       NA                    NA
    japonicus CONTINENTAL        1.6e-06  1.3e-03                    NA
    japonicus OCEANIC            7.6e-09  3.6e-11               9.8e-06
    meyeni                       5.4e-07  3.2e-03               1.0e+00
    montanus NORTH               2.9e-03  1.0e+00               4.7e-01
    montanus SOUTH               2.8e-06  9.0e-01               2.8e-01
    nigrorum                     1.0e+00  2.5e-01               9.9e-06
    nigrorum CS                  3.3e-05  6.6e-04               1.0e+00
    palpebrosus                  1.0e+00  1.7e-03               9.3e-06
    simplex                      1.0e+00  2.5e-05               1.9e-07
                          japonicus.OCEANIC  meyeni montanus.NORTH montanus.SOUTH
    everetti                             NA      NA             NA             NA
    japonicus CONTINENTAL                NA      NA             NA             NA
    japonicus OCEANIC                    NA      NA             NA             NA
    meyeni                          6.7e-07      NA             NA             NA
    montanus NORTH                  1.3e-05 1.0e+00             NA             NA
    montanus SOUTH                  1.2e-12 1.0e+00        1.0e+00             NA
    nigrorum                        2.0e-10 6.9e-06        1.6e-01        1.2e-04
    nigrorum CS                     4.2e-04 1.0e+00        6.8e-02        2.5e-01
    palpebrosus                     2.5e-08 5.2e-05        1.0e-02        3.8e-06
    simplex                         1.4e-09 2.6e-07        3.5e-04        1.1e-08
                          nigrorum nigrorum.CS palpebrosus
    everetti                    NA          NA          NA
    japonicus CONTINENTAL       NA          NA          NA
    japonicus OCEANIC           NA          NA          NA
    meyeni                      NA          NA          NA
    montanus NORTH              NA          NA          NA
    montanus SOUTH              NA          NA          NA
    nigrorum                    NA          NA          NA
    nigrorum CS            9.4e-05          NA          NA
    palpebrosus            4.6e-01     3.1e-04          NA
    simplex                6.4e-01     2.7e-05     1.0e+00
:::

::: {#cb90 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
WILCOX_table_BillNareTip
```
:::

::: {.cell-output .cell-output-stdout}
                          erythropleurus everetti japonicus.CONTINENTAL
    everetti                     1.0e-06       NA                    NA
    japonicus CONTINENTAL        1.0e-06  1.0e+00                    NA
    japonicus OCEANIC            8.4e-09  3.9e-07               6.5e-05
    meyeni                       9.2e-07  1.0e+00               1.0e+00
    montanus NORTH               2.3e-02  1.0e+00               1.0e+00
    montanus SOUTH               4.5e-09  1.0e+00               1.0e+00
    nigrorum                     2.1e-03  1.0e+00               2.3e-01
    nigrorum CS                  3.3e-05  1.8e-02               4.3e-02
    palpebrosus                  1.0e+00  6.2e-05               5.2e-05
    simplex                      1.1e-01  2.7e-03               1.4e-04
                          japonicus.OCEANIC  meyeni montanus.NORTH montanus.SOUTH
    everetti                             NA      NA             NA             NA
    japonicus CONTINENTAL                NA      NA             NA             NA
    japonicus OCEANIC                    NA      NA             NA             NA
    meyeni                          4.9e-03      NA             NA             NA
    montanus NORTH                  2.9e-04 5.3e-01             NA             NA
    montanus SOUTH                  5.3e-08 1.0e+00        1.0e+00             NA
    nigrorum                        6.9e-08 1.8e-02        1.0e+00        9.9e-02
    nigrorum CS                     1.0e+00 1.0e+00        3.5e-02        3.8e-02
    palpebrosus                     6.6e-08 3.2e-05        1.1e-01        7.0e-07
    simplex                         2.6e-09 3.0e-05        1.0e+00        3.4e-05
                          nigrorum nigrorum.CS palpebrosus
    everetti                    NA          NA          NA
    japonicus CONTINENTAL       NA          NA          NA
    japonicus OCEANIC           NA          NA          NA
    meyeni                      NA          NA          NA
    montanus NORTH              NA          NA          NA
    montanus SOUTH              NA          NA          NA
    nigrorum                    NA          NA          NA
    nigrorum CS            9.1e-04          NA          NA
    palpebrosus            1.3e-02     1.4e-04          NA
    simplex                1.0e+00     1.9e-05     4.4e-01
:::

::: {#cb92 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
WILCOX_table_BillDepth
```
:::

::: {.cell-output .cell-output-stdout}
                          erythropleurus everetti japonicus.CONTINENTAL
    everetti                     5.3e-08       NA                    NA
    japonicus CONTINENTAL        3.0e-01  3.1e-06                    NA
    japonicus OCEANIC            1.5e-07  1.0e+00               2.3e-06
    meyeni                       4.0e-06  1.0e+00               1.0e-03
    montanus NORTH               1.0e+00  2.3e-04               1.0e+00
    montanus SOUTH               3.3e-06  4.4e-04               7.4e-02
    nigrorum                     2.6e-03  1.1e-02               1.0e+00
    nigrorum CS                  5.9e-05  4.1e-01               1.1e-04
    palpebrosus                  1.0e+00  5.2e-07               1.0e+00
    simplex                      1.0e+00  3.3e-10               2.4e-02
                          japonicus.OCEANIC  meyeni montanus.NORTH montanus.SOUTH
    everetti                             NA      NA             NA             NA
    japonicus CONTINENTAL                NA      NA             NA             NA
    japonicus OCEANIC                    NA      NA             NA             NA
    meyeni                          1.0e+00      NA             NA             NA
    montanus NORTH                  2.0e-04 3.3e-03             NA             NA
    montanus SOUTH                  1.9e-05 3.3e-01        1.0e-01             NA
    nigrorum                        1.0e-03 4.4e-01        1.0e+00        1.0e+00
    nigrorum CS                     1.0e+00 5.0e-01        1.3e-03        4.0e-04
    palpebrosus                     7.1e-07 3.5e-05        1.0e+00        7.5e-05
    simplex                         5.8e-09 1.0e-07        1.0e+00        7.9e-09
                          nigrorum nigrorum.CS palpebrosus
    everetti                    NA          NA          NA
    japonicus CONTINENTAL       NA          NA          NA
    japonicus OCEANIC           NA          NA          NA
    meyeni                      NA          NA          NA
    montanus NORTH              NA          NA          NA
    montanus SOUTH              NA          NA          NA
    nigrorum                    NA          NA          NA
    nigrorum CS            2.7e-03          NA          NA
    palpebrosus            1.6e-02     1.2e-04          NA
    simplex                4.5e-05     1.4e-05     1.0e+00
:::

::: {#cb94 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
WILCOX_table_BillWidth
```
:::

::: {.cell-output .cell-output-stdout}
                          erythropleurus everetti japonicus.CONTINENTAL
    everetti                     2.1e-08       NA                    NA
    japonicus CONTINENTAL        1.5e-01  8.1e-04                    NA
    japonicus OCEANIC            1.8e-07  1.0e+00               2.2e-04
    meyeni                       7.4e-07  2.4e-01               2.2e-05
    montanus NORTH               3.5e-01  1.0e+00               1.0e+00
    montanus SOUTH               7.9e-07  1.0e+00               3.8e-02
    nigrorum                     5.5e-01  8.4e-04               1.0e+00
    nigrorum CS                  5.1e-05  1.0e+00               8.5e-04
    palpebrosus                  1.0e+00  1.6e-08               1.6e-01
    simplex                      1.0e+00  6.3e-08               7.5e-01
                          japonicus.OCEANIC  meyeni montanus.NORTH montanus.SOUTH
    everetti                             NA      NA             NA             NA
    japonicus CONTINENTAL                NA      NA             NA             NA
    japonicus OCEANIC                    NA      NA             NA             NA
    meyeni                          1.0e+00      NA             NA             NA
    montanus NORTH                  8.3e-01 7.7e-02             NA             NA
    montanus SOUTH                  1.0e+00 4.8e-02        1.0e+00             NA
    nigrorum                        1.1e-03 1.2e-04        1.0e+00        1.9e-02
    nigrorum CS                     1.0e+00 1.0e+00        7.4e-01        1.0e+00
    palpebrosus                     4.0e-07 1.3e-06        1.0e+00        1.6e-06
    simplex                         2.9e-07 5.6e-07        1.0e+00        2.3e-06
                          nigrorum nigrorum.CS palpebrosus
    everetti                    NA          NA          NA
    japonicus CONTINENTAL       NA          NA          NA
    japonicus OCEANIC           NA          NA          NA
    meyeni                      NA          NA          NA
    montanus NORTH              NA          NA          NA
    montanus SOUTH              NA          NA          NA
    nigrorum                    NA          NA          NA
    nigrorum CS            1.1e-02          NA          NA
    palpebrosus            1.0e+00     4.6e-05          NA
    simplex                1.0e+00     6.5e-05     1.0e+00
:::

::: {#cb96 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
WILCOX_table_Tarsus
```
:::

::: {.cell-output .cell-output-stdout}
                          erythropleurus everetti japonicus.CONTINENTAL
    everetti                     7.1e-03       NA                    NA
    japonicus CONTINENTAL        1.2e-05  4.9e-02                    NA
    japonicus OCEANIC            1.3e-08  5.3e-10               3.7e-05
    meyeni                       4.1e-06  1.4e-03               1.0e+00
    montanus NORTH               4.4e-01  1.0e+00               2.3e-01
    montanus SOUTH               6.1e-06  1.0e+00               1.3e-01
    nigrorum                     1.4e-01  1.0e+00               8.9e-03
    nigrorum CS                  1.0e-04  3.3e-04               4.5e-01
    palpebrosus                  1.0e-02  6.0e-08               7.9e-08
    simplex                      1.0e+00  1.5e-01               4.5e-05
                          japonicus.OCEANIC  meyeni montanus.NORTH montanus.SOUTH
    everetti                             NA      NA             NA             NA
    japonicus CONTINENTAL                NA      NA             NA             NA
    japonicus OCEANIC                    NA      NA             NA             NA
    meyeni                          1.5e-04      NA             NA             NA
    montanus NORTH                  7.4e-06 1.3e-02             NA             NA
    montanus SOUTH                  6.8e-13 5.7e-04        1.0e+00             NA
    nigrorum                        2.3e-09 2.9e-04        1.0e+00        8.0e-01
    nigrorum CS                     4.3e-02 1.0e+00        1.8e-03        3.8e-05
    palpebrosus                     1.2e-08 1.7e-07        4.8e-04        4.1e-11
    simplex                         5.3e-09 1.1e-05        1.0e+00        3.0e-04
                          nigrorum nigrorum.CS palpebrosus
    everetti                    NA          NA          NA
    japonicus CONTINENTAL       NA          NA          NA
    japonicus OCEANIC           NA          NA          NA
    meyeni                      NA          NA          NA
    montanus NORTH              NA          NA          NA
    montanus SOUTH              NA          NA          NA
    nigrorum                    NA          NA          NA
    nigrorum CS            2.7e-04          NA          NA
    palpebrosus            3.3e-06     4.1e-05          NA
    simplex                1.0e+00     1.9e-04     2.1e-04
:::

::: {#cb98 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
WILCOX_table_Wing
```
:::

::: {.cell-output .cell-output-stdout}
                          erythropleurus everetti japonicus.CONTINENTAL
    everetti                     1.4e-05       NA                    NA
    japonicus CONTINENTAL        1.9e-01  2.2e-04                    NA
    japonicus OCEANIC            1.6e-01  3.0e-10               1.6e-07
    meyeni                       7.7e-04  1.0e+00               1.0e-01
    montanus NORTH               2.3e-04  1.0e+00               4.3e-05
    montanus SOUTH               6.8e-06  1.0e+00               1.6e-03
    nigrorum                     1.1e-07  3.4e-04               7.8e-08
    nigrorum CS                  1.0e+00  1.0e-03               1.0e+00
    palpebrosus                  4.1e-06  3.4e-03               2.4e-07
    simplex                      1.4e-05  1.0e+00               5.0e-05
                          japonicus.OCEANIC  meyeni montanus.NORTH montanus.SOUTH
    everetti                             NA      NA             NA             NA
    japonicus CONTINENTAL                NA      NA             NA             NA
    japonicus OCEANIC                    NA      NA             NA             NA
    meyeni                          1.8e-08      NA             NA             NA
    montanus NORTH                  2.2e-06 9.7e-03             NA             NA
    montanus SOUTH                  1.3e-12 1.0e+00        1.5e-01             NA
    nigrorum                        7.7e-11 4.3e-05        1.0e+00        2.0e-06
    nigrorum CS                     9.2e-03 2.5e-02        5.4e-04        4.0e-03
    palpebrosus                     1.1e-08 3.0e-05        1.0e+00        9.3e-05
    simplex                         1.4e-09 6.3e-01        1.0e+00        1.0e+00
                          nigrorum nigrorum.CS palpebrosus
    everetti                    NA          NA          NA
    japonicus CONTINENTAL       NA          NA          NA
    japonicus OCEANIC           NA          NA          NA
    meyeni                      NA          NA          NA
    montanus NORTH              NA          NA          NA
    montanus SOUTH              NA          NA          NA
    nigrorum                    NA          NA          NA
    nigrorum CS            2.4e-05          NA          NA
    palpebrosus            1.0e+00     5.4e-05          NA
    simplex                2.1e-02     3.2e-04     7.3e-02
:::

::: {#cb100 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
WILCOX_table_Tail
```
:::

::: {.cell-output .cell-output-stdout}
                          erythropleurus everetti japonicus.CONTINENTAL
    everetti                     1.0e+00       NA                    NA
    japonicus CONTINENTAL        8.5e-03  5.6e-03                    NA
    japonicus OCEANIC            1.9e-06  1.3e-07               1.0e+00
    meyeni                       1.0e+00  1.0e+00               3.9e-02
    montanus NORTH               3.2e-02  7.8e-03               5.6e-05
    montanus SOUTH               3.2e-01  4.6e-03               2.2e-08
    nigrorum                     1.0e+00  4.4e-01               7.8e-05
    nigrorum CS                  1.0e+00  1.0e+00               1.0e+00
    palpebrosus                  1.0e+00  1.0e+00               1.3e-03
    simplex                      1.0e+00  1.0e+00               1.2e-02
                          japonicus.OCEANIC  meyeni montanus.NORTH montanus.SOUTH
    everetti                             NA      NA             NA             NA
    japonicus CONTINENTAL                NA      NA             NA             NA
    japonicus OCEANIC                    NA      NA             NA             NA
    meyeni                          9.3e-06      NA             NA             NA
    montanus NORTH                  2.5e-06 6.1e-03             NA             NA
    montanus SOUTH                  2.5e-13 3.2e-02        1.0e+00             NA
    nigrorum                        3.3e-08 3.9e-01        1.0e+00        1.0e+00
    nigrorum CS                     5.3e-03 1.0e+00        3.1e-02        8.5e-02
    palpebrosus                     4.3e-07 1.0e+00        2.7e-01        1.0e+00
    simplex                         3.9e-06 1.0e+00        6.2e-02        1.7e-01
                          nigrorum nigrorum.CS palpebrosus
    everetti                    NA          NA          NA
    japonicus CONTINENTAL       NA          NA          NA
    japonicus OCEANIC           NA          NA          NA
    meyeni                      NA          NA          NA
    montanus NORTH              NA          NA          NA
    montanus SOUTH              NA          NA          NA
    nigrorum                    NA          NA          NA
    nigrorum CS            6.3e-01          NA          NA
    palpebrosus            1.0e+00     1.0e+00          NA
    simplex                1.0e+00     1.0e+00     1.0e+00
:::
:::
:::
:::

::: {#close-log .section .level2}
## Close log {#close-log .anchored anchor-id="close-log"}

End the log.

::: {.cell}
::: {#cb102 .sourceCode .cell-code}
``` {.sourceCode .r .code-with-copy}
log_close()
```
:::
:::
:::

::: {#quarto-appendix .default}
::: {#quarto-bibliography .section .quarto-appendix-contents role="doc-bibliography"}
## References {#references .anchored .quarto-appendix-heading}

::: {#refs .references .csl-bib-body .hanging-indent entry-spacing="0" role="list"}
::: {#ref-gridExtra .csl-entry role="listitem"}
Auguie, Baptiste. 2017. "gridExtra: Miscellaneous Functions for \"Grid\"
Graphics." <https://CRAN.R-project.org/package=gridExtra>.
:::

::: {#ref-logr .csl-entry role="listitem"}
Bosak, David. 2024. "Logr: Creates Log Files."
<https://CRAN.R-project.org/package=logr>.
:::

::: {#ref-gt .csl-entry role="listitem"}
Iannone, Richard, Joe Cheng, Barret Schloerke, Ellis Hughes, Alexandra
Lauer, JooYoung Seo, Ken Brevoort, and Olivier Roy. 2024. "Gt: Easily
Create Presentation-Ready Display Tables."
<https://CRAN.R-project.org/package=gt>.
:::

::: {#ref-factoextra .csl-entry role="listitem"}
Kassambara, Alboukadel, and Fabian Mundt. 2020. "Factoextra: Extract and
Visualize the Results of Multivariate Data Analyses."
<https://CRAN.R-project.org/package=factoextra>.
:::

::: {#ref-broom .csl-entry role="listitem"}
Robinson, David, Alex Hayes, and Simon Couch. 2024. "Broom: Convert
Statistical Objects into Tidy Tibbles."
<https://CRAN.R-project.org/package=broom>.
:::

::: {#ref-plotly .csl-entry role="listitem"}
Sievert, Carson. 2020. "Interactive Web-Based Data Visualization with r,
Plotly, and Shiny." <https://plotly-r.com>.
:::

::: {#ref-htmlwidgets .csl-entry role="listitem"}
Vaidyanathan, Ramnath, Yihui Xie, JJ Allaire, Joe Cheng, Carson Sievert,
and Kenton Russell. 2023. "Htmlwidgets: HTML Widgets for r."
<https://CRAN.R-project.org/package=htmlwidgets>.
:::

::: {#ref-ggplot2 .csl-entry role="listitem"}
Wickham, Hadley. 2016. "Ggplot2: Elegant Graphics for Data Analysis."
<https://ggplot2.tidyverse.org>.
:::

::: {#ref-dplyr .csl-entry role="listitem"}
Wickham, Hadley, Romain François, Lionel Henry, Kirill Müller, and Davis
Vaughan. 2023. "Dplyr: A Grammar of Data Manipulation."
<https://CRAN.R-project.org/package=dplyr>.
:::

::: {#ref-readr .csl-entry role="listitem"}
Wickham, Hadley, Jim Hester, and Jennifer Bryan. 2024. "Readr: Read
Rectangular Text Data." <https://CRAN.R-project.org/package=readr>.
:::

::: {#ref-tidyr .csl-entry role="listitem"}
Wickham, Hadley, Davis Vaughan, and Maximilian Girlich. 2024. "Tidyr:
Tidy Messy Data." <https://CRAN.R-project.org/package=tidyr>.
:::
:::
:::
:::
:::
:::

# AXL-RB1-Sequence-Variation-Clustering
A bioinformatics pipeline in R for comparative analysis of AXL and RB1 gene sequences, featuring quality control, hierarchical clustering, and dimensionality reduction to investigate how functional diversity is reflected in genetic variation.

![R](https://img.shields.io/badge/R-%276ABC.svg?style=for-the-badge&logo=R&logoColor=white)
![BioConductor](https://img.shields.io/badge/Bioconductor-%23C3BBA4.svg?style=for-the-badge)
![Markdown](https://img.shields.io/badge/Markdown-%23000000.svg?style=for-the-badge&logo=markdown&logoColor=white)

## 📖 Overview

This project implements a complete R-based workflow for acquiring, processing, and analyzing mRNA and CDS sequences for the AXL and RB1 genes from NCBI. The AXL gene is associated with cancer metastasis and immune response, while RB1 is a critical tumor suppressor. The analysis tests the hypothesis that these distinct functional roles are reflected in their patterns of sequence conservation and variability.

Key steps include:
*   **Data Acquisition & Exploration:** Retrieval of sequences from NCBI and initial characterization of length, GC content, and composition.
*   **Quality Control:** Filtering sequences based on type (mRNA/CDS), length, GC content, and ambiguity (N-content).
*   **Clustering Analysis:** Hierarchical clustering of sequences using multiple linkage methods, validated with silhouette scores, Dunn, and Davies-Bouldin indices.
*   **Dimensionality Reduction:** Principal Component Analysis (PCA) to visualize sequence clusters.
*   **Comparative Genomics:** A detailed comparison of clustering results between AXL and RB1 to draw biological insights.

## 🧬 Key Findings

The analysis revealed a stark contrast between the two genes:
*   **AXL** exhibited high sequence variability, forming **304 clusters** with a lower average silhouette width (**0.216**), suggesting greater genetic diversity which may underpin its role in adaptable processes like metastasis.
*   **RB1** showed strong sequence conservation, forming only **69 clusters** with a high average silhouette width (**0.659**), indicating evolutionary constraint consistent with its essential, non-redundant tumor suppressor function.


## 🛠️ Installation & Usage

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/AXL-RB1-Sequence-Variation-Clustering.git
    cd AXL-RB1-Sequence-Variation-Clustering
    ```

2.  **Install Required R Packages:**
    The main script (`GeneAnslysis.Rmd`) will check for and attempt to install all required packages (Biostrings, DECIPHER, ggplot2, etc.). You can also install them manually:
    ```r
    # Install from CRAN and Bioconductor
    if (!require("BiocManager", quietly = TRUE))
        install.packages("BiocManager")
    
    BiocManager::install(c("Biostrings", "DECIPHER"))
    install.packages(c("ggplot2", "vegan", "cluster", "clValid", "viridis", "patchwork"))
    ```

3.  **Run the Analysis:**
    *   Place your FASTA files in the `data/` directory.
    *   Open `scripts/GeneAnslysis.Rmd` in RStudio.
    *   Ensure the file paths in the "Data Loading" section point to your files (e.g., `"./data/AXL_human_mRNA_CDS_sequences.fasta"`).
    *   Knit the Rmd file to execute the entire pipeline and generate the report and all figures.

## 📊 Results

The final report (`GeneAnalysis.pdf`) includes all figures and a full discussion. Key outputs are also saved as PNG images in the `output/` folder.



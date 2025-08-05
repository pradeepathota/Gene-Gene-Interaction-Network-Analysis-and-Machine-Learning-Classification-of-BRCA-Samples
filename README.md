# Gene-Gene Interaction Network-Based Classification of Breast Cancer Samples

This project integrates transcriptomic data and network-based feature engineering to classify breast cancer (BRCA) tumor vs. normal samples using machine learning. It uses TCGA gene expression data, constructs a Pearson correlation-based gene-gene interaction (GGI) network, extracts centrality features, and trains a Random Forest classifier.

---

## Project Highlights

- **Dataset**: TCGA BRCA gene expression & clinical data
- **ML Task**: Classify tumor vs. normal samples
- **Feature Engineering**: 
  - Low-variance gene filtering
  - Gene-Gene Interaction (GGI) network
  - Degree and betweenness centrality
- **Model**: Random Forest
- **Metrics**: Accuracy, ROC AUC, classification report
- **Visualization**: GGI network (top 50 genes by centrality)

---
## Step-by-Step Workflow

1. **Data Loading**  
   Load expression and phenotype data from TCGA.

2. **Label Assignment**  
   Assign binary labels based on sample suffix (-01 = Tumor, -11 = Normal).

3. **Expression Filtering**  
   Remove low-variance genes using `VarianceThreshold`.

4. **Gene-Gene Interaction Network**  
   Build Pearson correlation network and retain gene pairs with |r| ≥ 0.7.

5. **Network Feature Extraction**  
   Calculate `degree_centrality` and `betweenness_centrality` using NetworkX.

6. **Feature Matrix Creation**  
   Combine expression with centrality-weighted features.

7. **Random Forest Classification**  
   Train/test split, model training, prediction, and evaluation.

8. **Top Feature Visualization**  
   Bar plot of top 20 genes by importance.

9. **GGI Network Plotting**  
   Visualize the GGI subgraph for the top 50 central genes.

---

## Run in Google Colab

> This project is fully runnable in **Google Colab**. Just upload the required files and follow the step-by-step cells in the notebook.

---

## Results

- **Model**: Random Forest  
- **Evaluation**: Classification report + ROC AUC  
- **Top Genes**: Automatically extracted and visualized

---

## Project Use Case

This project demonstrates how biological networks can enhance predictive models in cancer genomics by uncovering biologically relevant features beyond raw expression levels.

---

## References

- The Cancer Genome Atlas (TCGA): https://portal.gdc.cancer.gov/
- NetworkX: https://networkx.org
- scikit-learn: https://scikit-learn.org/

---

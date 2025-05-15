# Apriori vs Word2Vec: Comparative Analysis of Product Recommendation Systems

This repository contains a comparative analysis of traditional association rule mining (Apriori algorithm) with neural embedding techniques (Word2Vec) for product recommendation systems in retail environments.

## Overview

The project analyzes transaction data to generate product recommendations using two distinct approaches:

1. **Apriori Algorithm**: A classic market basket analysis technique that identifies frequent itemsets and generates association rules to discover relationships between products purchased together.

2. **Word2Vec**: A neural network-based approach that represents products as vector embeddings, capturing semantic relationships between products based on their co-occurrence in transactions.

The goal is to quantitatively and qualitatively evaluate the differences in recommendation quality, performance, and practical applications of both techniques.

## Dataset

The analysis uses retail transaction data containing:
- Transaction IDs (BillNo)
- Product names (Itemname)
- Categories
- Dates
- Quantities
- Customer IDs

The dataset is analyzed for key characteristics including unique products, transaction sizes, purchase patterns, and category distributions to provide context for the recommendation system evaluation.

## Repository Structure

```
.
├── Dataset/                              # Data files and processed outputs
│   ├── Assignment-1_Data.xlsx            # Raw transaction data
│   ├── df_merged_items_category.xlsx     # Main dataset with product categories
│   ├── distinct_products_with_categories.xlsx  # Unique products listing
│   └── Analysis_plots/                   # Visualization outputs
├── Models/                               # Implementation of algorithms
│   └── Models_Evaluator.ipynb            # Evaluation framework for comparing models
├── Dataset-Analysis.ipynb                # Data exploration and preprocessing
├── Apriori.ipynb                         # Implementation of Apriori algorithm
├── Words2vec.ipynb                       # Implementation of Word2Vec approach
└── README.md
```

## Requirements

- Python 3.8+
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- mlxtend (for Apriori implementation)
- gensim (for Word2Vec implementation)
- Jupyter Notebook

Install required packages:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn mlxtend gensim jupyter
```

## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/Mohammed87FS/Apriori_VS_Word2Vec.git
   cd Apriori_VS_Word2Vec
   ```

2. Run the Jupyter notebooks in sequence:
   ```bash
   jupyter notebook
   ```
   
   - First, run Dataset-Analysis.ipynb to understand the data
   - Then, explore the implementations in `Apriori.ipynb` and `Words2vec.ipynb`
   - Finally, check comparative analysis in Models_Evaluator.ipynb

## Methodology

The project follows these key steps:

1. **Data Preprocessing**:
   - Cleaning transaction data
   - Organizing products into categories
   - Splitting data for evaluation 

2. **Apriori Implementation**:
   - Convert transactions to appropriate format
   - Generate frequent itemsets with various support thresholds
   - Create association rules with confidence thresholds
   - Measure performance and memory usage

3. **Word2Vec Implementation**:
   - Format transactions as "sentences" of products
   - Train product embeddings
   - Generate similar product recommendations
   - Measure performance metrics

4. **Evaluation Metrics**:
   - Coverage (percentage of products that can receive recommendations)
   - Diversity of recommendations
   - Execution time
   - Memory efficiency
   - Scalability with dataset size

## Results

The comparative analysis reveals strengths and weaknesses of each approach:

- **Apriori**: Provides highly interpretable rules but struggles with scalability and sparse datasets
- **Word2Vec**: Offers better coverage and handles sparse data well, but with less interpretable recommendations

Detailed performance metrics and visualizations can be found in the evaluation notebook.

## License

This project is available under the MIT License.
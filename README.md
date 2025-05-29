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

### Product Categorization

Products are organized into a hierarchical category structure:

#### Main Categories:
- Home & Living
- Personal Items
- Entertainment & Hobbies
- Seasonal & Gifts
- Office & Craft

Each main category is further divided into subcategories. For example:
- **Home & Living**: Home Decor, Lighting, Kitchen & Dining, Textiles & Cozy Items, etc.
- **Personal Items**: Fashion & Accessories, Electronics & Gadgets
- **Entertainment & Hobbies**: Kids & Toys, Books & Magazines, Games & Puzzles, etc.

Products were classified through both automated methods and manual review for accuracy.

## Repository Structure

```
.
├── Dataset/                              # Data files and processed outputs
│   ├── Assignment-1_Data.xlsx            # Raw transaction data
│   ├── full_validated_dataset.xlsx       # Main dataset with product categories
│   ├── distinct_products_with_categories.xlsx  # Unique products listing
│   └── Analysis_plots/                   # Visualization outputs
├── Models/                               # Implementation of algorithms
│   └── Models_Evaluator.ipynb            # Evaluation framework for comparing models
├── Finding_Categories/                   # Documentation of categorization methodology
│   └── README.md                         # Detailed explanation of category structure
├── Dataset-Analysis.ipynb                # Data exploration and preprocessing
├── Apriori.ipynb                         # Implementation of Apriori algorithm
├── Words2vec.ipynb                       # Implementation of Word2Vec approach
└── README.md                             # Project overview and instructions
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
   
   - First, run `Dataset-Analysis.ipynb` to understand the data
   - Then, explore the implementations in `Apriori.ipynb` and `Words2vec.ipynb`
   - Finally, check comparative analysis in `Models_Evaluator.ipynb`

## Methodology

The project follows these key steps:

1. **Data Preprocessing**:
   - Cleaning transaction data (handling missing values, duplicates)
   - Organizing products into the hierarchical category structure
   - Splitting data into training and evaluation sets

2. **Apriori Implementation**:
   - Convert transactions to appropriate basket format
   - Generate frequent itemsets with various support thresholds (0.001-0.01)
   - Create association rules with confidence thresholds (0.1-0.5) 
   - Measure performance and memory usage across different parameter settings

3. **Word2Vec Implementation**:
   - Format transactions as "sentences" of products for training
   - Train product embeddings using Skip-gram architecture
   - Generate similar product recommendations based on vector similarity
   - Experiment with different window sizes and dimensionality

4. **Evaluation Metrics**:
   - Coverage (percentage of products that can receive recommendations)
   - Execution time for model training and recommendation generation
   - Memory efficiency during training and storage
   - Scalability with increasing dataset size
   - Relevance of recommendations (within-category vs cross-category)

## Results

The comparative analysis reveals distinct strengths and weaknesses of each approach:

- **Apriori**:
  - Provides highly interpretable rules with clear confidence metrics
  - Excellent for identifying direct product relationships
  - Struggles with scalability on large product catalogs
  - Poor performance with sparse transaction data
  - Memory usage grows exponentially with lower support thresholds

- **Word2Vec**:
  - Offers superior recommendation coverage across the product catalog
  - Handles sparse transaction data effectively
  - Discovers non-obvious product relationships
  - Scales better with increasing dataset size
  - Less interpretable recommendations requiring additional validation

Detailed performance metrics, visualizations, and recommendation examples can be found in the evaluation notebook.

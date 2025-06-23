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

Products were classified through both automated methods and manual review for accuracy (There are more details regarding this in the thesis "3.1.1 Dataset Overview" section)

## Repository Structure

```
├── Dataset/
│   ├── Analysis_plots/
│   ├── Kaggle_Dataset_Pre_Processing/                    # The original Kaggle Dataset without preprocessing
│   ├── distinct_products_with_categories.xlsx            # Unique products category mapping
│   ├── full_validated_dataset.xlsx                       # Final dataset that is validated and sent to the algorithms
│   ├── not_validated_dataset_with_category.xlsx          # Contains the full dataset with category mapping for each product coming from the assignment of gpt 3.5 turbo
│   ├── Original_Dataset.xlsx
│   ├── unique_items.xlsx                                 # Unique products
│   └── validated_distinct_products_with_categories.xlsx  # Manually validated category mapping dataset (row by row manual vaildation)
│
├── Models/
│   ├── Models_Evaluator.ipynb                            # Complete evaluation code
│   └── Models_Parameters_Grid_Search.ipynb               # Parameter optimization code
│
├── Results/                                              # Generated analysis outputs
│   ├── whole_dataset/                                    # Full dataset results
│   ├── first_third/                                      # analysis (first 1/3)
│   └── last_two_thirds/                                  # analysis (last 2/3)
│
│
├── Finding_Categories/                                   # Categorization methodology
│   ├── high_level_categories.xlsx
│   ├── low_level_openai_category_products_mapping.ipynb
│   └── *.ipynb                                           # Category assignment notebooks
├── Dataset-Analysis.ipynb                                # Full data explorationn for the third thesis captial

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
   - Then, explore the implementations in `Models_Evaluator.ipynb`
   - Finally, check comparative analysis in `Models_Evaluator.ipynb`

## Methodology

The project follows these key steps:

1. **Data Preprocessing**:

   - Cleaning transaction data (handling missing values, duplicates)
   - Organizing products into the hierarchical category structure
   - Splitting data into training and evaluation sets

2. **Parameter Optimization:**
   Both algorithms use grid-search optimized parameters to find the configuration where both models have the highst agreement percentage regarding their recommendations to have a better comparasion foundation.

   **Apriori Configuration:**

   - Minimum Support: 0.01 (1% of transactions)
   - Minimum Confidence: 0.1 (10% confidence threshold)

   **Word2Vec Configuration:**

   - Vector Size: 50 dimensions
   - Window Size: 10 (context window)
   - Training Epochs: 10
   - Min Count: 20 (minimum word frequency)
   - Similarity Threshold: 0.5 for recommendations
   - Architecture: Skip-gram model

3. **Apriori Implementation**:

   - Converts transactions to appropriate basket format
   - Measure performance and memory usage across different dataset partions

4. **Word2Vec Implementation**:

   - Formats transactions as "sentences" of products for training
   - Trains product embeddings using Skip-gram architecture
   - Generates similar product recommendations based on vector similarity

5. **Evaluation Metrics**:
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
  - High memory usage grows

- **Word2Vec**:
  - Offers superior recommendation coverage across the product catalog
  - Discovers more product relationships
  - Scales better with increasing dataset size
  - Less interpretable recommendations requiring additional validation

Detailed performance metrics, visualizations, and recommendation examples can be found in the evaluation notebook.

### Contact

- **Author**: Mohammed Alhamadani
- **Email**: mohammedamaar165@gmail.com
- **LinkedIn**: https://www.linkedin.com/in/mohammed-ammar-burhan-al-hamadani-a88518302/
- **Institution**: FH St.Pölten

## Acknowledgments

- Thanks to my supervsior FH-Prof. Dipl.-Ing. Dr. Markus Seidl, Bakk. for his guidance and support

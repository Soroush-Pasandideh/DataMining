# Data Mining Project
## Overview

This repository contains the implementation of a Data Mining project. The project is structured into multiple Parts across two phases, each focusing on different aspects of data preprocessing, quality assessment, analysis, and advanced data mining techniques. The main tasks performed in this project include:

1. **Dataset Understanding**: Analyzing the features of the dataset and computing essential statistics such as mean, median, mode, min, max, and identifying outliers.
2. **Data Quality Assessment**: Evaluating the quality of the dataset based on various dimensions such as consistency, currentness, validity, completeness, and accuracy.
3. **Data Preprocessing**: Handling missing values, converting and normalizing data, engineering new features, removing outliers, and reducing data.
4. **Dataset Integration**: Combining the primary dataset with an additional dataset to enhance the scope of analysis and gain deeper insights.
5. **Frequent Pattern Extraction**: Identifying frequent itemsets and association rules within the dataset.
6. **Clustering and Classification**: Applying clustering algorithms to group data and classification algorithms to predict outcomes.

## Datasets

### Primary Dataset

The primary dataset (`source_Playstore_final.csv` - 450,794 records) contains detailed information about various apps available on the Google Play Store. This includes attributes such as app name, category, rating, installation statistics, pricing, developer information, and update history. This comprehensive dataset provides a rich source of data for performing various data mining tasks.

### Additional Dataset

The additional dataset (`GooglePlay.csv` - 10,840 records) includes similar information about apps but in a slightly different format. It covers aspects such as app ratings, reviews, size, installation numbers, content rating, genres, and version details. This dataset complements the primary dataset and is used for integration and enhanced analysis.

### Result Dataset

The preprocessing and integration processes have been applied to the two original datasets, resulting in a new dataset (`combined_df.csv`).

## **Structure of the Project**

### ***Phase 1***

#### ***Part 1:*** Dataset Understanding

1. **Feature Analysis**: For numerical data, the following statistics are computed:
   - Mean
   - Median
   - Mode
   - Min
   - Max
   - Outliers (using Box Plot)
2. **Outlier Detection**: Identifying and handling outliers by plotting box plots for each feature.

#### ***Part 2:*** Data Quality Assessment

1. **Quality Evaluation**: Assessing the dataset quality based on the ISO 25012 data quality model, focusing on:
   - Consistency
   - Currentness
   - Validity
   - Completeness
   - Accuracy
2. **Error Identification**: Identifying missing values, inconsistencies, and other errors within the dataset and suggesting ways to handle them.

#### ***Part 3:*** Data Preprocessing

1. **Handling Missing Values**: Using methods such as mean, median, mode, or regression to fill in missing values. Columns with excessive missing data may be removed.
2. **Data Conversion**: Normalizing and converting data as needed.
3. **Feature Engineering**: Creating new features by combining existing ones to enhance the dataset.
4. **Outlier Handling**: Removing outliers from numerical data.
5. **Data Reduction**: Applying techniques for data reduction if necessary.
6. **Categorical Data Handling**: Converting numerical data to categorical data where appropriate.
7. **Text Data Processing**: Performing operations like stemming, lemmatization, and removal of stopwords for text data.

#### ***Part 4:*** Dataset Integration

1. **Combining Datasets**: Integrating the current dataset with another larger dataset to enhance analysis.
2. **Column Matching and Merging**: Ensuring compatibility of columns between the datasets and handling any discrepancies.
3. **Creating New Insights**: Adding new columns by combining data from both datasets for deeper analysis.

### ***Phase 2***

#### ***Part 1:*** Extracting Frequent Patterns

1. **Frequent Itemset Mining**: Identifying frequent itemsets using techniques such as the Apriori algorithm and FP-Growth.
2. **Association Rule Mining**: Deriving association rules from the frequent itemsets to uncover hidden patterns and relationships within the data.

#### ***Part 2:*** Clustering and Classification

1. **Clustering**: Applying clustering algorithms such as K-Means, K-Medians, and hierarchical clustering to group the data into meaningful clusters.
   - Visualizing cluster patterns using various plotting techniques.
2. **Classification**: Building classification models using algorithms such as Naive Bayes, Decision Tree, Random Forest, and SVM to predict outcomes.
   - Feature Selection: Identifying relevant features for classification.
   - Model Evaluation: Testing different models to determine the best performing one based on the dataset.

## Requirements

- **Python**: Ensure you have Python installed (preferably Python 3.8 or higher).
- **Jupyter Notebook**: For running the `.ipynb` file.
- **Libraries**: Install the necessary Python libraries using the command below:
  ```sh
  pip install -r requirements.txt
  ```

## Usage

1. Clone the repository:
   ```sh
   git clone https://github.com/Soroush-Pasandideh/DataMining.git
   ```
2. Navigate to the project directory:
   ```sh
   cd DataMining
   ```
3. Open the Jupyter Notebook:
   ```sh
   jupyter notebook DataMining.ipynb
   ```
4. Run the cells in the notebook sequentially to perform the data mining tasks as outlined.

## Results

The notebook contains detailed results of each Part, including visualizations, statistical analyses, and data preprocessing steps. Ensure to go through the notebook for insights and understanding of the dataset.
the documentation of the implementation of final Phase is available in `DataMining_Document_phase2.pdf`.

# Data Mining Project

## Table of Contents

1. [Overview](#overview)
2. [Datasets](#datasets)
   - [Primary Dataset](#primary-dataset)
   - [Additional Dataset](#additional-dataset)
   - [Result Dataset](#result-dataset)
3. [Structure of the Project](#structure-of-the-project)
   - [Phase 1](#phase-1)
     - [Part 1: Dataset Understanding](#part-1-dataset-understanding)
     - [Part 2: Data Quality Assessment](#part-2-data-quality-assessment)
     - [Part 3: Data Preprocessing](#part-3-data-preprocessing)
     - [Part 4: Dataset Integration](#part-4-dataset-integration)
   - [Phase 2](#phase-2)
     - [Part 1: Extracting Frequent Patterns](#part-1-extracting-frequent-patterns)
     - [Part 2: Clustering and Classification](#part-2-clustering-and-classification)
4. [Requirements](#requirements)
5. [Usage](#usage)
6. [Results](#results)


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

- phase1:
  - DataPreProcessing.ipynb
- phase2: 
  - part1:
    - FrequentPatternExtraction.ipynb
  - part2:
    - Clustering.ipynb
    - Classification.ipynb

### **Phase 1**

#### Part 1: Dataset Understanding

  1. **Feature Analysis**: For numerical data, the following statistics are computed:
     - Mean
     - Median
     - Mode
     - Min
     - Max
     - Outliers (using Box Plot)
  2. **Outlier Detection**: Identifying and handling outliers by plotting box plots for each feature.

#### Part 2: Data Quality Assessment

1. **Quality Evaluation**: Assessing the dataset quality based on the ISO 25012 data quality model, focusing on:
   - Consistency
   - Currentness
   - Validity
   - Completeness
   - Accuracy
2. **Error Identification**: Identifying missing values, inconsistencies, and other errors within the dataset and suggesting ways to handle them.

#### Part 3: Data Preprocessing

1. **Handling Missing Values**: Using methods such as mean, median, mode, or regression to fill in missing values. Columns with excessive missing data may be removed.
2. **Data Conversion**: Normalizing and converting data as needed.
3. **Feature Engineering**: Creating new features by combining existing ones to enhance the dataset.
4. **Outlier Handling**: Removing outliers from numerical data.
5. **Data Reduction**: Applying techniques for data reduction if necessary.
6. **Categorical Data Handling**: Converting numerical data to categorical data where appropriate.
7. **Text Data Processing**: Performing operations like stemming, lemmatization, and removal of stopwords for text data.

#### Part 4: Dataset Integration

1. **Combining Datasets**: Integrating the current dataset with another larger dataset to enhance analysis.
2. **Column Matching and Merging**: Ensuring compatibility of columns between the datasets and handling any discrepancies.
3. **Creating New Insights**: Adding new columns by combining data from both datasets for deeper analysis.

### **Phase 2**

#### Part 1: Extracting Frequent Patterns

1. **Dataset Preparation**: 
   - Using the cleaned dataset of previous phase, combined from Google Play and Play Store, joined on the "App Name" column.

2. **Data Preprocessing**: 
   - Applying binning techniques to convert numerical columns to categorical.
   - Converting categorical data to appropriate formats for analysis.

3. **Frequent Itemset Mining**: 
   - Utilizing the Apriori algorithm from the mlxtend library.
     
     <img src="./phase2_tables/freq_itemsets.png" width="80%" height="80%">
     
   - Identifying maximal itemsets from the frequent itemsets.

     <img src="./phase2_tables/maximal_itemset.png" width="80%" height="80%">

4. **Association Rule Mining**: 
   - Extracting association rules from maximal itemsets with a confidence threshold of 0.7.
   - Analyzing the rules to uncover hidden patterns and relationships within the data.
  
     <img src="./phase2_tables/association_rules.png" width="80%" height="80%">

#### Part 2: Clustering and Classification

1. **Clustering**: 
   - Implementing two unsupervised learning algorithms: K-means and DBSCAN.
   
   - **Data Preparation**:
     - Selecting relevant numerical columns (Rating, Rating Count, Reviews, Size, Installs, Price, Revenue, popularity).
     - Applying dynamic binning using the Freedman-Diaconis rule and static binning for comparison.
   
   - **K-means Implementation**:
     - Determining optimal K using the elbow method (testing K from 1 to 12).
    
       <img src="./phase2_tables/elbow_method.png" width="50%" height="50%">

     - Visualizing clusters in 2D and 3D plots.
    
       <img src="./phase2_tables/kmeans_2D.png" width="50%" height="50%">
       
       <img src="./phase2_tables/kmeans_3D.png" width="50%" height="50%">
   
   - **DBSCAN Implementation**:
     - Applying DBSCAN algorithm to the preprocessed data.
     - Visualizing DBSCAN clusters in 2D and 3D plots.
    
       <img src="./phase2_tables/dbscan_2D.png" width="50%" height="50%">
       
       <img src="./phase2_tables/dbscan_3D.png" width="50%" height="50%">

   - **Pattern Analysis**:
     - Extracting frequent itemsets and association rules for each cluster to identify cluster-specific patterns.

2. **Classification**: 
   - Objective: Predicting app ratings based on other features.
   
   - **Feature Selection**:
     - Using correlation matrix to identify relevant features for rating prediction.
    
       <img src="./phase2_tables/correlation.png" width="90%" height="90%">
   
   - **Data Preprocessing**:
     - Converting 'normal_rating' to ordinal categorical type.
     - Splitting data into training and test sets.
     - Scaling features for standardization.
   
   - **Model Implementation**:
     - Implementing three classification models: Decision Tree, Random Forest, and Naive Bayes.
     - Performing hyperparameter tuning using Grid Search for each model.

       <img src="./phase2_tables/hyperparameter_tuning.png" width="50%" height="50%">
   
   - **Model Evaluation**:
     - Using metrics such as Accuracy, Precision, Recall, and F1 Score.
     - Generating confusion matrices for each model.
       
       <img src="./phase2_tables/eval_DT.png" width="50%" height="50%">
       <img src="./phase2_tables/eval_RF.png" width="50%" height="50%">
       <img src="./phase2_tables/eval_NB.png" width="50%" height="50%">
   
   - **Results**:
     - Random Forest performed best among the three models.
     - Naive Bayes showed the lowest performance for this classification task.

The enhanced clustering and classification techniques provide deeper insights into app characteristics and their relationship with ratings, offering valuable information for app developers and marketers in the Google Play Store ecosystem.
## Requirements

- **Python**: Ensure you have Python installed (preferably Python 3.8 or higher).
- **Jupyter Notebook**: For running the `.ipynb` files.
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
   open the notebook related to the phase you want to execute. 
   ```sh
   jupyter notebook DataMining.ipynb
   ```
5. Run the cells in the notebooks sequentially to perform the data mining tasks as outlined.

## Results

The notebooks contains detailed results of each Part, including visualizations, statistical analyses, data preprocessing and data mining steps. Ensure to go through the notebook for insights and understanding of the dataset.
The documentation of the implementation of Phase 2 is available in `DataMining_Document_phase2.pdf`.

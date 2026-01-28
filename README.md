# AI Enabled Recommendation Engine for an E-commerce Platform

## Milestone 1: Data Preparation

### Objective
Prepare clean and structured datasets for model development.

### Description
In this milestone, a real-world Amazon Product Reviews dataset was used to collect user and product interaction data.
The dataset was cleaned by handling missing values, removing duplicate records, and resolving inconsistencies.
Only relevant attributes such as user ID, product ID, and rating were retained.

The cleaned data was transformed into a user–item interaction matrix, where rows represent users and columns represent products.
This matrix will be used in the next milestone to develop recommendation models.

### Tasks Completed
- Collected user and product interaction data
- Cleaned and structured the dataset
- Handled data inconsistencies
- Built the user–item interaction matrix

### Tools Used
- Python
- Pandas
- Google Colab

### Dataset
- Amazon Product Reviews Dataset (Kaggle)  
  Dataset by Arham Rumi

## Data Files (Google Drive)

Due to GitHub file size limitations, the processed datasets generated during Milestone 1 are hosted on Google Drive.

- **Cleaned Reviews Dataset (`cleaned_reviews.csv`)**  
  https://drive.google.com/file/d/1NYuWacU84vgyJ2OeKYC6ZR00-cqo1m0r/view?usp=drive_link

- **User–Item Interaction Matrix (`user_item_matrix.csv`)**  
  https://drive.google.com/file/d/1gUbaqX5DiLuOsYES1f8hqhj7BNl2PhFc/view?usp=drive_link

### Access
- Anyone with the link can view and download the files.

> Note: These files were generated as part of the data preparation process and are required for further model development in upcoming milestones.

> Note: Due to GitHub file size limitations, large datasets and generated matrices are not uploaded. The complete data preparation code is available in the notebooks folder.

---

## Milestone 2: Model Building

### Objective
To build and train a recommendation model using the cleaned user–item interaction data prepared in Milestone 1.

### Approach
In this milestone, an item-based collaborative filtering approach was implemented.  
The model uses cosine similarity to identify relationships between products based on historical user ratings.

### Model Description
- A user–item interaction matrix was created from the cleaned dataset.
- Missing values were filled with zero to represent no interaction.
- The matrix was transposed to compute item–item similarity.
- Cosine similarity was used to calculate how similar products are to each other.

### Recommendation Logic
A recommendation function was implemented that:
- Takes a product ID as input
- Finds similar products using the item–item similarity matrix
- Returns the top-N most similar products excluding the product itself

### Evaluation
The model was tested by generating top-N product recommendations for sample products.  
The results show that the system produces meaningful recommendations based on user interaction patterns.

### Tools Used
- Python
- Pandas
- NumPy
- Scikit-learn
- Google Colab
---

## Milestone 3: Evaluation and Refinement

### Objective
To evaluate the performance of the recommendation model built in Milestone 2 and refine it using appropriate evaluation metrics.

### Evaluation Approach
The model was evaluated using an offline evaluation strategy.  
The cleaned user–product interaction data was split into training and testing sets (80% training, 20% testing) to ensure evaluation on unseen data.

### Metrics Used
The following evaluation metrics were used:

- **Precision**: Measures how many of the recommended products were actually relevant.
- **Recall**: Measures how many of the relevant products were successfully recommended.
- **F1-score**: Harmonic mean of precision and recall.
- **Hit@K**: Checks whether at least one relevant product appears in the top-K recommendations.

### Results and Analysis
During evaluation, precision, recall, F1-score, and Hit@K values were observed to be zero for selected test cases.  
This behavior is expected due to the highly sparse nature of real-world e-commerce datasets, where users interact with only a very small subset of products.

The zero metric values indicate limited overlap between recommended items and actual test interactions, which is a known limitation of offline evaluation in recommendation systems rather than a model failure.

### Refinement
To address sparse evaluation challenges, the recommendation list size (Top-N) was increased, and Hit@K evaluation was used as a more suitable metric for sparse datasets.  
Future improvements may include hybrid recommendation approaches, popularity-based filtering, and advanced evaluation strategies.

### Tools Used
- Python
- Pandas
- NumPy
- Scikit-learn
- Google Colab

### Output
- Evaluated recommendation model using Precision, Recall, F1-score, and Hit@K
- Analysis of model performance and limitations
- Refined evaluation strategy suitable for sparse datasets

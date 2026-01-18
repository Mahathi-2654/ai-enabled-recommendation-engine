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

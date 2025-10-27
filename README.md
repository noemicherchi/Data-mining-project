## Data Mining and Machine Learning project
# Music Popularity Across Borders
Project for the Data Mining and Machine Learning course of the Master in Artificial Intelligence and Data Engineering at University of Pisa 
Authors: Feyzan Çolak, Noemi Cherchi 
# Overview of the project
This project applies DMML techiniques to analyze which factors determine the popularity of songs on Spotify in different geographic areas. Understanding the public's preferences is fundamental for marketing and music promotion. The goal is to predict the popularity of a song based on its audio characterstics (such as danceability, energy, tempo, duration, etc...) and to determine which of these make a song successful in different world regions.
# Dataset
The final dataset was built combining two data sources:
- Spotify Charts (from Kaggle): a complete dataset of the "Top 200" and "Viral 50" rankings published by Spotify globally, from the 1st Genuary 2017 on
- Spotify API: used to collect the different audio features for more than songs 200.000 

# Work pipeline 
1. Data Preprocessing: to transform raw data in a clean format suitable for data modeling. Countries were grouped in 11 geographic regions (Northern Europe, Latin America, East Asia, Middle East, etc.). Duplicates of the same songs were removed after computing their ranking mean. A new column for popularity was created: a song was labelled as "popular" if its ranking mean was lower than the 40° percentile and its frequency higher than 60° percentile. The final dataset had 189.297 rows and 15 columns
2. Management of unbalanced classes: in the final dataset, about 80% of the songs were labaled as "non popular". To solve this, oversampling (SMOTE) and undersampling were used
3. Modeling: the data was divided in training (80%) and test set (20%). Five different classification algorithms were used and evaluated: logistic regression, decision trees, random forest, naive bayes, k-nearest neighbors
# Results
Models' performance was evaluated using: accuracy, precision, recall, F1-score and confusion matrices.
The best model found was random forest, with an accuracy of 83.02%, thanks to which it was possibile to predict the popularity of a song and to discover different tastes of music in different world regions.


# Repository structure 

├── documentation/
│   ├── chapter/          
│   └── media/    
├── notebooks_final/
│   ├── algorithms/
|       ├── data_visualization.ipynb
|       ├── decision_tree.ipynb
|       ├── knn.ipynb
|       ├── logistic_regression.ipynb
|       ├── naive_bayes.ipynb
|       ├── random_forest.ipynb
│   ├── preprocessing/
        ├── frequency.ipynb
        ├── preprocessing.ipynb
        ├── spotify_api.ipynb
├── documentation.pdf # complete documentation of the project
└── README.md
|__app.py

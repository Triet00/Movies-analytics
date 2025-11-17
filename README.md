#Movie Analysis: Data Collection, NLP & Predictive Modeling
Complete movie analysis pipeline from data collection to predictive modeling, combining web scraping, advanced NLP techniques, and statistical modeling to understand narrative patterns and predict movie success metrics.

#Project Overview

This project performs end-to-end movie analysis through:
•	Data Collection: Web scraping IMDb for movie data and box office information
•	NLP Analysis: BERT embeddings, topic modeling (LDA), and plot similarity
•	Feature Engineering: Creating predictive features from plot semantics
•	Regression Modeling: Multiple linear regression with log transformations for ROI prediction
Technologies Used
•	Python 3.x
•	NLP: sentence-transformers, gensim, nltk, spacy
•	ML/Stats: scikit-learn, statsmodels, numpy, pandas
Dataset
Scraped data: imdb_scraped_data_with_box_office.xlsx - Fresh IMDb data including movie titles, ratings, votes, plots, budget, and box office figures.
Processed data: movies_with_nlp_features.csv - Original data enhanced with engineered NLP features for modeling.
Analysis Pipeline

Part 1: Data Collection
•	Web Scraping: Automated data collection from IMDb search results
•	Box Office Data: Individual movie page scraping for financial metrics
•	Data Handling: Smart navigation through IMDb's dynamic content and pagination

Part 2: NLP Feature Extraction
•	BERT Embeddings: 384-dimensional plot vectors using all-MiniLM-L6-v2
•	Topic Modeling: 6 narrative topics via LDA (Action, Crime, Family, Sci-Fi, Horror, Romance)
•	Similarity Metrics: Plot similarity to highest-ROI movies
•	Feature Engineering: Centroid distance, embedding complexity, topic probabilities

Part 3: Regression Modeling
•	Log Transformations: Applied to ROI, Budget, Votes, Opening Weekend earnings
•	Logit Transformation: For similarity scores bounded between 0 and 1
•	Multiple Linear Regression: 
•	log(ROI) ~ log(Budget) + Year + Rating + log(Votes) +            log(Opening_Weekend) + logit(Similarity_to_top_ROI) + Topic

#📋 Installation
1.	Clone the repository:
git clone https://github.com/yourusername/movie-plot-analysis.git
cd movie-plot-analysis

2.	Install dependencies:
pip install selenium beautifulsoup4 webdriver-manager pandas openpyxl
pip install numpy sentence-transformers scikit-learn gensim nltk spacy statsmodels

3.	Download NLTK data:
import nltk
nltk.download('stopwords')
nltk.download('punkt')

Usage
1.	Data Collection: Run the web scraping script to gather fresh IMDb data
2.	NLP Analysis: Execute feature extraction to generate embeddings and topics
3.	Regression Modeling: Run statistical modeling for ROI prediction
The complete pipeline:
•	Scrapes current movie data from IMDb with box office information
•	Generates BERT embeddings and discovers narrative topics
•	Creates engineered features from plot semantics
•	Fits multiple regression models with proper transformations
•	Outputs predictions and model summaries
Key Results
•	Fresh Data Collection: Automated scraping of current movie information and box office data
•	Topic Discovery: 6 distinct narrative categories automatically identified
•	Plot Similarity: Quantified similarity between movies based on semantic content
•	ROI Prediction: Multiple regression model incorporating both financial and narrative features
•	Feature Importance: Statistical significance of plot-based features in predicting success
Example Output
Movies similar to 'Terrifier 2':
Horror Movie A: 0.8234 similarity
Horror Movie B: 0.7891 similarity
Horror Movie C: 0.7654 similarity
Identified movie topics:
Topic 0 (Action/Adventure): car, chase, mission, hero...
Topic 4 (Horror): blood, murder, scary, death...
Project Structure
movie-analysis/
├── Project code.py        # IMDb web scraping
├── imdb_scraped_data_with_box_office.xlsx  # Scraped dataset
├── movies_with_nlp_features.csv    # Generated features
└── README.md                       # This file
Applications
•	Content Strategy: Understanding narrative patterns that drive success
•	Investment Decisions: ROI prediction incorporating plot characteristics
•	Recommendation Systems: Plot-based movie similarity matching
•	Market Analysis: Genre trends and audience preferences
•	Data Pipeline: Automated collection and analysis of entertainment industry data
Contributing:
1.	Fork the repository
2.	Create a feature branch (git checkout -b feature/amazing-feature)
3.	Commit your changes (git commit -m 'Add amazing feature')
4.	Push to the branch (git push origin feature/amazing-feature)
5.	Open a Pull Request
License
This project is licensed under the MIT License - see the LICENSE file for details.
Acknowledgments
•	Sentence Transformers team for the pre-trained BERT models
•	Gensim contributors for the LDA implementation
•	NLTK and spaCy teams for NLP preprocessing tools
________________________________________
Note: This analysis focuses on narrative content and semantic understanding of movie plots. The techniques can be extended to other text analysis domains including book analysis, news categorization, and content recommendation systems.


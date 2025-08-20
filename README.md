Content-Based Movie Recommender System
A content-based movie recommender system that suggests similar movies based on their textual features. This project uses the IMDb Top 1000 Movies dataset and leverages TF-IDF Vectorization and Cosine Similarity to find movies with similar genres, plots, and crew.

📋 Table of Contents
Features
Project Workflow
Technologies Used
Setup and Installation
Methodology
Feature Representation: Genre-Only vs. Combined Features
Vectorization: TF-IDF vs. CountVectorizer
How to Use
Dataset
License

✨ Features
Data Cleaning: Preprocesses the IMDb dataset to handle missing values and format text.
Exploratory Data Analysis (EDA): Includes visualizations like genre distribution bar plots, word clouds, and similarity heatmaps.
Feature Engineering: Creates feature sets based on "Genre-Only" and "Combined Features" (Genre, Overview, Director, Stars).
Comparative Analysis: Compares the performance and recommendation quality of TF-IDF vs. CountVectorizer.
Similarity Modeling: Uses Cosine Similarity to calculate the likeness between movies.
Recommendation Function: A simple function to get top N movie recommendations for a given title.

📂 Project Workflow
The project follows a systematic workflow:
Data Loading & Cleaning: The IMDb dataset is loaded, and essential preprocessing is performed to clean the data for analysis.
Exploratory Data Analysis (EDA): Genre distributions are analyzed using plots and word clouds to understand the dataset's composition.
Feature Engineering: Text features (like genres, overview) are converted into numerical vectors using TF-IDF and CountVectorizer.
Model Building: A cosine similarity matrix is computed to determine the similarity score between all pairs of movies.
Recommendation Generation: A function is created to retrieve and rank movies based on their similarity scores to a user's input movie.

🛠️ Technologies Used
Technology	Description
Python	Core programming language.
Pandas	Data manipulation and analysis.
NumPy	Numerical operations.
Scikit-learn	For TF-IDF, CountVectorizer, and Cosine Similarity.
Matplotlib	For creating static and interactive plots.
Seaborn	For high-level, attractive statistical graphics.
WordCloud	To generate genre word clouds.
Jupyter Notebook	For interactive development and analysis.

🚀 Setup and Installation
To run this project locally, follow these steps:
Clone the repository:
code
Bash
git clone https://github.com/your-username/movie-recommender-system.git
cd movie-recommender-system
Create a virtual environment (recommended):
code
Bash
python -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
Install the required libraries:
To install the dependencies, run:
code
Bash
pip install -r requirements.txt
Download the dataset:
Download the IMDB Top 1000 Movies dataset from Kaggle.
Place the imdb_top_1000.csv file in a data/ directory.
Run the Jupyter Notebook:
code
Bash
jupyter notebook Movie_Recommender_System.ipynb
🔬 Methodology
We explored two key decisions in building the recommendation engine.
1. Feature Representation: Genre-Only vs. Combined Features
Genre-Only Approach
How it Works: Uses only the Genre column (e.g., "Action, Adventure, Sci-Fi").
Pros: Fast and simple; good for broad category recommendations.
Cons: Too generic, as many movies share the same genres.
Combined Features Approach
How it Works: Merges Genre, Overview, Director, and Main Stars into a single text feature.
Pros: Creates a rich, detailed movie profile, leading to more specific and nuanced recommendations.
Cons: Computationally more intensive and can be affected by noisy text.
2. Vectorization: TF-IDF vs. CountVectorizer
CountVectorizer
How it Works: Counts the occurrences of each word. It treats common words (e.g., "Action") and rare words equally.
Result: Often recommends movies that share popular, high-frequency tags.
TF-IDF (Term Frequency – Inverse Document Frequency)
How it Works: Measures a word's importance by considering its frequency in a single movie's features while penalizing words that are common across all movies.
Result: Highlights more distinctive similarities, often leading to smarter, more relevant recommendations.
🎬 How to Use
The core of the project is the recommendation function. To get movie suggestions, you can call it with a movie title.
code
Python
# Example of generating recommendations for 'Inception'

# Using the TF-IDF model
print("Recommendations for 'Inception' using TF-IDF:")
recommendations_tfidf = recommend("Inception", cosine_sim_tfidf)
print(recommendations_tfidf)
# Expected Output: A list of movies with complex sci-fi themes.

# Using the CountVectorizer model
print("\nRecommendations for 'Inception' using CountVectorizer:")
recommendations_count = recommend("Inception", cosine_sim_count)
print(recommendations_count)
# Expected Output: A list of movies that are also 'Action' or 'Adventure'.
📂 Dataset
This project uses the IMDB Top 1000 Movies dataset, sourced from Kaggle. It contains detailed information on the top 1000 movies as rated by IMDb users.
Source: Kaggle - IMDB Top 1000 Movies
File: imdb_top_1000.csv
📄 License
This project is licensed under the MIT License. See the LICENSE file for more details.

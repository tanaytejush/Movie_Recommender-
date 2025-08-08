# Movie_Recommender-
This is a Python-based Movie Recommender System built using Streamlit for the user interface. It recommends movies based on the similarity of their content, using a machine learning model to find the most similar films.

Features -
Content-Based Filtering: The system recommends movies that are similar to a selected movie based on their genre, cast, and keywords.

Intuitive UI: A user-friendly web application created with Streamlit allows users to easily select a movie from a dropdown list and receive recommendations.

API Integration: It fetches movie posters from The Movie Database (TMDb) API to provide a visually appealing and informative user experience.

How It Works ⚙-
The core of the system is a cosine similarity model. It works by:

Data Preprocessing: Movie data (titles, genres, keywords, cast) is preprocessed and converted into a numerical representation.

Vectorization: The text data is transformed into a matrix of TF-IDF vectors to capture the importance of words.

Similarity Calculation: Cosine similarity is used to calculate the similarity scores between each movie, creating a similarity matrix.

Recommendation Logic: When a user selects a movie, the system looks up its index in the similarity matrix and retrieves the movies with the highest similarity scores.

Technologies Used -
Python: The primary programming language.

Streamlit: For creating the interactive web application.

Scikit-learn: For machine learning tasks, including vectorization and similarity calculation.

Pandas: For data manipulation and analysis.

Requests: For making API calls to fetch movie posters.

Pickle: To serialize and deserialize the pre-trained model and dataframes.


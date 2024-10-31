# Movie Recommendation System using Content-Based Filtering

This project implements a **content-based recommendation system** to recommend movies based on the similarity of movie features like genres, keywords, and cast. The system is built using the **TMDB 5000 movies dataset** and uses machine learning techniques to suggest movies similar to the one selected by the user.

## Project Structure
```
Movie-Recommendation-System/
│
├── code.ipynb            # Jupyter notebook with the code for the recommendation system
├── tmdb_5000_credits.csv # Dataset containing movie credits (cast and crew)
├── tmdb_5000_movies.csv  # Dataset containing detailed movie information
└── Workflow.png          # Workflow diagram of the recommendation system
```

## Features
- **Content-based filtering** using cosine similarity.
- **Recommendation system** suggesting top 5 similar movies based on the user’s selection.
- **TMDB 5000 Dataset**: Provides detailed metadata of movies such as genres, keywords, cast, and crew.
- **Data Preprocessing**: Cleans and prepares the dataset for feature extraction and similarity analysis.

## Technologies Used
- **Python** for programming.
- **Pandas & NumPy** for data handling and preprocessing.
- **NLTK** for text stemming.
- **Scikit-learn** for feature extraction and similarity computation.
- **Jupyter Notebook** as the development environment.

## Getting Started

### Prerequisites
Make sure you have the following Python packages installed:
```bash
pip install pandas numpy nltk scikit-learn
```

### Running the Jupyter Notebook
1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd Movie-Recommendation-System
   ```

2. Open `code.ipynb` in Jupyter Notebook.

3. Run all the cells to preprocess the data, train the model, and generate recommendations.

## Dataset Overview
The TMDB 5000 movies dataset contains two files:
1. **tmdb_5000_credits.csv**: Includes information about the cast and crew of each movie.
2. **tmdb_5000_movies.csv**: Contains metadata such as genres, keywords, and popularity for each movie.

## Data Preprocessing Steps
1. **Merge Datasets:** Combine `tmdb_5000_movies.csv` and `tmdb_5000_credits.csv` based on movie titles.
2. **Data Cleaning:** Remove null and duplicate values.
3. **Feature Extraction:** Extract relevant fields such as genres, keywords, cast, and crew.
4. **Text Preprocessing:** Apply text stemming and lowercase conversion to make data consistent.
5. **Tag Generation:** Combine multiple features into a single `tags` column.

## Model Architecture
- **Vectorization:** Convert the `tags` column into vectors using **CountVectorizer**.
- **Cosine Similarity:** Compute the similarity between movie vectors.
- **Recommendation Function:** Sort movies based on similarity scores and return the top 5 recommendations.

## Example Code Snippet (Recommendation Function)
```python
def recommend(movie):
    movie_index = new_df[new_df['title'] == movie].index[0]
    distances = similarity[movie_index]
    movies_list = sorted(list(enumerate(distances)), reverse=True, key=lambda x: x[1])[1:6]
    print("Top 5 movies recommended for you are:\n")
    for i in movies_list:
        print(new_df.iloc[i[0]].title)
```

## Usage

1. **Select a Movie:** Choose a movie title from the dataset.
2. **Run the Recommendation Function:** Use the function `recommend()` with the selected movie.
3. **View Recommendations:** The top 5 similar movies will be printed.

### Example Output
```bash
Top 5 movies recommended for you are:

Aliens vs Predator: Requiem
Aliens
Falcon Rising
Independence Day
Titan A.E.
```

## License
This project is licensed under the **MIT License**.

## Acknowledgments
- **TMDB 5000 Dataset**: Provided by The Movie Database (TMDB).
- **Scikit-learn**: Used for machine learning algorithms and vectorization.
- **NLTK**: Used for stemming operations.

---

This README provides all the necessary information to understand, set up, and run the movie recommendation system. Enjoy finding your next favorite movie!

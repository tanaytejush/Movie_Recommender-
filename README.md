# Movie Recommender System

A content-based **movie recommendation web app** built with Python and Streamlit. Pick a movie from the dropdown and get five similar films, each shown with its poster.

## Features

- **Content-based filtering**: recommends movies similar to the selected one based on genre, cast and keywords
- **Simple UI**: a Streamlit page with a searchable dropdown and a "Show Recommendation" button
- **Movie posters** fetched from [The Movie Database (TMDb)](https://www.themoviedb.org/) API, with a placeholder when a poster is missing

## How it works

1. **Preprocessing**: titles, genres, keywords and cast are cleaned and combined into text per movie.
2. **Vectorisation**: the text is converted into a TF-IDF matrix that captures how important each word is.
3. **Similarity**: cosine similarity between every pair of movies produces a similarity matrix.
4. **Recommendation**: for the selected movie, the app looks up its row in the matrix and returns the five most similar titles.

The pre-computed data is stored with `pickle`:

| File | Contents |
|------|----------|
| `model/movie_list.pkl` | DataFrame of movie titles and TMDb ids |
| `model/similarity.pkl` | Cosine similarity matrix (**not included in this repo**, see below) |

## Tech stack

Python, Streamlit, scikit-learn, pandas, requests, pickle

## Run it locally

```bash
pip install streamlit scikit-learn pandas requests
streamlit run app.py
```

### Before you run

- **Similarity matrix**: `app.py` loads `model/similarity.pkl`, which is not committed because of its size. Regenerate it from the TMDb 5000 movies dataset by running the vectorisation steps above and saving the result to `model/similarity.pkl`. Note the app looks in a folder named `model` (lowercase).
- **TMDb API key**: poster fetching needs a free TMDb API key. Get one from your TMDb account settings and set it in `fetch_poster()` in `app.py`. Do not commit your key to a public repository.

## Project structure

```
app.py     Streamlit app and recommendation logic
model/     Pickled movie list (and similarity matrix once generated)
```


---

<sub>Made by [tanaytejush](https://github.com/tanaytejush)</sub>

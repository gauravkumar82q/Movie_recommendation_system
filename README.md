# 🎬 Movie Recommendation System

This is a Content-Based Movie Recommendation System built using Python and Scikit-Learn.  
It recommends similar movies based on genre similarity using CountVectorizer + Cosine Similarity.

## 🚀 Features
- Content-based filtering (genre similarity)
- Partial title matching (user can type part of a movie name)
- Top-10 movie recommendations
- Clean and simple ML pipeline
- Works with any movies.csv containing `title` and `genres`

## 🧠 Tech Stack
- Python
- Pandas
- Scikit-Learn
- CountVectorizer
- Cosine Similarity
- Google Colab / Jupyter Notebook

## 📌 How It Works
1. Load movies.csv  
2. Preprocess titles and genres  
3. Convert genres to vectors using CountVectorizer  
4. Calculate similarity between movies  
5. Recommend top similar movies

## 🧪 Core Recommendation Function
```python
def recommend(movie_name):
    movie_name = movie_name.lower()
    matches = df[df['title'].str.lower().str.contains(movie_name)]

    if matches.empty:
        return ["Movie not found."]

    idx = matches.index[0]
    distances = list(similarity[idx])
    sorted_list = sorted(enumerate(distances), reverse=True, key=lambda x: x[1])[1:10]

    return [df.iloc[i[0]].title for i in sorted_list]
```

## 📂 Project Structure
```
movie-recommender/
│── movies.csv
│── movie_recommender.ipynb
│── README.md
```

## 🌟 This Project 
- Demonstrates understanding of ML pipelines  
- Real-world use case (recommendation systems)
- Shows knowledge of vectorization + similarity search  


## 📈 Future Improvements
- Add TMDb API for posters and descriptions  
- Hybrid (Content + Collaborative) model  
- Streamlit UI + Deployment

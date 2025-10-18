# Movie Recommender System

A content-based movie recommendation system built with Streamlit that suggests similar movies based on your selection. The system uses cosine similarity to find movies with similar features and displays them with posters fetched from TMDb API.

## 🎬 Features

- **Intuitive Interface**: Clean and user-friendly web interface
- **Movie Recommendations**: Get 5 similar movie suggestions based on content
- **Poster Display**: Visual movie posters fetched from TMDb API
- **Real-time Search**: Type or select from dropdown to find movies
- **Content-Based Filtering**: Uses movie features to find similar items


## 🛠️ Installation

1. **Clone the repository** or create project directory

2. **Install required dependencies**:
```bash
pip install streamlit requests pickle5 pandas numpy scikit-learn
```

## 📊 Model Development (Jupyter Notebook)

The **`notebook86c26b4f17.ipynb`** file contains the complete data processing and model training workflow used to build the recommendation engine.

---

### 🧹 Data Processing Steps
- **Data Loading:** Loaded TMDb 5000 Movies and Credits datasets.  
- **Data Merging:** Combined both datasets to unify movie and cast information.  
- **Feature Extraction:** Extracted key attributes like *genres*, *keywords*, *cast*, and *crew*.  
- **Text Processing:** Converted JSON strings to Python lists for easier manipulation.  
- **Tag Creation:** Merged overview, genres, keywords, cast, and director into a single descriptive feature — *tags*.  

---

### 🧠 Feature Engineering
- **Genres:** Extracted and cleaned genre names from JSON format.  
- **Keywords:** Filtered and normalized movie keywords.  
- **Cast:** Limited to the top 3 actors to reduce noise.  
- **Crew:** Extracted only the *director* from the crew data.  
- **Text Normalization:** Removed spaces and standardized text for vectorization.  

---

### ⚙️ Model Training
- **Vectorization:** Used `CountVectorizer` (max features = 5000) to convert text tags into feature vectors.  
- **Cosine Similarity:** Computed similarity scores between all movie vectors.  
- **Model Export:**  
  - `movie_list.pkl` → Processed movie data  
  - `similarity.pkl` → Precomputed cosine similarity matrix  

---

### 📈 Outcome
The processed and vectorized dataset allows the Streamlit app to:
- Quickly retrieve similar movies based on cosine similarity.  
- Efficiently display movie posters and names in real time.  
- Deliver accurate and visually appealing content-based recommendations.

## 🎯 How It Works

This project uses a **content-based filtering approach** that analyzes movie attributes to recommend similar titles. The recommendation logic is driven by **cosine similarity** between movie feature vectors.

---

### 🧩 Recommendation Algorithm
1. **Feature Extraction:**  
   Each movie is represented using combined features — *overview, genres, keywords, cast,* and *director*.  
2. **Text Vectorization:**  
   These textual features are converted into numerical vectors using **CountVectorizer**.  
3. **Cosine Similarity Computation:**  
   Measures the similarity between movies by comparing vector angles.  
4. **Top Recommendations:**  
   The top 5 movies with the highest similarity scores to the selected movie are displayed.  

---

### 🌐 API Integration
- **TMDb API:** Fetches movie poster images using unique movie IDs.  
- **Poster Retrieval:** The app dynamically retrieves and displays high-quality posters.  
- **Real-time Data:** Ensures accurate and visually rich recommendations by fetching the latest poster paths from TMDb.  

---

### 💡 User Interaction Flow
1. User selects or searches for a movie in the Streamlit app.  
2. The system finds movies with the most similar content profiles.  
3. Posters and titles of the top 5 recommendations are displayed side by side.  
4. Users can explore multiple movies interactively without reloading the app.  


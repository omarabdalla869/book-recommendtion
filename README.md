# book-recommendtion
📚 Book Recommendation System

"Find the right book for every reader – powered by data, embeddings, and emotions!"

🚀 Overview

This project builds a smart book recommendation system using:

7,000+ books metadata

Natural Language Processing (NLP) for semantic search

Emotion and category prediction to enhance recommendations

It goes beyond basic filtering by understanding what readers feel and want.

🗂 Workflow
1. Data Acquisition

Dataset: 7k Books with Metadata

Loaded automatically using KaggleHub

import kagglehub
dataset_path = kagglehub.dataset_download("dylanjcastillo/7k-books-with-metadata")

2. Feature Engineering

Handled missing values (description)

Added new features like age_of_book

Prepared data for semantic search

books["missing_description"] = books["description"].isna().astype(int)
books["age_of_book"] = 2024 - books["published_year"]

3. Semantic Recommendations

Uses vector embeddings to find similar books

Example:

retrieve_semantic_recommendations("magic fantasy adventure", top_k=5)


Returns books with themes similar to the query.

4. Emotion & Category Analysis

Category Prediction: Fiction vs. Nonfiction

Emotion Detection: Understands emotional tone of a description

predict_category("A story about dragons and magic")  # Fiction
analyze_emotions("A scary haunted house story")      # {'fear': 0.87, ...}

5. Visualization & Insights

Missing data visualization

Publication year trends

Emotion distribution across books

🔧 Tech Stack

Python: Data handling & ML

Pandas, NumPy: Data processing

Matplotlib, Seaborn: Visualization

Transformers (HuggingFace): NLP for emotions & categories

🖥 How to Run
git clone https://github.com/your-username/book-recommendation.git
cd book-recommendation
pip install -r requirements.txt
jupyter notebook recommendation_book.ipynb

🌟 Why This Project?

Traditional recommendations rely on ratings – ours understands meaning & emotion.

Can be extended to:

Personalized recommendations

Integration into eBook platforms

Real-time user feedback

🛠 Future Enhancements

Deploy as a Streamlit web app

Use state-of-the-art embeddings (e.g., OpenAI, SBERT)

Add user preference learning

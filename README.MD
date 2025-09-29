# AI Anime Recommender System

A modern, LLM-powered anime recommender system that leverages vector search and large language models to provide personalized anime recommendations based on user preferences.

## Features

- **Natural Language Recommendations:** Enter your anime preferences in plain English and get relevant suggestions.
- **LLM Integration:** Uses advanced language models (e.g., Llama, Groq) for understanding and generating recommendations.
- **Vector Search:** Embeds anime synopses and retrieves the most relevant titles using semantic similarity.
- **Streamlit Web App:** User-friendly interface for interactive recommendations.

## Project Structure

```
.
├── app/                # Streamlit web app
├── config/             # Configuration files and API keys
├── data/               # Anime dataset (CSV)
├── pipeline/           # Data/vector pipeline scripts
├── src/                # Core logic: data loading, vector store, recommender
├── utils/              # Logging and custom exceptions
├── requirements.txt    # Python dependencies
├── setup.py            # Package setup
```

## Quickstart

1. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

2. **Set up environment variables:**
   - Create a `.env` file in the root directory.
   - Add your API keys (e.g., for Groq/OpenAI):
     ```
     GROQ_API_KEY=your_groq_api_key
     ```

3. **Build the vector store:**
   ```bash
   python pipeline/build_pipeline.py
   ```

4. **Run the web app:**
   ```bash
   streamlit run app/app.py
   ```

5. **Use the app:**  
   - Enter your anime preferences (e.g., "light-hearted anime with school settings") and get recommendations!

## Dataset

- Uses `data/anime_with_synopsis.csv` (ensure this file is present and formatted correctly).

## Main Components

- **AnimeDataLoader:** Loads and preprocesses anime data.
- **VectorStoreBuilder:** Embeds and stores anime data for fast retrieval.
- **AnimeRecommender:** Uses LLMs and vector search to generate recommendations.
- **AnimeRecommendationPipeline:** Orchestrates the end-to-end recommendation process.

## Requirements

See `requirements.txt` for all dependencies, including:
- `langchain`, `streamlit`, `chromadb`, `pandas`, `python-dotenv`, `sentence-transformers`, etc.

## Customization

- Swap out the LLM or embedding model by editing `config/config.py` and `src/vectorstore.py`.
- Add more data or features to the CSV for richer recommendations.

## Troubleshooting

- **ModuleNotFoundError:** Make sure to run scripts from the project root, or add the root to your `PYTHONPATH`.
- **dotenv errors:** Ensure `python-dotenv` is installed and `.env` is present.

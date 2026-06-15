## News Articles ETL Pipeline (Apple News)

This project is an automated Python-based ETL (Extract, Transform, Load) pipeline that collects, cleans, and stores global trending news articles about Apple.

### What it Does
*   **Extracts**: Connects to the NewsAPI `everything` endpoint to fetch popular news articles mentioning "Apple".
*   **Transforms**: Converts the raw JSON response into a structured Pandas DataFrame, dropping complex and unused columns (`source` and `urlToImage`).
*   **Loads**: Securely loads the refined data into a PostgreSQL database table named `articles_pipeline` using SQLAlchemy.

### Project Architecture
The pipeline is self-contained within `pipeline.py` and uses a modular function structure:
*   `extract_articles()`: Handles authentication and downloads raw JSON data from NewsAPI.
*   `transform_articles()`: Normalizes the data structure using Pandas.
*   `load_articles()`: Manages the connection pool and streams data rows safely to PostgreSQL.
*   `main()`: Coordinates the execution of the entire ETL sequence.

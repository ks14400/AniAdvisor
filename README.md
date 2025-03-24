# Anime Recommendation System with LLMs and Web Scraping

## Overview

This project is a personal endeavor to build an anime recommendation system using data scraped from MyAnimeList (MAL). The project leverages web scraping techniques, data preprocessing, and advanced natural language processing (NLP) methods—including embedding generation and fine-tuning using Parameter-Efficient Fine-Tuning (PEFT) with LoRA—to deliver personalized recommendations based on rich anime metadata.

## Features

- **Data Collection & Scraping:**  
  - Scrapes club IDs from MAL to identify active communities.
  - Retrieves usernames from clubs using the Jikan API.
  - Collects users' anime lists via API calls.
  - Downloads anime HTML pages and extracts detailed anime information (e.g., name, score, genres, synopsis, etc.) using BeautifulSoup.

- **Data Preprocessing:**  
  - Merges data from multiple sources into a comprehensive dataset.
  - Cleans and combines key fields (such as `Name_synopsis`, `Genres_synopsis`, and `sypnopsis`) into a rich `combined_text` field for each anime.

- **Embedding Generation & Fine-Tuning:**  
  - Uses the `all-mpnet-base-v2` Sentence Transformer to generate semantic embeddings for anime descriptions.
  - Fine-tunes the model on domain-specific anime similarity pairs using PEFT with LoRA, adapting the embedding space to better capture the nuances of the anime domain.

- **Recommendation Engine:**  
  - Computes cosine similarity between user queries and anime embeddings to generate personalized recommendations.
  - Integrates multiple metadata signals to refine recommendations.

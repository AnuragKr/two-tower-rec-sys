## TwoTowerNewsRec: Personalized News Recommendation System

## Project Overview

TwoTowerNewsRec is a personalized news recommendation system that leverages two-tower neural network embeddings to generate candidate news articles for each user. The system further re-ranks candidates using content-based filtering to maximize user engagement and relevance.

It is designed to handle user behavior, news content, and metadata, and can provide real-time recommendations even in cold-start scenarios.

## Features

+ Generate user and news embeddings using a two-tower neural network.
+ Perform candidate generation via embedding similarity (cosine similarity).
+ Re-rank recommendations using content-based filtering leveraging two-tower embeddings and user interaction history.
+ Support for batch and single-user recommendation.
+ Handles interaction history, metadata, and embedding features.
+ Designed for scalability and modular architecture.

## Architecture
1. Two-Tower Neural Network
   + User Tower: processes user features/embeddings into a dense vector.
   + News Tower: processes news content, metadata, and embeddings into a dense vector.
   + Output: similarity scores between user and news embeddings.

Training:
 + Optimized using Margin Ranking Loss (MNR) to maximize similarity for positive interactions.
 + Supports negative sampling to train embeddings effectively.

2. Candidate Generation
   + Compute cosine similarity between user embeddings and news embeddings.
   + Generate top-K candidate news per user.

3. Content-Based Re-ranking
   + Re-rank candidates using user history and two-tower embeddings.
   + Combines embedding similarity and past interaction patterns.

## Dataset

The system uses the following datasets:
+ User Data: deviceId, user features, user embedding.
+ News Data: hashId, title, content, categories, hashtags, news embedding.
+ Interactions Data: deviceId, hashId, overallTimeSpent, event_type, timestamp.

These datasets are used to train embeddings, generate candidate news, and perform content-based re-ranking.

## Future Work

+ Incorporate temporal dynamics in recommendations.
+ Improve cold-start handling using content and metadata features.
+ Extend to collaborative filtering or hybrid ranking in future versions.
+ Deploy real-time recommendation API with FastAPI / Flask.

## License

This project is licensed under the MIT License.

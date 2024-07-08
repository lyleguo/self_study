## Types
1. Content-based filtering: Content-based filtering uses item features to recommend other items similar to what the user likes, based on their previous actions or explicit feedback.
2. Collaborative-filtering: Collaborative filtering uses similarities between users and items simultaneously to provide recommendations.
3. Hybrid

## Deep Learning Recommendation System
Survey: Deep Learning based Recommender System: A Survey and New Perspectives

- They use either one type of neural networks (MLP, CNN, RNN, AE, etc) or multiple of them.

**MLP based models**

- Combine matrix factorization with MLP.
- Use MLP to learn feature representations.

**Autoencoder based models**

- Use autoencoder to learn lower-dimensional feature representations. (Reconstruct user/item vector)
- Fill the blanks of the interaction matrix directly in the reconstruction layer.

**CNN/RNN based models**

- Use CNN to extract features.

- Use RNN to encode sequential data.

- Use RNN for sequential recommendation.

**Reinforcement learning models**


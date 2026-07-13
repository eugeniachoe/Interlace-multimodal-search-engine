# Interlace-multimodal-search-engine

A semantic search prototype that translates natural language "vibes" into visual product matches across a catalog of 30,000+ ASOS products — no filters required.

Overview
Traditional keyword search struggles with subjective fashion queries like "coastal summer cardigan" or "Y2K cyber party look." This system bridges the gap between human intent and product discovery by combining vision-language embeddings with metadata filtering, allowing users to describe what they want conversationally and get back visually relevant results instantly.

How It Works
1. CLIP Embeddings — Fashion-CLIP (patrickjohncyh/fashion-clip) encodes all 30,000+ product images into 512-dimensional vectors. When a user submits a query, the text encoder generates a matching vector.
2. FAISS Vector Search — Retrieves the top-K visually similar products from the image index in seconds.
3. Pandas Metadata Filtering — Applies hard constraints like price range and category that CLIP cannot handle, narrowing results to match the full user intent.

Tech Stack
* Python
* HuggingFace Transformers (Fashion-CLIP)
* FAISS
* Pandas
* Google Colab
  
Dataset
* Primary: ASOS Kaggle Dataset (30,000+ product images with metadata)
* Supplementary: DeepFashion (800,000+ annotated fashion images)
  
Performance Metrics
- Recall@10 — How often a relevant item appears in the top 10 results
- Mean Reciprocal Rank (MRR) — How highly ranked the best match is on average
- Latency — Target under 3 seconds for the full search pipeline

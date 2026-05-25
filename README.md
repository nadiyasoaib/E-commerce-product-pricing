# E-commerce-product-pricing
A repository for managing, analyzing, and optimizing e-commerce product pricing strategies. Includes data models, APIs, and pricing algorithms.
# E-Commerce Product Pricing

A multimodal machine learning repository designed to manage, analyze, and optimize e-commerce product pricing strategies. This project was  leverages both textual descriptions and product images to accurately predict item prices.

## 🚀 Project Overview

Predicting the correct price for an e-commerce product requires understanding both its visual appeal and its functional description. This project utilizes a **Multimodal Fusion Architecture** to combine text embeddings, image embeddings, and categorical metadata into a single optimized price-prediction model.

### Key Features
* **Smart Data Extraction:** Custom parsing logic to extract key details (Brand, Unit, Quantity) from raw `catalog_content` strings.
* **Text Embeddings:** Utilizes `SentenceTransformer` (`all-MiniLM-L6-v2`) to encode product titles and bullet points into rich 384-dimensional vectors.
* **Image Embeddings:** Uses **OpenAI's CLIP** (`ViT-B/16`) to extract 512-dimensional visual features from product images.
* **Advanced Multimodal MLP:** A custom PyTorch neural network featuring:
  * Independent text, image, and metadata encoders.
  * Cross-attention mechanism (Text attending to Image).
  * Pseudo-Huber loss optimization for robust regression.
  * 5-Fold Cross Validation for stable predictions.
* **Interactive Web UI:** A Flask-based web application with an inline UI (tunneled via Cloudflare) that allows users to upload an image, enter a description, and get a real-time price prediction.

## 📁 Repository Structure

```text
E-commerce-product-pricing/
├── src/
│   └── utils.py              # Helper scripts (e.g., smart image downloading)
├── main.ipynb                # Core notebook: Data processing, embedding generation, model training, and Flask App
├── .gitignore                # Ignored files (data, embeddings, models)
├── LICENSE                   # Open-source license
└── README.md                 # Project documentation

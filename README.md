# Semantic Product Image Search

An end to end visual search system that finds products using natural language descriptions, uploaded images, or PDF mood boards. Built with CLIP embeddings and ChromaDB vector search, indexed on 44,000 fashion products.

## Live Demo

[Open in Colab](https://colab.research.google.com/github/Fatima-Shahid11/semantic_product_search/blob/main/Semantic%20Product%20Search.ipynb)

## What it does

Type "black leather handbag" and instantly see matching products. Upload a photo of a shoe and find visually similar ones. Drop in a PDF mood board and retrieve the closest products for every image inside it. No keyword matching — the system understands meaning.

## How it works

Every product image is converted into a 512 number embedding using CLIP, a multimodal model trained by OpenAI on 400 million image text pairs. These embeddings are stored in ChromaDB. At query time, the input is embedded using the same CLIP model and compared against all stored embeddings using cosine similarity. Top matches are returned in milliseconds.

<img width="193" height="273" alt="image" src="https://github.com/user-attachments/assets/508b6387-90fb-4007-8706-375dc55b3003" />

<img width="1367" height="290" alt="image" src="https://github.com/user-attachments/assets/ca592cbd-f6da-4723-be45-0b0ee09a189e" />

## Features

Text search finds products from plain English descriptions even when no exact keyword match exists in the product name.

Image search uploads any product photo or illustration and finds visually similar items regardless of color name, brand, or category label.

PDF mood board search extracts every image from an uploaded buyer catalog or trend book and retrieves the closest catalog matches for each one automatically.

## Tech stack

CLIP ViT B 32 via sentence transformers for image and text embeddings. ChromaDB for persistent vector storage and cosine similarity search. PyMuPDF for PDF image extraction and page rendering. Gradio for the interactive UI with drag and drop support. Python and PIL for image loading and batch processing.

## Results

Indexed 4,900 products from the Fashion Product Images dataset. Text queries like "formal watch", "blue summer dress", and "red leather sneakers" return semantically correct results even without exact keyword matches. A 6 image mood board returns 18 matched products in under 3 seconds on CPU.

## How to run

Open the notebook in Colab and run all cells in order. The first run downloads CLIP and the dataset and embeds all images into ChromaDB. Subsequent runs load from the persisted database instantly.

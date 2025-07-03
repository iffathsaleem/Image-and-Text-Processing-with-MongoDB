# Data Engineering Coursework: Image and Text Processing with MongoDB
## Overview
This project, part of the 5DATA005C.1 Data Engineering coursework, focuses on building a Content-Based Image Retrieval (CBIR) system and performing sentiment analysis on text reviews. The system processes images from various genres (Fashion, Animals, Art, Automotive, Travel) and text reviews (Travel, Fashion, Cars) to create two MongoDB databases: one for image data (features, metadata, and binary images) and one for text data (processed reviews and sentiment labels). The project was completed by Iffath Saleem (UOW ID: W2052156, IIT No: 20231818) under the guidance of Ms. Yaalini Balathasan.

## Objectives
The primary objectives are:

Image Database: Develop a CBIR system to store and retrieve images based on visual features (color, shape, texture) and metadata (keywords, descriptions) for genres like Fashion, Animals, Art, Automotive, and Travel.
Text Database: Perform sentiment analysis on user-generated reviews (Travel, Fashion, Cars) to classify sentiments as positive, negative, or neutral, enhancing user experience with relevant insights.
Integration: Store processed data in MongoDB for efficient retrieval and management.

## Data Sources
### Image Files

Cars: Sourced from Supercars.net for high-quality supercar images.
Animals: Obtained from Pexels for diverse animal photographs.
Art: High-quality reproductions from Top of Art.
Fashion: Curated from Pinterest for fashion trends and styles.
Travel: Compiled from UNESCO Cultural Heritage Site pages on Wikipedia.

### Text Files

Travel Reviews: Extracted from the Travel Recommendation Dataset on Kaggle.
Fashion Reviews: Sourced from the Women's Clothing E-Commerce Reviews dataset.
Car Reviews: Obtained from the Reviews of 5 Car Brands dataset on Kaggle.

## Methodology
### Image Processing

Data Ingestion: Import images from specified directories.
Renaming: Apply a consistent naming convention (e.g., 1.jpg, 2.jpg) for organized file management.
Processing:
Resizing: Uniformly resize images to 500x500 pixels.
Orientation Correction: Rotate images to ensure consistent alignment.
Noise Reduction: Apply Gaussian Blur for improved image quality.

Metadata Creation: Generate metadata with keywords and descriptions for each image to enhance searchability.
Feature Extraction:
Color Features: Calculate mean intensity of RGB channels.
Shape Features: Extract contours, perimeter length, centroid, and bounding box.
Texture Features: Compute GLCM metrics (contrast, dissimilarity, homogeneity, energy, correlation, ASM).

Storage: Save metadata and features in JSON files and insert into MongoDB collections (Image_Features, Image_Metadata, Images).
Validation: Query MongoDB to ensure accurate storage and retrieval.

## Text Processing

Data Ingestion: Import text reviews from CSV files into text files.
Preprocessing:
Tokenization: Split text into words using NLTK's word_tokenize.
Stop Word Removal: Remove common words (e.g., 'the', 'a') using NLTK's stopwords.
Punctuation Removal: Eliminate punctuation to focus on meaningful content.

Vectorization: Convert text to numerical format using Bag of Words (BoW) and Term Frequency-Inverse Document Frequency (TF-IDF).
Sentiment Analysis: Use TextBlob to classify reviews as positive, negative, or neutral based on polarity scores.
Storage: Save processed text and sentiment labels in JSON files and insert into MongoDB collections (Reviews, Labels).
Validation: Query MongoDB to verify accurate storage of sentiment labels.

# Book Recommender System

A collaborative filtering based book recommendation web app built with Flask.

This project helps users discover similar books by entering a title they already know, then returns related recommendations based on reader rating patterns from the dataset.

The app combines a trained recommendation model, saved pickle files, and a clean web interface. The home page highlights popular books, while the recommendation page lets users search for a title and view suggested books with cover images and author details.

## Features

- Shows the top popular books from the dataset
- Recommends similar books based on a selected title
- Uses book cover images, author names, ratings, and vote counts
- Includes a Jupyter notebook for the model-building workflow

## Requirements

- Python 3.9 or higher
- Flask
- NumPy
- Pandas
- Gunicorn

Install dependencies:

```bash
pip install -r requirements.txt
```

## Run Locally

Start the Flask app:

```bash
python app.py
```

## How It Works

The notebook creates the processed data and similarity matrix used by the app. The Flask app loads these files:

```text
popular.pkl
pt.pkl
books.pkl
similarity_scores.pkl
```

When a user enters a book title, the app finds similar books using the saved similarity scores and displays the recommended titles with cover images.

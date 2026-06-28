# Book Recommender System

This project is a book recommendation web app built with Flask. It helps users discover similar books by entering a title they already know, then returns related recommendations based on reader rating patterns from the dataset.

The app combines a trained recommendation model, saved pickle files, and a clean web interface. The home page highlights popular books, while the recommendation page lets users search for a title and view suggested books with cover images and author details.

## Features

- Shows the top popular books from the dataset
- Recommends similar books based on a selected title
- Uses book cover images, author names, ratings, and vote counts
- Includes a Jupyter notebook for the model-building workflow
- Ready for deployment with Gunicorn

## Project Structure

```text
.
├── app.py
├── book-recommender-system.ipynb
├── requirements.txt
├── Procfile
├── popular.pkl
├── pt.pkl
├── books.pkl
├── similarity_scores.pkl
├── data/
│   ├── Books.csv
│   ├── Ratings.csv
│   └── Users.csv
└── templates/
    ├── index.html
    └── recommend.html
```

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

Open the app in your browser:

```text
http://127.0.0.1:5000/
```

Do not open the HTML files directly with Live Server. The templates use Flask/Jinja, so they must be served through the Flask app.

## How It Works

The notebook creates the processed data and similarity matrix used by the app. The Flask app loads these files:

```text
popular.pkl
pt.pkl
books.pkl
similarity_scores.pkl
```

When a user enters a book title, the app finds similar books using the saved similarity scores and displays the recommended titles with cover images.

## Deployment

The app can be deployed on platforms such as Render, Railway, or Heroku.

Use this start command:

```bash
gunicorn app:app
```

The `Procfile` already contains:

```text
web: gunicorn app:app
```

Make sure the pickle files are included in the deployed project because they are required when the app starts.

## Dataset

The project uses book, rating, and user CSV files stored in the `data/` folder. The processed model files are generated from this data in the notebook.

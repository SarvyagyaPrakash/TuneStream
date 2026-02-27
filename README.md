# TuneStream 🎵

TuneStream is a web-based music recommendation engine built with **Flask**, **MongoDB**, and **Machine Learning** (`scikit-learn`). 
By entering your favorite artist, TuneStream analyzes musical genres and popularity metrics using Cosine Similarity to recommend similar artists and track suggestions tailored to your taste.

## Features

- **Artist Recommendations:** Input an artist you love, and get a curated list of top 5 similar artists.
- **Machine Learning Powered:** Utilizes `scikit-learn` to compute Cosine Similarity on one-hot encoded genre data for accurate recommendations.
- **MongoDB Integration:** Artists data (name, genre, popularity, top song) is efficiently stored and queried from a local MongoDB database.
- **Web Interface:** A simple and intuitive web UI built with Flask to interact with the recommendation engine.

## Technologies Used

- **Backend:** Python, Flask
- **Machine Learning:** `scikit-learn`, `pandas`, `numpy`
- **Database:** MongoDB (`pymongo`)
- **Frontend:** HTML/CSS (Jinja2 templates)

## Prerequisites

Before running the project locally, ensure you have the following installed:
- [Python 3.x](https://www.python.org/downloads/)
- [MongoDB](https://www.mongodb.com/try/download/community) (running locally on `mongodb://localhost:27017/`)
- Git

## Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/SarvyagyaPrakash/TuneStream.git
   cd TuneStream
   ```

2. **Database Setup:**
   Ensure your local MongoDB instance is running. You will need a database named `Music` with a collection named `Artists`. The documents should contain the fields: `name`, `genre`, `popularity`, and `song`.

3. **Install dependencies:**
   ```bash
   pip install flask pymongo scikit-learn numpy pandas
   ```

4. **Run the Application:**
   ```bash
   python app.py
   ```

5. **Access the App:**
   Open your web browser and navigate to `http://127.0.0.1:5000`.

## How It Works

1. The app fetches artist data from the MongoDB `Music` database.
2. It preprocesses the data by applying **one-hot encoding** to the `genre` feature.
3. When a user inputs an artist, the system generates a feature vector and calculates the **Cosine Similarity** against all other artists in the database.
4. The top 5 similar artists are returned directly to the web interface alongside their popularity scores and recommended songs.

## License

This project is open-source and available to use.

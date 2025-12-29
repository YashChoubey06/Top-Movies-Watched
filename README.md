# Top-Movies-Watched

# 🎬 My Top 10 Movies

This project is a dynamic, full-stack web application built to help users curate, rate, and automatically rank their all-time favorite films. It combines real-time data from a global movie database with a personalized local collection.

The primary goal of this project was to master **API integration**, **Relational Database management (ORM)**, and **interactive UI/UX design** using Python and Flask.

---

## 🚀 Key Features

* **TMDB API Integration:** Instead of manual entry, the app connects to **The Movie Database (TMDB) API** to search for titles and fetch high-resolution posters, release dates, and plot overviews.
* **Automatic Dynamic Ranking:** The app includes logic to automatically re-rank the entire collection every time the homepage loads; the highest-rated movie is always assigned rank #1.
* **Interactive 3D UI:** Uses custom CSS3 **3D transforms** to create a card-flip effect. The front shows the movie's ranking and poster, while the back reveals the user's personal review and rating.
* **Full CRUD Functionality:** Users can **Create** (add from API), **Read** (view list), **Update** (edit ratings/reviews), and **Delete** movies seamlessly from the interface.
* **Form Validation & Security:** Utilizes **Flask-WTF** and **WTForms** for secure data entry and CSRF protection when adding or editing movie details.

---

## 🛠️ Tech Stack

* **Backend:**
* **Python:** Core application logic.
* **Flask (2.3.2):** Web framework and routing.
* **SQLAlchemy (2.0.25):** ORM for managing the SQLite database through Python classes.


* **Frontend:**
* **Jinja2:** For dynamic HTML rendering and template inheritance.
* **Bootstrap 5:** Via `Bootstrap-Flask` for responsive layouts and styled forms.
* **CSS3:** Custom styles for animations, flexbox layouts, and the 3D card perspective.


* **Database:** * **SQLite:** Local persistent storage for the movie collection.
* **APIs:**
* **The Movie Database (TMDB):** For sourcing comprehensive film metadata.


---

## ⚙️ How It Works

1. **Search:** When a user clicks "Add Movie," they enter a title. The app sends a GET request to the TMDB API `search/movie` endpoint.
2. **Select:** The API returns a list of matches, which are displayed on a selection page.
3. **Fetch & Save:** Once a movie is selected, the app calls the TMDB `movie/{id}` endpoint to get full details (description, poster path) and saves a new record to the `books.db` SQLite database.
4. **Rate:** The user is redirected to an "Edit" form to provide their own rating (0-10) and a personal review.
5. **Rank:** Every time the home route (`/`) is accessed, the backend queries the database, sorts all movies by rating in descending order, and updates their `ranking` attribute in the database before rendering the page.

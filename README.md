# 📚 Book Recommendation System

A simple **book recommendation system** built with Python using **user-based collaborative filtering** and **cosine similarity**. The system recommends books to users based on the rating patterns of other users with similar preferences.

## 🚀 Project Overview

Recommendation systems are widely used by platforms such as Amazon, Netflix, Spotify, and Goodreads to suggest content that users may enjoy.

This project demonstrates a basic **collaborative filtering** approach where users are compared based on their book ratings. Books that highly similar users have rated positively are then recommended to the target user.

## 🛠️ Technologies Used

* Python
* Pandas
* Scikit-learn
* Cosine Similarity

## 📊 Dataset

The project uses a small sample dataset containing:

* `user_id` — Unique identifier for each user
* `book_title` — Name of the book
* `rating` — Rating given by the user

Example:

| User ID | Book   | Rating |
| ------- | ------ | -----: |
| 1       | Book A |      5 |
| 1       | Book B |      3 |
| 1       | Book C |      4 |
| 2       | Book A |      4 |
| 2       | Book D |      5 |
| 3       | Book B |      5 |

## ⚙️ How It Works

### 1. Create the User-Book Matrix

The ratings are transformed into a matrix where:

* Rows represent users
* Columns represent books
* Values represent ratings

Books that a user has not rated are represented by `0`.

### 2. Calculate User Similarity

The system uses **cosine similarity** to compare users based on their rating patterns.

A similarity score closer to `1` indicates that two users have more similar rating patterns.

### 3. Find Similar Users

For a selected user, the system identifies other users with similar rating patterns.

### 4. Generate Recommendations

Ratings from similar users are weighted according to their similarity score:

```text
Weighted Score = Rating × Similarity
```

Books that the target user has not already rated are considered for recommendation.

### 5. Return Top Recommendations

The books are sorted according to their aggregated weighted scores, and the highest-ranked books are returned.

## 💻 Installation

Clone the repository:

```bash
git clone https://github.com/Vedline2547/Book-recommendation-system.git
```

Navigate into the project directory:

```bash
cd book-recommendation-system
```

Install the required libraries:

```bash
pip install pandas scikit-learn
```

## ▶️ Usage

Run the Python script:

```bash
python recommendation.py
```

The program creates the user-book matrix, calculates user similarities, and generates recommendations for the selected user.

You can change the target user:

```python
user_id = 4
```

You can also change the number of recommendations:

```python
recommended_books = recommend_books(
    user_id,
    user_similarity_df,
    user_book_matrix,
    top_n=3
)
```

## 📌 Example Output

```text
Dataset:
   user_id book_title  rating
0        1      Book A       5
1        1      Book B       3
2        1      Book C       4
...

User Similarity Matrix:
...

Books recommended for 4: [...]
```

## 🎯 Key Concepts Learned

* Recommendation Systems
* Collaborative Filtering
* User-Based Recommendation
* Cosine Similarity
* Pandas Pivot Tables
* Similarity Matrices
* Weighted Recommendations

## 🔮 Future Improvements

This project can be extended by:

* Using a larger real-world book-rating dataset
* Implementing **item-based collaborative filtering**
* Adding a web interface using **Flask**
* Building a recommendation API
* Adding user and book profiles
* Comparing cosine similarity with other similarity measures
* Implementing matrix factorization techniques such as **SVD**
* Deploying the recommendation system online

## 📄 License

This project is intended for educational and learning purposes.

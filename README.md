# RECOMMENDATION-SYSTEM

*COMPANY* : CODTECH IT SOLUTIONS

*NAME* : GHADIYARAM JAYA SAI SREE RAMA KUMAR

*INTERN ID* : CT06DM1188

*DOMAIN* : MACHINE LEARNING

*DURATION* : 6 WEEKS

*MENTOR* : NEELA SANTOSH

The Book Recommendation System developed in this project is based on a collaborative filtering technique using user ratings. It aims to recommend books similar to a selected one by analyzing rating patterns of various users. The dataset utilized in this project is sourced from GeeksforGeeks, comprising three CSV files: Users.csv, Books.csv, and Ratings.csv. These datasets include user metadata (like age and location), book details (such as title, author, and publisher), and user-book rating interactions.

To begin, the data is loaded using pandas and explored using the .info() function to understand its structure and ensure integrity. Redundant entries in the book dataset are removed using the drop_duplicates() method on the book title column to avoid skewed results due to repetition. The ratings data is then merged with the cleaned book dataset on the ISBN field, and unnecessary columns like image URLs and ISBNs are dropped. Following this, the merged data is again combined with the users dataset to include user-related details, although columns like age and location are later excluded for modeling relevance.

The dataset is then filtered for quality. Users who have rated more than 100 books are considered “knowledgeable users,” as their input is more statistically meaningful. Similarly, books that have received at least 50 ratings are considered “famous books” and retained for final modeling. This filtration ensures the model is trained on robust and relevant interactions, reducing noise caused by sparse data.

The core recommendation engine is powered by a user-item matrix created via a pivot table. In this matrix, rows represent book titles and columns represent users, with the values indicating the ratings. Since not every user has rated every book, missing values are common. These are filled with zeros to maintain matrix compatibility during the similarity calculation step. However, such direct zero imputation may affect the precision in some contexts, and this is an area where matrix factorization techniques could be explored in the future for improvement.

Before calculating similarities, the pivot table is standardized using StandardScaler from scikit-learn. This step ensures all rating values are on the same scale, removing biases caused by users who generally rate books higher or lower. Cosine similarity is then applied to the normalized pivot table to compute pairwise similarity between books. This technique effectively captures the angles between book-rating vectors rather than their absolute distances, making it particularly useful when dealing with sparse and high-dimensional data.

The recommendation function, recommend(book_name, similarity_score), takes a book title as input and returns the top 5 most similar books. It uses the similarity matrix to locate the index of the input book and fetches the next highest scores, omitting the first one since it would always be the book itself. Each recommendation includes the book’s title, author, and cover image URL, providing a complete and user-friendly output.

While the system works well, a few challenges were encountered. One issue was dealing with books that had very few ratings, which could introduce noise and misleading recommendations. This was mitigated through user and item filtering thresholds. Another challenge was handling missing values in the pivot table, which was addressed by filling them with zeros. Though this allowed for computational efficiency, it could be further improved with advanced imputation techniques like SVD or KNN imputation. Additionally, merging large datasets initially caused memory consumption issues, which were solved by filtering early and minimizing data columns.

In conclusion, the project successfully demonstrates how collaborative filtering can be implemented to recommend books based on user behavior. The system performs well on dense sections of the dataset and provides personalized, content-rich recommendations. With further enhancements like user-based collaborative filtering, matrix factorization, or hybrid modeling with content-based filters, the recommendation engine can be scaled and made more accurate for real-world deployment.

<img width="1111" height="480" alt="Image" src="https://github.com/user-attachments/assets/ce7cb05a-7b4a-453a-ae8e-63319f6801b4" />

<img width="531" height="442" alt="Image" src="https://github.com/user-attachments/assets/163a0e7a-0b4f-44d0-b3f5-5915ca9bb257" />

<img width="839" height="217" alt="Image" src="https://github.com/user-attachments/assets/61ec2254-48af-4882-9198-076aa308477e" />

<img width="398" height="141" alt="Image" src="https://github.com/user-attachments/assets/00922c69-8c06-453c-95f6-6577369e3590" />

<img width="1222" height="352" alt="Image" src="https://github.com/user-attachments/assets/b4fda81e-87fe-49af-8666-0225ee815e0f" />

<img width="613" height="290" alt="Image" src="https://github.com/user-attachments/assets/8bb76d30-2edf-4078-a95d-6d90244154b9" />

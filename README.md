# 📊 Assignment: Recommender Systems Dashboard (SVD Model)

## 🎯 Objective

Design and develop a **Frontend Dashboard** for a **Recommender System built using Collaborative Filtering (SVD)**.

The backend ML model is implemented using the `Surprise` library and performs:

* Dataset loading
* Train-test split
* Model training (SVD)
* Evaluation (RMSE, MAE)
* Top-N item recommendations for a selected user
* Interpretation labeling

Your task is to build a **complete interactive dashboard layout** that consumes backend API endpoints and visualizes the model outputs effectively.

---

# 🧠 Background: ML Model Summary

The backend performs the following:

1. Loads ratings dataset (`ratings.csv`)
2. Trains an SVD model
3. Evaluates model performance:

   * RMSE: 0.9279
   * MAE: 0.7885
4. Predicts ratings for each item for a selected user
5. Assigns interpretation labels:

   * ⭐⭐⭐⭐⭐ Highly Recommended (≥ 4.5)
   * ⭐⭐⭐⭐ Recommended (≥ 4.0)
   * ⭐⭐⭐ Moderate (≥ 3.0)
   * ⭐⭐ Not Recommended (< 3.0)

---

# 🏗️ Dashboard Layout Requirements

## 📌 Overall Wireframe

```
---------------------------------------------------------
| Recommender Systems Dashboard Title                  |
| Collaborative Filtering using SVD                    |
---------------------------------------------------------
| KPI Cards (RMSE | MAE | Total Users | Total Items)  |
---------------------------------------------------------
| Ratings Distribution | User Activity Distribution    |
---------------------------------------------------------
| User–Item Interaction Heatmap                        |
---------------------------------------------------------
| Select User Dropdown + Generate Button               |
---------------------------------------------------------
| Recommendation Table | Predicted Ratings Chart       |
---------------------------------------------------------
| Explanation & Interpretation Panel                   |
---------------------------------------------------------
```

---

# 🟢 Section 1: Dashboard Header

### Requirements:

* Title: **Recommender Systems Dashboard**
* Subtitle: **Collaborative Filtering using SVD**
* Display:

  * Model Name
  * Rating Scale (1–5)
  * Dataset name

---

# 🟢 Section 2: KPI Cards

### Display the following metrics:

| Metric      | Description            |
| ----------- | ---------------------- |
| RMSE        | Root Mean Square Error |
| MAE         | Mean Absolute Error    |
| Total Users | Unique User IDs        |
| Total Items | Unique Item IDs        |

### UI Requirements:

* 4 equal cards
* Large metric number
* Small descriptive text
* Icon for each card

---

# 🟢 Section 3: Ratings Distribution Chart

### Chart Type:

Bar Chart

### Data:

* X-axis → Rating values (1–5)
* Y-axis → Number of ratings

### Purpose:

Understand rating bias and data imbalance.

---

# 🟢 Section 4: User Activity Distribution

### Chart Type:

Histogram or Bar Chart

### Data:

* X-axis → Number of ratings per user
* Y-axis → Number of users

### Purpose:

Identify:

* Cold-start users
* Highly active users

---

# 🟢 Section 5: User–Item Interaction Heatmap

### Chart Type:

Heatmap

### Data:

* X-axis → Items
* Y-axis → Users
* Color → Rating value

### Purpose:

Visualize sparsity and collaborative structure.

---

# 🟢 Section 6: User Selection Panel

### Components:

* Dropdown (User ID list)
* "Generate Recommendations" Button

### Behavior:

* On selection, fetch recommendations via API
* Update table and charts dynamically

---

# 🟢 Section 7: Top-N Recommendations

## 🟦 Left Panel: Recommendation Table

### Columns:

| Item ID | Predicted Rating | Interpretation | Stars | Rank |

### Features:

* Sortable table
* Color-coded rows:

  * Green → Highly Recommended
  * Blue → Recommended
  * Orange → Moderate
  * Red → Not Recommended

---

## 🟦 Right Panel: Predicted Ratings Chart

### Chart Type:

Horizontal Bar Chart

### Data:

* Y-axis → Item ID
* X-axis → Predicted Rating
* Color based on interpretation label

---

# 🟢 Section 8: Explanation Panel

### Display:

* Selected Item
* Predicted Rating
* Interpretation Label
* Explanation Text

### Example Explanation:

```
Item 106 is recommended because:

• Similar users rated it highly
• SVD captured latent factors between users and items
• Predicted rating: 4.28
• Category: Recommended ⭐⭐⭐⭐
```

---

# 🔗 Backend API Endpoints to Use

Base URL:

```
/api/v1/
```

---

## Model Endpoints

* GET `/model/info`
* GET `/model/metrics`
* POST `/model/retrain` (optional)

---

## Dataset Endpoints

* GET `/dataset/summary`
* GET `/users`
* GET `/items`

---

## Analytics Endpoints

* GET `/analytics/ratings-distribution`
* GET `/analytics/user-activity`
* GET `/analytics/item-popularity`
* GET `/analytics/interaction-matrix`
* GET `/analytics/cold-start-users`

---

## Recommendation Endpoints

* GET `/recommendations/{user_id}?top_n=5`
* GET `/recommendations/{user_id}/explanation/{item_id}`
* GET `/predict?user_id=1&item_id=106`

---

# 🛠️ Technology Requirements

You must use:

* HTML5
* CSS3
* Bootstrap 5
* JavaScript
* Chart.js (or equivalent)
* Fetch API for backend communication

---

# 📁 Project Structure (Suggested)

```
recommender-dashboard/
│
├── index.html
├── css/
│   └── styles.css
├── js/
│   ├── api.js
│   ├── charts.js
│   └── main.js
└── README.md
```

---

# 🎓 Academic Expectations

Students must:

* Follow clean UI layout
* Use proper Bootstrap grid system
* Implement dynamic API calls
* Handle loading states
* Handle empty or cold-start users
* Use proper chart labeling and legends
* Maintain clean code structure

---

# 📝 Submission Requirements

1. Complete frontend source code
2. Screenshots of:

   * KPI section
   * Charts
   * Heatmap
   * Recommendation output
3. Short report (2–3 pages) including:

   * Dashboard design explanation
   * API integration explanation
   * Challenges faced
   * Future improvements

---

# ⭐ Bonus (Optional Enhancements)

* Add model comparison (SVD vs KNN)
* Add recommendation confidence score
* Add filtering (Top 5, Top 10)
* Add dark mode
* Add animation effects

---

# 📊 Evaluation Criteria

| Criteria                     | Marks |
| ---------------------------- | ----- |
| Layout Design                | 20    |
| Chart Visualization          | 20    |
| API Integration              | 20    |
| Code Structure               | 20    |
| Explanation & Interpretation | 10    |
| Innovation                   | 10    |

---

# 🚀 Final Goal

By completing this assignment, students should:

* Understand how ML models connect to dashboards
* Learn frontend–backend integration
* Visualize recommender system outputs
* Interpret model evaluation metrics
* Build production-style ML dashboards

---

**End of Assignment**

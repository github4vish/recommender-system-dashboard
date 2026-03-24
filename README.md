

---

# 📊 Recommender System Dashboard – Simple 6 Steps Guide

---

## ✅ Step 1: Understand File Structure (Diagram + Purpose)

### 📁 Project Structure

```
recommender-dashboard/
│
├── index.html
├── css/
│   └── styles.css
├── js/
│   └── dashboard.js
│
├── models/
│       model.pkl
│
├── training/
│       train_model.py
│       notebook.ipynb
│
└── app.py
```

### 📌 Purpose of Each File

| File/Folder        | Purpose                           |
| ------------------ | --------------------------------- |
| **index.html**     | Main dashboard UI                 |
| **styles.css**     | Styling and layout design         |
| **dashboard.js**   | Handles API calls and updates UI  |
| **models/**        | Stores trained ML model           |
| **train_model.py** | Converts notebook into model file |
| **notebook.ipynb** | Used for training SVD model       |
| **app.py**         | Backend API server                |

---

## ✅ Step 2: Design Dashboard (index.html Structure)

Use:

* Bootstrap 5 (layout)
* DC.js + D3.js + Crossfilter2 (charts)

### 📊 Dashboard Layout Diagram

```
---------------------------------------------------------
📊 Recommender Systems Dashboard
---------------------------------------------------------
Header:
- Title + Subtitle (SVD Model Info)
---------------------------------------------------------
KPI Cards Row:
[ RMSE ] [ MAE ] [ Total Users ] [ Total Items ]
---------------------------------------------------------
Charts Row:
[ Ratings Distribution ] [ User Activity ]
---------------------------------------------------------
Heatmap Section:
[ User–Item Interaction Heatmap ]
---------------------------------------------------------
User Selection:
[ Dropdown ] [ Generate Button ]
---------------------------------------------------------
Recommendations Section:
[ Table ] [ Predicted Ratings Chart ]
---------------------------------------------------------
Bottom Section:
[ Explanation Panel ]
---------------------------------------------------------
```

### 🎯 Goal

* Create a clean structured dashboard
* Use Bootstrap grid
* Reserve chart areas for DC.js

---

## ✅ Step 3: Create Model Training Script

### 📌 Task

Create **train_model.py** using the `.ipynb` file.

### 🎯 Purpose

* Train SVD recommender model
* Load dataset (ratings)
* Evaluate model (RMSE, MAE)

---

## ✅ Step 4: Generate Model File

### 📌 Task

Run the training script.

### 🎯 Output

* Save trained model into:

```
/models/model.pkl
```

* This model will be used by backend APIs

---

## ✅ Step 5: Create Backend API (app.py)

### 📌 API Design (Names + Routes + Purpose)

| API Name             | Route                                                     | Purpose                |
| -------------------- | --------------------------------------------------------- | ---------------------- |
| Model Info           | `/api/v1/model/info`                                      | Show model details     |
| Model Metrics        | `/api/v1/model/metrics`                                   | RMSE, MAE              |
| Dataset Summary      | `/api/v1/dataset/summary`                                 | Users & items count    |
| Users List           | `/api/v1/users`                                           | Get all users          |
| Items List           | `/api/v1/items`                                           | Get all items          |
| Ratings Distribution | `/api/v1/analytics/ratings-distribution`                  | Chart data             |
| User Activity        | `/api/v1/analytics/user-activity`                         | Activity data          |
| Interaction Matrix   | `/api/v1/analytics/interaction-matrix`                    | Heatmap data           |
| Recommendations      | `/api/v1/recommendations/{user_id}`                       | Top-N items            |
| Prediction           | `/api/v1/predict`                                         | Predict rating         |
| Explanation          | `/api/v1/recommendations/{user_id}/explanation/{item_id}` | Explain recommendation |

### 🎯 Goal

* Connect dashboard with ML model
* Return structured JSON data

---

## ✅ Step 6: Create dashboard.js (Frontend Logic)

### 📌 Responsibilities

dashboard.js connects **index.html ↔ app.py**

### 🔧 Tasks

1. On page load:

   * Fetch model metrics (RMSE, MAE)
   * Fetch dataset summary
   * Load charts (DC.js)

2. User Selection:

   * Get user ID from dropdown
   * Request recommendations

3. Display Results:

   * Update recommendation table
   * Update predicted ratings chart
   * Show explanation panel

4. Render Charts:

   * Ratings Distribution
   * User Activity
   * Heatmap

5. Handle:

   * Loading states
   * Errors
   * Dynamic updates

---

## 🎯 Final Flow

```
User → index.html (Dashboard UI)
        ↓
dashboard.js (Frontend Logic)
        ↓
app.py (API Backend)
        ↓
SVD Model (Prediction)
        ↓
Response → Dashboard Visualization
```

---



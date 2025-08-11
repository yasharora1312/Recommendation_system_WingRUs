### Wings R Us – Customer Data Analysis & Recommendation System
## 📌 Overview
This project processes raw order & customer data from Wings R Us, performs data cleaning, transformation, and exploratory analysis, and builds an advanced recommendation engine to suggest menu items to customers based on their past behavior, current cart, and global purchasing patterns.

## The project is split into two main stages:

# Data Processing & Analysis

    .Cleans and transforms raw JSON order data into structured format.
    .Detects and corrects pricing outliers.
    .Generates customer segmentation & behavior insights.
    .Produces a hackathon-ready dataset for modeling.

# Recommendation System 

Implements multiple recommendation techniques:

# Market Basket Analysis (MBA) with association rules.
    .Popularity-based recommendations.
    .Customer segmentation-based suggestions.
    .Sequential purchase pattern mining.
    .Collaborative filtering (Matrix Factorization).
    .Category-based rules.

    >Builds an ensemble recommender combining all techniques.
    >Tests recall@3 performance against MBA baseline.
    >Adds context-aware, hierarchical, and customer journey–based enhancements.
    >Includes an optimized ultimate recommender with customizable weights.

## 📂 Project Structure

     .
    ├── wwt4.py                # Data processing, cleaning, transformation, and EDA
    ├── wwt5.py                # Recommendation system and performance evaluation
    ├── hackathon_ready_dataset.csv   # Cleaned dataset output from wwt4.py
    ├── requirements.txt       # Project dependencies
    └── README.md              # Project documentation
## ⚙️ Installation
# Clone the repository

    git clone https://github.com/yourusername/wings-r-us-recommender.git
    cd wings-r-us-recommender
    Install dependencies

pip install -r requirements.txt

## 📊 Data Processing Workflow 
    1.Load raw data from CSV in chunks for memory efficiency.
    2.Transform ORDERS JSON into item1–item6 with corresponding prices.
    3.Calculate average order value per order.
    4.Detect & correct price outliers using IQR and rule-based fixes.
    5.Perform customer segmentation (One-time, Occasional, Regular, Loyal).
    6.Basket analysis (size, category distribution, combination patterns).
    7.Save cleaned dataset to hackathon_ready_dataset.csv.

## 🤖 Recommendation System Workflow (wwt5.py)
# 1.Market Basket Analysis (MBA)
     .Generate frequent itemsets and association rules.
     .Recommend based on confidence × lift scores.

# 2.Popularity Fallback
    .Recommend globally popular items when rules have low coverage.

# 3.Advanced Models
    .Customer Segment Recommendations – Suggest popular items within similar customer groups.
    .Sequential Pattern Mining – Recommend items based on order history sequences.
    .Collaborative Filtering (NMF) – Predict based on customer-item interactions.
    .Category Rules – Suggest complementary categories.
# 4.Ensemble Model
    .Combines all above approaches with weighted scoring.
    .Evaluates Recall@3 vs MBA baseline.

# 5.Enhanced Recommendation
    .Context-Aware – Adjust recommendations based on time, day, and order channel.
    .Hierarchical – Cross-category suggestions.
    .Journey-Based – Personalized based on a customer’s historical path.
    .Optimized Weights – Tune component importance.

## 🏆 Example Use

# Example: Run recommender for a test cart
cart = ["10 pc Spicy Wings"]
recs = wings_r_us_recommender(cart, rules, popular_items)
print("Recommendations:", recs)

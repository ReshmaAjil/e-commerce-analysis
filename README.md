# e-commerce-analysis
Machine learning project analyzing e-commerce product value using engineered trust-weighted metrics and Random Forest regression with cross-validation
E-Commerce Product Value Analysis using Machine Learning
📌 Project Overview

In this project, I built a value-based product analysis system for an e-commerce dataset.
The goal was to identify which products offer the best value for money by considering price, discounts, customer ratings, and review volume.

Instead of focusing only on ratings or discounts, this project combines multiple signals to create a composite value score and evaluates machine learning models to understand product value drivers.

🎯 Business Objective

Identify high-value products within each category

Understand how price, discounts, ratings, and reviews influence perceived value

Build a robust model suitable for small datasets

Translate model outputs into business insights

🧠 Problem Framing

This problem was framed as a regression task where the target represents a weighted value score for each product.

Target Variable:
rating_per_price_wtd_normd


This value score was engineered to reflect:

Higher ratings

Greater number of reviews (confidence)

Lower effective price (after discount)

🛠 Feature Engineering

Key features used:

price

discount_percent

discounted_price

rating

num_reviews

Engineered Metrics:

Rating per price

Weighted rating per price

Normalized value score (for model stability)

📈 Models Used
1️⃣ Linear Regression (Baseline)

Used as a simple baseline

Helped test linear assumptions

Result:

High error

Strongly negative R²

Indicated non-linear relationships

2️⃣ Random Forest Regressor

Chosen to capture non-linear interactions

Handles small datasets better than linear models

Initial Result (single split):

Lower RMSE than linear regression

R² still unstable due to small data size

3️⃣ Random Forest with Cross-Validation (Final Model)

Used 5-fold cross-validation

Evaluated using RMSE

Final Performance:

Cross-Validated RMSE ≈ 0.26


This provided a stable and reliable estimate of model performance.

📊 Evaluation Strategy

RMSE was used as the primary metric

R² was intentionally not used in final evaluation because:

The target variable was engineered from the same features

R² becomes misleading for deterministic targets and small datasets

This choice reflects methodological correctness, not model weakness.

🔍 Key Insights

Products with moderate prices and strong review volume offer better value than heavily discounted high-priced items

Discounts alone do not guarantee high value

Customer trust (reviews) is a stronger value signal than price cuts

⚠️ Limitations

Small dataset

No sales or revenue data

No user behavior or time-based trends

Value score is engineered, not directly observed


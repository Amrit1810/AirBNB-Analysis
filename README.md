# Airbnb Marketing Analytics Project

**Author:** Amritpal Singh
**Topic:** Marketing Analytics

---

## Overview

This project presents a comprehensive marketing analysis of Airbnb, the platform founded in 2008 that revolutionized the hospitality industry. By leveraging advanced technology and data analysis, this project aims to generate actionable insights and strategies for Airbnb.

We analyze Airbnb's market position, customer demographics, trends, and competitor performance to develop valuable marketing strategies. Utilizing machine learning models, the project focuses on:

1.  **Price Prediction:** Optimizing listing prices for hosts.
2.  **Customer Sentiment Analysis:** Understanding guest feedback to enhance satisfaction.
3.  **Listing Clustering:** Segmenting properties for targeted marketing.

The ultimate goal is to enable better decision-making for hosts and users, improve business growth, enhance the customer experience, and ultimately strengthen Airbnb's overall platform and market position. Data cleaning, preprocessing, feature engineering, and exploratory data analysis (EDA) were performed as foundational steps.

---

## Competitor Comparison

To understand Airbnb's market standing, a comparison with key competitors was conducted:

| Platform      | Countries Covered | Hosts (Listings) | Users (Annual) | Unique Features                                       | Target Market                              | Revenue (Annual) |
| :------------ | :---------------- | :--------------- | :------------- | :---------------------------------------------------- | :----------------------------------------- | :--------------- |
| **Airbnb**    | 220+              | 7 million+       | 150 million+   | Diverse accommodations, local experiences, longer stays | Leisure, business, unique experience seekers | $8.4 billion+    |
| Booking.com   | 200+              | 28 million+      | 500 million+   | Hotels, resorts, flights, large-scale bookings        | Tourists, business travelers, hotel seekers | $17 billion+     |
| Vrbo          | 190+              | 2 million+       | 15 million+    | Vacation rentals, family-centric, large properties      | Families, large groups, vacationers      | $3.5 billion+    |
| Expedia       | 70+               | 15 million+      | 70 million+    | Flight & hotel bundles, vacation packages           | Mainstream travelers, package seekers    | $10.5 billion+   |

*Key Takeaway:* While Booking.com leads in user volume and revenue (broader hotel/flight scope), Airbnb excels in global reach (countries) and unique, diverse accommodation offerings, targeting experience seekers. Vrbo focuses on family/group vacation rentals, and Expedia focuses on travel packages.

---

## SWOT Analysis

A SWOT analysis was performed to assess Airbnb's internal capabilities and external environment:

**Strengths:**
*   Vast global reach (220+ countries, 7M+ listings).
*   Diverse accommodations and unique local experiences.
*   Strong brand recognition and a loyal user base.
*   Scalable platform catering to both leisure and business travel.

**Weaknesses:**
*   Regulatory challenges and hurdles in multiple cities.
*   Dependence on hosts for consistent quality control.
*   Potential for inconsistent customer service experiences.
*   Safety concerns and associated reputation risks.

**Opportunities:**
*   Expansion into emerging markets (e.g., Asia, Africa).
*   Growth potential in business travel and remote work segments.
*   Strategic partnerships with local businesses and service providers.
*   Increased focus on sustainability and eco-friendly travel options.

**Threats:**
*   Intense competition from platforms like Booking.com, Vrbo, and Expedia.
*   Economic downturns negatively impacting travel demand.
*   Negative public perception regarding housing shortages and affordability issues.
*   Increasing regulatory restrictions and compliance costs.

---

## Data Analysis & Models

To extract meaningful insights, three core machine learning models were developed after thorough data cleaning, preprocessing, feature engineering, and EDA:

1.  **Clustering Model:** Groups similar listings based on features like price, location, and amenities.
    *   *Goal:* Enable targeted marketing strategies and market segmentation.
2.  **Price Prediction Model:** Predicts optimal listing prices.
    *   *Goal:* Help hosts maximize earnings and remain competitive.
3.  **Sentiment Analysis Model:** Analyzes guest reviews to categorize sentiment (positive/negative/neutral).
    *   *Goal:* Help hosts improve guest satisfaction and manage reputation.

---

## Clustering Model

### Model Development (Slide 6)
A clustering model (likely K-Means, based on Elbow/Silhouette analysis) was developed to group properties into distinct segments based on features like price, location, amenities, and guest ratings. Analysis using the Elbow Method and Silhouette Scores suggested an optimal number of clusters (visuals point towards K=4 being a good candidate explored further). Principal Component Analysis (PCA) was used for visualizing the clusters in 2D space.

### Cluster Profiles
Based on the analysis (assuming K=4 was chosen), the clusters exhibited distinct characteristics:

*   **Cluster 0:** Mid-range price (~$206), moderate availability (~282 days), good reviews (~28), moderate host listings (~16.3%).
*   **Cluster 1:** Highest price (~$251), highest availability (~296 days), good reviews (~22), highest host listings (~34.8%).
*   **Cluster 2:** Lower-mid price (~$114), lowest availability (~56 days), highest reviews (~31), significant host listings (~26.1%).
*   **Cluster 3:** Lowest price (~$90), low availability (~57 days), good reviews (~24), moderate host listings (~22.9%).
    *(Note: Availability/Minimum Nights data interpretation from charts might need refinement based on exact axis labels/context).*

### Marketing Insights & Strategies

| Stakeholder        | Cluster 0 (Mid-Range/Moderate)                     | Cluster 1 (High-Price/High-Avail)                    | Cluster 2 (Budget/Active Hosts)                        | Cluster 3 (Economical/High-Avail - *Revisit chart data*) |
| :----------------- | :------------------------------------------------- | :--------------------------------------------------- | :----------------------------------------------------- | :------------------------------------------------------- |
| **Existing Hosts** | Emphasize value, optimize amenities for comfort.   | Focus on luxury, personalization, justify premium price. | Highlight affordability & high satisfaction, maintain service. | Offer flexibility/discounts, promote affordability.      |
| **Potential Guests** | Target value/comfort seekers for longer stays.     | Target extended stay, "home away from home" seekers. | Target budget-conscious, value seekers (highlight reviews). | Target last-minute, low-cost extended stay seekers.    |
| **New Hosts**      | Target mid-range travelers, focus on service/reviews. | Focus on quality/premium amenities for high-end guests. | Focus on budget travelers, build reputation via service. | Target budget travelers/students, offer reliable, low-cost options. |

---

## Price Prediction Model

### Model Development & Performance
Several regression models were trained and evaluated to predict listing prices.

| Model              | MSE           | MAE         | RMSE        | R-squared |
| :----------------- | :------------ | :---------- | :---------- | :-------- |
| Linear Regression  | 3996.62       | 47.69       | 63.22       | 0.6133    |
| Decision Tree      | 3435.46       | 42.12       | 58.61       | 0.6676    |
| Random Forest      | 2435.36       | 34.10       | 49.35       | 0.7643    |
| **XGBoost**        | **2395.02**   | **33.74**   | **48.94**   | **0.7682**|

**Conclusion:** XGBoost emerged as the best-performing model, explaining approximately 77% of the variance in price, demonstrating high accuracy and strong predictive power. Random Forest was a close second.

### Marketing Insights & Strategies

*   **Existing Hosts:**
    *   Use the model for *dynamic pricing* (adjust based on trends, events).
    *   Perform *competitive analysis* against similar listings.
    *   Achieve *revenue maximization* by avoiding under/overpricing.
*   **Potential Guests:**
    *   *Compare prices* to ensure fair deals.
    *   *Plan budgets* by understanding expected price ranges.
    *   *Identify potentially overpriced listings* and negotiate or seek alternatives.
*   **New Hosts:**
    *   Get *initial pricing guidance* to set competitive rates.
    *   *Avoid common pitfalls* of underpricing (lost revenue) or overpricing (fewer bookings).
    *   *Optimize for occupancy* by understanding seasonal/demand-based pricing.

### Key Price Drivers & Temporal Insights

*   **Reviews (Slide 13):** Cleanliness shows a notable positive correlation with price. Location has the strongest correlation among review metrics.
    *   *Hosts:* Prioritize cleanliness.
    *   *Guests:* Expect to pay more for prime locations.
    *   *New Hosts:* Understand your location's impact on pricing potential.
*   **Capacity (Slide 14):** Price clearly scales with the number of guests a listing accommodates.
    *   *Hosts:* Consider investments (e.g., sofa beds) to increase capacity if feasible.
    *   *Guests:* Budget for higher prices when traveling in larger groups.
    *   *New Hosts:* Benchmark pricing accurately against listings with similar capacity.
*   **Time & Seasonality (Slide 15):** Prices tend to be highest in Fall and Summer. Mid-week (Tue/Wed) often shows slightly lower prices than weekends. May and potentially December (within Fall/Winter) show peaks.
    *   *Hosts:* Optimize pricing and availability for peak seasons/months.
    *   *Guests:* Look for savings during Spring or mid-week travel.
    *   *New Hosts:* Use seasonal/weekly trends for initial pricing strategy and anticipate demand fluctuations.

---

## Sentiment Analysis Model

### Model Development & Performance
Various models were evaluated for classifying the sentiment of guest reviews.

| Model                   | Accuracy | Avg Precision | Avg Recall | Avg F1-Score |
| :---------------------- | :------- | :------------ | :--------- | :----------- |
| Logistic Regression     | 0.8753   | 0.8785        | 0.8755     | 0.8766       |
| Random Forest           | 0.8831   | 0.8836        | 0.8837     | 0.8834       |
| Naive Bayes             | 0.8246   | 0.8252        | 0.8268     | 0.8251       |
| Support Vector Machine  | 0.8737   | 0.8758        | 0.8742     | 0.8749       |
| **BERT**                | **0.9242** | **0.9256**    | **0.9242** | **0.9242**   |

**Conclusion:** The deep learning-based BERT model significantly outperformed traditional models, achieving the highest accuracy (92.42%) and demonstrating superior performance across all metrics for sentiment classification.

### Marketing Insights & Strategies

*   **New Hosts:** Gather actionable insights from early reviews to quickly understand guest reception and make improvements.
*   **Potential Guests:** Evaluate the general tone of reviews for a listing to gauge past guest experiences and alignment with expectations.
*   **Existing Hosts:** Gain valuable, automated insights into feedback, identify key areas for improvement (or areas of excellence), enhance guest satisfaction, and maintain competitiveness.

### Key Sentiment Themes

*   **Positive Reviews (Word Cloud):** Dominated by terms like `great`, `place`, `host`, `location`, `clean`, `stay`, `recommend`, `walking distance`, `comfortable`, `easy`.
    *   *Key Takeaway:* Guests highly value location, cleanliness, host responsiveness, and overall comfort/convenience.
*   **Negative Reviews (Word Cloud):** Prominent terms include `not`, `clean`, `host`, `no`, `stay`, `airbnb`, `problem`, `working`, `recommend`, `told`, `paper`, `toilet`, `bed`, `hot water`, `air conditioning`.
    *   *Key Takeaway:* Negative feedback frequently revolves around unmet expectations regarding cleanliness, basic amenities (toilet paper, hot water), maintenance issues (not working), and host communication/responsiveness.

---

## Project Summary & Recommendations

This project provided a comprehensive analysis of Airbnb's operations through:
*   **Market Assessment:** SWOT analysis and competitor benchmarking identified Airbnb's strategic position, growth opportunities (emerging markets, business travel), and key challenges (regulation, competition).
*   **Machine Learning Insights:**
    *   **Clustering:** Revealed distinct market segments for targeted strategies.
    *   **Price Prediction:** Developed a highly accurate model (XGBoost R²=0.77) to optimize pricing based on features, seasonality, and demand.
    *   **Sentiment Analysis:** Built a state-of-the-art model (BERT Acc=92.4%) to understand guest feedback drivers.

**Recommendations for Airbnb:**
Leverage these insights and models to create a suite of data-driven tools for stakeholders:
*   **For Hosts:** Offer a dynamic pricing optimization tool and a sentiment feedback dashboard to refine offerings and manage reputation effectively.
*   **For Guests:** Provide sentiment analysis-powered property evaluations to highlight listings with high guest satisfaction, aiding informed decisions.
*   **For New Hosts:** Deliver onboarding tools incorporating clustering and pricing insights to guide setup for appeal and profitability.

**Overall Impact:** Offering these tools will enhance market segmentation, differentiate Airbnb from competitors, drive higher revenue, expand market share, and ultimately strengthen Airbnb's position by increasing profitability and growth potential.

---

## Technologies Used (Inferred)

*   **Language:** Python
*   **Libraries:**
    *   Data Manipulation: Pandas, NumPy
    *   Machine Learning: Scikit-learn (Linear Regression, Decision Tree, Random Forest, K-Means, SVM, Naive Bayes), XGBoost
    *   Deep Learning (Sentiment): Transformers (Hugging Face for BERT), PyTorch/TensorFlow
    *   Visualization: Matplotlib, Seaborn
    *   NLP (Preprocessing): NLTK, spaCy (potentially)

---

## Project Structure (Example - Please Adapt)

# Customer Review Analysis Project

This project analyzes Amazon customer reviews using natural language processing to uncover insights into consumer behavior and product performance.

## Objectives
- **Explore Consumer Trends**: Identify key factors (quality, design, price, service) influencing purchases.
- **Understand Customer Behavior**: Highlight product strengths and weaknesses to propose improvements.

![image](https://github.com/user-attachments/assets/163a7bae-cc90-47ff-83b2-e52e8f63bb3b)

## Data Processing
- **Source**: Raw Amazon review data.
- **Steps**:
  - Removed duplicates and handled missing values.
  - Created three datasets:
    - `normalized_data.csv`: 10,000 rows, 21 columns (product details).
    - `seller.csv`: 31,579 rows, 3 columns (seller info).
    - `customer_review.csv`: 29,530 rows, 7 columns (review details).
- **Storage**: Data dictionary managed on Datahub.

## Data Modeling
- **Structure**: Star schema with `normalized_data` as the central table, linked via `uniq_id`.

   ![image](https://github.com/user-attachments/assets/c1ef7bb2-b834-4580-9688-e5c457b1d170)
  
## Exploratory Data Analysis (EDA)
- **Correlation Heatmap**:

  ![image](https://github.com/user-attachments/assets/3416efc4-7945-463b-9390-cb99f8a98283)

- **Customer Interaction**:
  - Retention rate: 89%.
  - Question engagement: 92.35%.
  - Avg. reviews/product: 9; avg. answered questions: 2.

- **Inventory & Pricing**:
  - In-stock rate: 75%.
  - Avg. stock/product: ~6 units.
  - Category 4 products are the most expensive.

  ![image](https://github.com/user-attachments/assets/f981dcfe-4890-4425-b053-f96878aec955)


- **Sellers**:
  - Avg. seller count/product: 4.
  - Exclusive sellers dominate; products with 10 sellers are notable (moderate competition).
  
  ![image](https://github.com/user-attachments/assets/c1410fc2-b371-4d39-a4aa-4dafab3071cd)
  ![image](https://github.com/user-attachments/assets/0f5c5bac-13a6-4f63-8e2f-f0f6bbc2c3a6)


    - The vast majority of transactions show a small negative difference (seller_price just below price), with the bulk clustered between about –20% and 0%. 
    - A sharp peak near 0% indicates most sellers list very close to the “price” value. 
    - A long, heavy left tail (down to –50,000%!) reveals extreme outliers—likely data errors or exceptional discounts. 
    - The strong skew suggests you’ll want to cap or trim those outliers before any downstream analysis or modeling. 
    - Overall, sellers tend to undercut the listed price slightly, but only a handful of points drive most of the variability.

- **Reviews**:

  ![image](https://github.com/user-attachments/assets/2fe93078-2611-491f-942d-62e4c725f018)
  ![image](https://github.com/user-attachments/assets/ee4138e7-c460-4599-92aa-f0e47b203d69)

  
  - Mostly 5-star (avg. rating: 4.71), stable at 4.3–5.0 (2001–2025), peaking in 2002, dipping in 2006.
  
- **Product Insights**:
  - Avg. price: $32.
  - Stock Availability 75.0%
  - Average Review Rating 4.71.
  - Popular products: Toys (puzzles, Lego, dominoes), often gifts for kids.

  ![image](https://github.com/user-attachments/assets/45aa027a-ddd4-4963-a070-53a125aeab31)

  ![image](https://github.com/user-attachments/assets/82d441dd-df84-4adc-989c-65ddc1375611)
  
  ![image](https://github.com/user-attachments/assets/ab4add98-d094-49d3-9639-e32d76a051cd)


- **Word Cloud**:

  ![image](https://github.com/user-attachments/assets/1690d610-9bc2-4daf-9a5a-0ac993d73b69)

  - Positive terms: good, great, well-made, quality, durable, excellent, fun, easy, value, good-value, recommend, would-recommend, lovely, sturdy.
  - Negative terms: (very few in titles) not, small-enough, would-not-recommend
  - Themes: Age Suitability, Gift Occasions, Play & Creativity, Value & Affordability, Quality & Durability, Easy of Use, Educational/Developmental, Packaging & Delivery
## Review Analysis
- **Methodology**:
  - Classified reviews: ≥3 stars (positive), <3 stars (negative).
  - Used BERTopic with CountVectorizer (stopword removal) for topic extraction.
  ![image](https://github.com/user-attachments/assets/f326fab7-9c8a-441b-bead-126a53648c7d)

- **Positive Reviews** (5 topics):
  - High satisfaction with quality, ease of use, and kid-friendliness.
  - Toys promote creativity/outdoor play; fast delivery, fair pricing praised.
  - Niche products (e.g., cosplay swords, Beyblades) get detailed, enthusiastic feedback.
- **Negative Reviews** (4 topics):
  - Complaints: Products smaller than expected, misleading images.
  - Compatibility issues (e.g., new Thomas trains not fitting old tracks).
  - Expensive electronics (e.g., Furby) often fail, causing disappointment.
  - Description errors (color, version) impact trust, especially for gifts.

## Tools & Visualizations
- **Power BI**: Interactive dashboards.
- **ChatGPT**: Keyword-based conclusions.
- **Visuals**: Data models, word clouds, rating distributions, seller competition charts.

## Conclusions
- **Positive Aspects**:
  - Parents value toys fostering parent-child interaction and creativity.
  - High-quality products (e.g., beads, costumes) and fast delivery enhance satisfaction.
  - Simple accessories (e.g., chargers) praised, but battery quality needs improvement.
- **Negative Aspects**:
  - Misleading sizes/descriptions erode trust.
  - Compatibility/functionality issues with electronics lead to poor experiences.

Explore the repository for detailed code and visualizations!

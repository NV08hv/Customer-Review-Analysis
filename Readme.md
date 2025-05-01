# Customer Review Analysis Project

This project analyzes Amazon customer reviews using natural language processing to uncover insights into consumer behavior and product performance.

## Objectives
- **Explore Consumer Trends**: Identify key factors (quality, design, price, service) influencing purchases.
- **Understand Customer Behavior**: Highlight product strengths and weaknesses to propose improvements.
![alt text](image-11.png)
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

   ![alt text](image.png)

## Exploratory Data Analysis (EDA)
- **Correlation Heatmap**:

  ![alt text](image-12.png)
- **Customer Interaction**:
  - Retention rate: 89%.
  - Question engagement: 92.35%.
  - Avg. reviews/product: 9; avg. answered questions: 2.

  ![alt text](image-1.png)
- **Inventory & Pricing**:
  - In-stock rate: 75%.
  - Avg. stock/product: ~6 units.
  - Category 4 products are the most expensive.

  ![alt text](image-2.png)
  ![alt text](image-3.png)

    - Most products cluster at lower price points (under $200) with widely varying stock levels. \
    - There’s a slight downward trend: higher-priced items tend to have fewer units in stock. \
    - A handful of expensive outliers (up to $8,000) sit near zero stock, reinforcing the negative slope.\
    - The broad confidence band reflects high variability—price alone isn’t a strong predictor of stock levels. \
    - Inventory management might prioritize low-cost, high-stock items for turnover. 

- **Sellers**:
  - Avg. seller count/product: 4.
  - Exclusive sellers dominate; products with 10 sellers are notable (moderate competition).

  ![alt text](image-4.png) \
  ![alt text](image-13.png) \

    - The vast majority of transactions show a small negative difference (seller_price just below price), with the bulk clustered between about –20% and 0%. \
    - A sharp peak near 0% indicates most sellers list very close to the “price” value. \
    - A long, heavy left tail (down to –50,000%!) reveals extreme outliers—likely data errors or exceptional discounts. \
    - The strong skew suggests you’ll want to cap or trim those outliers before any downstream analysis or modeling. \
    - Overall, sellers tend to undercut the listed price slightly, but only a handful of points drive most of the variability.

- **Reviews**:

  ![alt text](image-5.png)

  - Mostly 5-star (avg. rating: 4.71), stable at 4.3–5.0 (2001–2025), peaking in 2002, dipping in 2006.
- **Product Insights**:
  - Avg. price: $32.
  - Stock Availability 75.0%
  - Average Review Rating 4.71.
  - 
  - Popular products: Toys (puzzles, Lego, dominoes), often gifts for kids.

  ![alt text](image-6.png)
  ![alt text](image-7.png)
  ![alt text](image-8.png)
- **Word Cloud**:

  ![alt text](image-9.png)
  - Positive terms: good, great, well-made, quality, durable, excellent, fun, easy, value, good-value, recommend, would-recommend, lovely, sturdy.
  - Negative terms: (very few in titles) not, small-enough, would-not-recommend
  - Themes: Age Suitability, Gift Occasions, Play & Creativity, Value & Affordability, Quality & Durability, Easy of Use, Educational/Developmental, Packaging & Delivery
## Review Analysis
- **Methodology**:
  - Classified reviews: ≥3 stars (positive), <3 stars (negative).
  - Used BERTopic with CountVectorizer (stopword removal) for topic extraction.
  ![alt text](image-10.png)
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

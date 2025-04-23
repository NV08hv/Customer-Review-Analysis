# Customer Review Analysis

## Project Overview
The **Customer Review Analysis** project focuses on extracting and analyzing customer review data from Amazon's website to uncover insights into shopping experiences and product feedback. By leveraging Natural Language Processing (NLP) techniques, the project aims to:
- **Identify consumer trends**: Analyze review content to highlight key factors such as quality, design, pricing, and customer service.
- **Understand customer behavior**: Pinpoint product strengths and weaknesses from real consumer perspectives, providing actionable improvement suggestions.

## Data Processing
### Raw Data Source
- **Duplicate Removal**: Identified and removed duplicate data entries.
- **Missing Data Handling**: Imputed or processed missing values individually per row.
- **Output Files**: Generated three structured datasets with dictionaries:
  - `normalized_data.csv`: 10,000 rows, 21 columns.
  - `seller.csv`: 31,579 rows, 3 columns.
  - `customer_review.csv`: 29,530 rows, 7 columns.
- **Data Dictionary**: Managed and stored on Datahub for reference.

## Data Modeling
The datasets are designed using a **star schema** model:
- **Central Table**: `normalized_data` (primary key: `uniq_id`), containing detailed product information.
- **Relationships**:
  - `normalized_data` (1) → (n) `seller`: One product can have multiple sellers.
  - `normalized_data` (1) → (n) `customer_review`: One product can have multiple customer reviews.

## Exploratory Data Analysis (EDA)
### 1. Customer Interaction and Behavior
- **Observation**: Customers are significantly more likely to purchase additional products after buying one, indicating strong cross-selling opportunities.
- **Insight**: Customers tend to compare and explore related products before making additional purchases.

### 2. Inventory and Pricing
- **In-Stock Rate**: 75% of products are in stock.
- **Average Stock**: Approximately 6 units per product.
- **Pricing**: Product type 4 has notably higher prices compared to others.

### 3. Seller Metrics
- **Average Seller Count**: 4 sellers per product.
- **Observation**: Exclusive products dominate, but some products have up to 10 competing sellers, indicating moderate market competition.

### 4. Customer Review Metrics
- **Rating Distribution**: Predominantly 5-star reviews, reflecting high customer satisfaction.
- **Rating Trends**: Ratings peaked at 4.6 in 2002, dipped to 4.3 in 2006, and stabilized around 4.3–5.0.
- **Word Cloud Insights**:
  - Positive terms: "Great," "Good," "Excellent," "Perfect."
  - Common themes: Products often purchased as gifts for children (e.g., toys like puzzles, Lego, dominoes) for occasions like Christmas and birthdays.

### 5. Review Analysis
Reviews were categorized based on ratings:
- **Positive** (≥3): Analyzed using BERTopic with 5 topics.
  - Key themes: High satisfaction with product quality, suitability for children, fast delivery, and reasonable pricing.
  - Notable products: Toys fostering creativity, outdoor play, and collectibles like Beyblade.
- **Negative** (<3): Analyzed using BERTopic with 4 topics.
  - Common issues: Products smaller than expected, compatibility issues (e.g., Thomas train not fitting old tracks), and faulty electronics (e.g., Furby, RoboSapien).
  - Pain points: Misleading product images and descriptions, especially for gifts.

## Tools and Technologies
- **Data Processing**: Python (Pandas for cleaning, handling duplicates, and missing data).
- **NLP**: BERTopic with CountVectorizer for topic modeling, stopword removal.
- **Visualization**: Word Cloud, Power BI for interactive dashboards.
- **External Tools**: ChatGPT for generating conclusions from keywords.
- **Data Storage**: Datahub for data dictionary management.

## Power BI Demo
Interactive dashboards were created to visualize:
- Customer behavior metrics.
- Inventory and pricing trends.
- Seller and review analytics.

## Conclusions
### Positive Aspects
- Parents highly value toys that encourage parent-child interaction and creativity.
- Strong satisfaction with product quality and fast delivery.
- Beads for crafts and costumes are praised for quality and versatility.
- Simple, efficient chargers and reusable party items (e.g., dice, card sleeves) are well-received.

### Negative Aspects
- Misleading product sizes and images lead to dissatisfaction.
- Compatibility issues with toys (e.g., train tracks) frustrate customers.
- Expensive electronic toys often fail to meet expectations.
- Inaccurate descriptions (e.g., color, version) erode trust, especially for gifts.
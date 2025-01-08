Amazon Sales Data Analysis

## Project Overview

This project dives into Amazon's sales data to uncover actionable insights that help businesses make smarter decisions. With an interactive dashboard, businesses can easily understand:

- Which products are driving revenue and profits.
- How different categories and subcategories are performing.
- Key trends in pricing, customer preferences, and profit margins.

## Why This Project?

Businesses often struggle to make sense of their sales data. This project was created to solve that problem by:

- Simplifying decision-making with clear insights into what works and what doesn’t.
- Helping teams focus on the most valuable products and categories.
- Replacing guesswork with solid, evidence-based strategies for growth.

## What We Achieved

- **Built an Interactive Dashboard**: Easy-to-use and packed with filters for exploring data.
- **Uncovered Key Insights**:
  - Identified top-performing products and categories.
  - Highlighted profitable and underperforming subcategories.
  - Provided actionable recommendations to improve sales and profits.

## Key Metrics (KPIs)

To measure success, the dashboard tracks:

- **Total Sales (Actual Price)**: Revenue before discounts.
- **Total Sales (Discounted Price)**: Revenue after discounts.
- **Total Profit**: Profit after subtracting costs.
- **Subcategory Metrics**:
  - Product orders and profits.
- **Top Products by Revenue and Profit**.
- **Category-Wise Profit Distribution**.
- **Product Ratings**: Customer satisfaction and quality.

## Tools and Technologies

### Tools

- **Power BI**: For creating visualizations and dashboards.
- **Excel**: For cleaning and preparing data.

### Technologies

- **Data Visualization**: Designed interactive charts and graphs.
- **Data Modeling**: Structured data relationships for better analysis.
- **DAX (Data Analysis Expressions)**: Built custom calculations for metrics.

### Data Source

- **CSV File**: Amazon sales data including categories, prices, and profits.

## How It Works

### Step 1: Data Collection and Cleaning

- Used Excel to remove duplicates, fill in missing values, and format data for Power BI.

### Step 2: Designing the Dashboard

#### Page 1: Overview

- Highlights top metrics like total sales and profit.
- Visuals for subcategory and category performance.
- Interactive table for comparing products.

#### Page 2: Product Details

- Focused insights into individual products, such as their category, subcategory, and ratings.

### Step 3: Interactive Features

- Filters for exploring data by category and performance tiers.
- Hover functionality for seamless navigation between pages.

### Step 4: User Interaction

- Hover over charts and data points for quick insights.
- Navigate between high-level trends and detailed product views with ease.

## Getting Started

### Prerequisites

1. Install **Microsoft Power BI Desktop** ([Download Here](https://go.microsoft.com/fwlink/?LinkId=2240819&clcid=0x409&culture=en-us&country=us)).
2. Install **Microsoft Excel** (optional for preprocessing).

### Steps

1. **Download Files**:
   - CSV file: `amazon.csv`.
   - Power BI file: `Amazon_Sales_Analysis.pbix`.
2. **Open the Dashboard**:
   - Import the Power BI file into Power BI Desktop.
3. **Explore the Data**:
   - Use filters and hover features to interact with the dashboard.

### Key DAX Formulas

- **Rating Count Updated**:
  ```DAX
  Rating_count_updated = IF(AND(amazon[rating_count]=13,amazon[Index]=325),0,amazon[rating_count])
  ```

- **Product Quality**:
  ```DAX
  Rating wise Quality = IF(amazon[rating]>=3.9,"Good",IF(amazon[rating]>=2.9,"Average","Low"))
  ```

- **Star Rating Visualization**:
  ```DAX
  rating star rating =
    VAR __MAX_NUMBER_OF_STARS = 5
    VAR __MIN_RATED_VALUE = 0
    VAR __MAX_RATED_VALUE = 5
    VAR __BASE_VALUE = SUM('amazon'[rating])
    VAR __NORMALIZED_BASE_VALUE =
        MIN(
            MAX(
                DIVIDE(
                    __BASE_VALUE - __MIN_RATED_VALUE,
                    __MAX_RATED_VALUE - __MIN_RATED_VALUE
                ),
                0
            ),
            1
        )
    VAR __STAR_RATING = ROUND(__NORMALIZED_BASE_VALUE * __MAX_NUMBER_OF_STARS, 0)
    RETURN
        IF(
            NOT ISBLANK(__BASE_VALUE),
            REPT(UNICHAR(9733), __STAR_RATING)
                & REPT(UNICHAR(9734), __MAX_NUMBER_OF_STARS - __STAR_RATING)
        )
  ```

## Key Insights

- **Top Products**:
  - Most profitable: AmazonBasics HDMI Cable ($853,945 profit).
  - Highest-grossing: Sony Bravia TV.
- **Subcategory Trends**:
  - Top-selling: USB Cables.
  - Most profitable: Smart Televisions.
- **Category Highlights**:
  - Electronics dominate profits ($3.1M).

## Challenges and Solutions

- **Messy Data**: Cleaned with Excel to ensure accuracy.
- **Dynamic Visualizations**: Used DAX for interactivity and hover effects.
- **Large Dataset**: Optimized the data model for performance.

## What’s Next?

- Add time-series analysis for tracking trends over time.
- Incorporate customer segmentation to tailor marketing strategies.
- Explore predictive analytics for forecasting demand.
- Expand regional sales analysis for localization.

## How to Contribute

1. **Report Issues**: Share bugs or suggestions for improvement.
2. **Suggest Features**: Propose new metrics or visualizations.
3. **Submit Code**: Fork the repository and make pull requests.
4. **Enhance Documentation**: Add setup guides or FAQs.

## Key Takeaways

- Learned to create interactive dashboards with Power BI.
- Gained expertise in DAX and data modeling.
- Discovered how to turn raw data into meaningful insights for businesses.

We hope this project inspires smarter business decisions through data-driven insights!

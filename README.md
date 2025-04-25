# 🏷️ Adidas USA Product Data Analysis
<img width="1430" alt="image" src="https://github.com/user-attachments/assets/c0b337b3-ac88-4f99-bc6c-a3b7784f716d" />
Image : Addidas_USA website 


## 📌 Introduction
This project explores a dataset sourced from Kaggle containing product listings for Adidas USA. The dataset, originally in CSV format, was converted to Excel for analysis.

Our objective is to clean, analyze, and visualize the data to uncover insights about product distribution, pricing, customer preferences, and more. This analysis serves as a foundational step toward building a dashboard for business insights.

## 🧹 Data Cleaning & Preparation
### 1. Column Review & Removal
Inspected all columns for relevance.

Removed: Currency: All values are in USD, URL: Not needed for our analysis, Crawled_at: Timestamp irrelevant to business context.

### 2. Data Type Conversion
Converted selling_price from text to numeric format to enable accurate calculations.

### 3. Discount Calculation
In the absence of an explicit discount column, we used: 
=IF(OR(ISBLANK(F3), F3=0), 0, (F3-D3)/F3) assuming F3 as original_price and D3 as selling_price

### 4. Standardizing Color Values
Identified duplicate entries due to inconsistent naming (e.g., Multi color, MultiColor, and Multi).

Used Advanced Find & Replace to standardize all values to Multi.
<img width="796" alt="image" src="https://github.com/user-attachments/assets/1cd1d109-bdc9-420c-b3ec-06d32487d911" />

### 5. Category Subdivision
The breadcrumbs column contained category hierarchies (e.g., Men/Clothing).
Used Excel's TEXTSPLIT function to extract the top-level category:
=INDEX(TEXTSPLIT(J2, "/"), 1) assuming J2 as the category_column

### 6. Image Count Extraction
Product images were concatenated using ~ as a separator.
Counted the number of images using:
=LEN(M2)-LEN(SUBSTITUTE(M2,"~",""))+1  assuming M2 as the column with images
This formula calculates how many image URLs are associated with each product.

Data is now clean and ready for exploratory analysis. 

## 🔍 Exploratory Data Analysis (EDA)
### 1. Category-Wise Product Count
Created a Pivot Table:
Rows: Category
Values: Count of SKUs
🎯 Insight: Shoes dominates the catalog

### 2. Price Analysis
Used histograms to analyze:

Selling price ranges

Discount distribution

### 3. Ratings vs. Reviews
Created a scatter plot:

X-axis: Average Rating

Y-axis: Reviews Count

🎯 Insight: Products with higher reviews also tend to maintain good ratings.

### 4. Top Products by Rating & Popularity
Filtered:

Products with more than 10 reviews

Sorted to identify:

Top 5 products by average rating

Top 5 by review count

## 📊 Dashboard
### KPIs:

Total Products

Average Price

Average Rating

### Visuals:

Product Count by Category

Price Distribution

Review vs Rating Chart

Top-Rated Products

### Filters / Slicers:

Category

Color

Discount %

### Business Insights:

Optimize stock for high-demand categories (e.g., shoes)

Promote top-rated products with strong reviews

Standardize color naming for consistent UX

Adjust pricing strategies based on discount analysis

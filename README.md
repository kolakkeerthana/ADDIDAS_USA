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
excel
Copy
Edit
=INDEX(TEXTSPLIT(J2, "/"), 1)
### 6. Image Count Extraction
Product images were concatenated using ~ as a separator.

Counted the number of images using:

excel
Copy
Edit
=LEN(M2)-LEN(SUBSTITUTE(M2,"~",""))+1
This formula calculates how many image URLs are associated with each product.

✅ Data is now clean and ready for exploratory analysis.

## 🔍 Exploratory Data Analysis (EDA)
### 1. Category-Wise Product Count
Created a Pivot Table:

Rows: Category

Values: Count of SKUs

🎯 Insight: Footwear dominates the catalog, indicating a strong focus on shoes.

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

## 📊 Dashboard Plan (Power BI or Tableau)
KPIs:

Total Products

Average Price

Average Rating

Visuals:

Product Count by Category

Price Distribution

Review vs Rating Chart

Top-Rated Products

Filters / Slicers:

Category

Color

Discount %

Business Insights:

Optimize stock for high-demand categories (e.g., shoes)

Promote top-rated products with strong reviews

Standardize color naming for consistent UX

Adjust pricing strategies based on discount analysis



## INTRODUCTION
THE DATASET HAS BEEN DOWNLOADED from Kaggle and Converted from CSV to Excel.
To get started, we clean the data, 
### Data Cleaning and Preparation
1. Check for required columsn. Add filters to columns check ifh there are any unqie and not null if nt we can remove as in: currency is in USD and they all are from Addiddas United States. We also do need URL here because We are not extraccting anything. We also removed crawled at because we don't need it that is the date andtime at which the column has been inserted. 
2. Changinf the daatatypes. We see tha the Selling price is not numeric so, Covert it to numeric, 
3. ssuming that there was no discount, We calculate the discount%
4. Now, moving on to check if there are any duplicate values we observe that the color column has multi color and multi as two columns so t o merge them we use. Using the find and replace cloumn we replace Multi color with Multi. Upon performing search funtion we found out ther are tother places where MultiColor is written so to not distubr that we perform Advnaced searcha adn select search by columns and find entire cells onl which will search only required cells and replace. 

5. Now to subcategorize the category dsection we split he breadscrumb sectiio and split them to subcategorising them for better analysis using the textSPLIT Formula on Excel =INDEX(TEXTSPLIT(J2, "/"),1)
6. Now to deal with the image count. We hace a one more than imge in the column. So to deal with that we count the number of speperators and add 1 to the count whic shows th enumber of links. for that we use the following formula.
 =LEN(M2)-LEN(SUBSTITUTE(M2,"~",""))+1
This will count the characters in M2 with ~ and then replace it with blank space and then count which gives us the count and add 1 to balance it. 'This was a nice one.'



We are done with cleaning I suppose and now we proceed with EDA. 
### EDA Exploratory data Analysis
1. Category wise product count
Between Category and count of SKU which displays the shoes are being sold in the maximum count
2. Price analysis
histograms between Price ranges and dicount distribution
3. Rating vs Review Analysis
Purpose: See what customers love or hate.

Do this:

Create a scatter plot:

X-axis: average_rating

Y-axis: reviews_count

4. Top Products by Rating & Popularity
Purpose: Show what’s working and what can be promoted.

Do this:

Filter products:

Reviews > 10

Sort by average_rating

Highlight top 5 products by:

Highest rating

Most reviews

### For creating a dashboard
KPIs: Total Products, Avg Price, Avg Rating
Product Distribution & Mix

What Customers Love: Ratings & Reviews

Pricing Strategy Insights

Design Trends: Color & Category

Business Recommendations

Slicers (by category, color




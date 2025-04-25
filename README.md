# ADDIDAS_USA
## INTRODUCTION
THE DATASET HAS BEEN DOWNLOADED from Kaggle and Converted from CSV to Excel.
To get started, we clean the data, 
### Data Cleaning and Preparation
1. Check for required columsn. Add filters to columns check ifh there are any unqie and not null if nt we can remove as in: currency is in USD and they all are from Addiddas United States. We also do need URL here because We are not extraccting anything. We also removed crawled at because we don't need it that is the date andtime at which the column has been inserted. 
2. Changinf the daatatypes. We see tha the Selling price is not numeric so, Covert it to numeric, 
3. ssuming that there was no discount, We calculate the discount%
4. Now, moving on to check if there are any duplicate values we observe that the color column has multi color and multi as two columns so t o merge them we use. Using the find and replace cloumn we replace Multi color with Multi. Upon performing search funtion we found out ther are tother places where MultiColor is written so to not distubr that we perform Advnaced searcha adn select search by columns and find entire cells onl which will search only required cells and replace. 
<img width="796" alt="image" src="https://github.com/user-attachments/assets/1cd1d109-bdc9-420c-b3ec-06d32487d911" />
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




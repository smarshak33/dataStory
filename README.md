## **Methodology**
Sami Marshak
Link to my Github page/story: https://smarshak33.github.io/dataStory/index.html
Link to my full dataset: https://github.com/smarshak33/dataStory/blob/main/data-raw/nyc.xlsx 

**Source: **
My data is exported on excel from the United States Census Bureau's collection of monthly Business Formations/Applications in NYC.

**Categories:** 
Originally, when I downloaded the data on business formations, it included the "value" or amount of business formations in NYC there were in each month of a given year. I downloaded data from January 2016 until the latest publication of data in April 2025, but because my story was about entrepreneurship slightly before the pandemic until now, I only needed data as far back as 2019. 

**Analysis:**
To analyze how the trend in business formations has changed in NYC in 2025, which corresponds to entrepreneurship, I knew I needed to calculate percent changes-- but this was much more complex to accomplisg in Python than I originally thought.

I started with the basic, preliminary steps such as importing pandas, getting rid of wonky formatting, and trying to understand the data better using info and describe. All the dates were in the same column in a format that Python wouldn't understand for calculations, so I created a df called business_applications and converted the "period" column to datetime format using pandas. I soon realized that I wouldn't be able to do any meaningful analysis without creating more columns where the dates are separated by year, as we learned in class. 

Therefore, I created a pivot table that created "month" and "year" columns to clean the data. I enlisted the help of one of the data coaches for this step, because there were many issues that needed troubleshooting. For instance, I originally thought I needed to reindex the data to start at "1" instead of "0." We were also not sure why the year/month were in the same column when doing the pivot table, but when we exported the data to a csv to see what was the culprit, we learned it was just a Jupyter notebook hiccup.

After creating the pivot table, I sliced the data using .loc to get rid of 2016-2018, focusing only on 2019-2025 to do percent change. I finally had enough columns to do calculations that could "go across" the data. 

I found a percent change function we learned in class and used that to help with my analysis. To apply the function to all the columns without having to create a new function for each column, one of the data coaches helped me do a "for loop" that calculated the YoY $ change between each consecutive year, and added each result as a new column. I finally had all the data needed to complete my analysis, learning that new business formations rose by 1% in April compared to the same month last year, and were 4% higher in March 2025 than in March 2024. 

Judgement calls and caveats: Did you omit any data (i.e. an outlier that was messing with your analysis? Something that didn’t make intuitive sense to include?)

I definitely made some judgement calls. There was DCWP data on NYC business licenses that I analyzed in excel, where I learned that in March of 2025, 1514 licenses have been issued to NYC businesses from the NYC Department of Consumer and Worker Protection (DWCP), a 24% increase from the same period last year. However, I didn't answer enough questions in my reporting about how significant that data was, what it truly means, and how it applies to entrepreneurship, so I decided to leave it out of my analysis.

Ideal further reporting and data analysis would also show the impact of congestion pricing and global tourism decline in hard data on entrepreneurship, but those answers aren't available yet. 

## **Methodology**

Link to Github page/story: https://smarshak33.github.io/dataStory/index.html

Link to my full dataset: https://github.com/smarshak33/dataStory/blob/main/data-raw/nyc.xlsx 

## **Source: **
My data is exported on excel from the United States Census Bureau's collection of monthly Business Formations/Applications in NYC.

## **Categories:** 
Originally, when I downloaded the data on business formations, it included the "value" or amount of business formations in NYC there were in each month of a given year. I downloaded data from January 2016 until the latest publication of data in April 2025, but because my story was about entrepreneurship slightly before the pandemic until now, I only needed data as far back as 2019. 

## **Analysis:**
To analyze how the trend in business formations has changed in New York City in 2025—a key indicator of entrepreneurship—I focused on calculating percent changes over time. While I initially thought this would be straightforward, I quickly realized it required more complex data cleaning and transformation in Python than expected.

I began with preliminary steps, such as importing relevant Python libraries like pandas, exploring the dataset with .info() and .describe(), and cleaning formatting issues. One major obstacle was the "period" column, which stored dates in a format incompatible with time-series analysis. I created a new DataFrame, business_applications, and converted the "period" column to datetime format using pandas.to_datetime().

To make the data more usable, I extracted the year and month from the datetime values and created new columns for each. This allowed for easier grouping and time-based comparisons. Creating a pivot table was a key step—though it required troubleshooting. Initially, I misinterpreted the output, thinking that year and month were incorrectly combined into one column. Exporting the pivot to a CSV revealed it was simply a display quirk in Jupyter Notebook.

Once the data was in a cleaner format, I used .loc[] to slice the DataFrame, narrowing the scope to business formations from 2019 to 2025 to allow for meaningful year-over-year (YoY) comparisons. I then used a percent change function we had covered in class. With help from a data coach, I applied the function in a loop across relevant columns to calculate the YoY percentage change for each month. This loop added new columns to the DataFrame showing the YoY change in business formations for each period.

The final analysis revealed that new business formations in NYC increased by 1% in April 2025 compared to April 2024, and were 4% higher in March 2025 than in March 2024. 

## **Editorial decisions** 

I made several editorial decisions about what data to include in the final analysis. For instance, I explored data from the NYC Department of Consumer and Worker Protection (DCWP), which showed that 1,514 business licenses were issued in March 2025—a 24% increase from the same month in 2024. However, I ultimately excluded this dataset. While the figure was interesting, I couldn’t confidently assess how directly it reflected entrepreneurial activity, and it raised more questions than answers. Without stronger reporting on what the licenses represented or how DCWP tracks business type or survival, including this data could have been misleading.

Further reporting and analysis could explore the impact of upcoming policies like congestion pricing, or trends such as a decline in global tourism, on business formation rates. Unfortunately, the necessary data for these angles was not yet available.

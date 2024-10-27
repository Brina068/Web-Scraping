# Project Overview

This is a simple web scraping and data cleaning project for a Wikipedia page about the most visited museums in the world. Although it may seem straightforward, some issues arose that may not be obvious to beginners.

## Libraries

- **Beautiful Soup**: for extracting data from the website
- **Pandas**: for creating the DataFrame and running some queries

## Project Structure

1. **HTML Data Extraction**: We begin by fetching HTML content from the target URL containing museum data. Using BeautifulSoup, we parse the HTML structure and locate relevant tables.

2. **Data Transformation**:
- With Pandas, we read the extracted data into a DataFrame.
- Column titles and row data are then organized into lists and added to the DataFrame. Here, we address certain inconsistencies, such as handling missing values and incorrect column counts.

3. **Data Cleaning**:
- The Visitors annually column contains more than just numeric data, making it difficult to filter or compare the numbers accurately.

4. **Filtering and Analysis**:
- After cleaning, the dataset is ready for further analysis, including filtering museums by location or selecting those with over a specific number of annual visitors.


## Problems That I've Encountered

1. The DataFrame was showing 101 rows instead of 100. This could have been due to duplicates or blank rows, so I first used `df.info()` to check for any null values. Then, I checked for unique values, counted duplicates, and finally eliminated them.
   
2. The "Visitors annually" column was not displaying just the number of visitors (e.g., 8,860,000 (2023)[3] instead of 8,860,000). To address this, I first checked the data type of the column and then created a function that cleans each line. The function started by converting the column to text using `astype()`, then extracted only the numbers using the expression `(\d[\d,]*)`, replaced the commas, and converted it back to numbers.

## Final Notes

With these issues resolved, the DataFrame is now well-prepared for additional queries and analysis. This project highlights that even simple web scraping tasks can present hidden challenges, making it a great learning experience for anyone stepping into data processing and web scraping. Future improvements could involve automating data updates from the webpage or extending the analysis to include trends in museum visits over time.

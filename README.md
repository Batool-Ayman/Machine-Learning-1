# Machine-Learning-1
# Netflix Movies and TV Shows: Exploratory Data Analysis (EDA)


## 1. Project Overview
This project involves a comprehensive Exploratory Data Analysis (EDA) of the Netflix library. By utilizing data cleaning and visualization techniques, the study uncovers trends in content distribution, geographical production hubs, and the temporal growth of the streaming platform.

## 2. Dataset Description
The following details outline the structure and origin of the data used in this analysis:
* **Dataset Source:** Sourced from the Netflix Movies and TV Shows dataset available on Kaggle.
* **Initial Size:** The raw dataset contains 8,807 rows (individual titles) and 12 columns (features).
* **Cleaned Size:** Following the data cleaning process, the dataset used for visualization contains 5,696 rows.
* **Purpose:** The primary purpose is to perform a retrospective analysis of Netflix's content strategy, identifying patterns in production types, audience targeting, and library scaling.

### Description of Features (Columns)
| Column Name | Description | Data Type |
| :--- | :--- | :--- |
| **show_id** | Unique identifier for every movie or show. | Object |
| **type** | Categorization as either a 'Movie' or 'TV Show'. | Object |
| **title** | The official title of the content. | Object |
| **director** | The director(s) involved in the production. | Object |
| **cast** | Main actors featured in the content. | Object |
| **country** | The country or countries where the content was produced. | Object |
| **date_added** | The specific date the title was released on the Netflix platform. | Datetime |
| **release_year** | The original year the movie or show was released. | Int64 |
| **rating** | The target audience age rating (e.g., TV-MA, PG-13). | Object |
| **duration** | The length of the movie (minutes) or the number of seasons for a show. | Object |
| **listed_in** | Genres and descriptive categories for the title. | Object |
| **description** | A brief summary of the movie or show. | Object |

## 3. Data Cleaning
The cleaning process was essential to ensure the accuracy of the visualizations and the reliability of the insights.

### Why was cleaning needed?
* **Missing Values:** Significant missing data was found in the `director` (2,634), `country` (831), and `cast` (825) columns.
* **Incorrect Formats:** The `date_added` column was a string object, which prevented chronological sorting and time-series analysis.
* **Redundancy:** String information (e.g., " min") in numerical fields needed to be removed to allow for mathematical calculations.

### Steps Performed and Changes Made
* **Null Treatment/Imputation:** Empty entries in the `country` column were filled using the **Mode** (most frequent value), identifying the "United States" as the primary producer.
* **Row Removal:** Other rows with critical missing data (like `date_added` or `rating`) were removed to ensure a clean analysis set.
* **Type Conversion:** The `date_added` column was converted to **datetime objects** to allow for chronological sorting.
* **Feature Engineering:** A `year_added` feature and a `month_added` feature were extracted from the date to facilitate growth and seasonal trend comparisons.
* **Numerical Extraction:** For movies, the string " min" was removed from the `duration` column and converted to a float to allow for mathematical correlation calculations.

## 4. Visualizations and Insights
The following plots were chosen to highlight specific business trends and content patterns within Netflix:

### Chart 1: Content Distribution (Pie Chart)
* **Purpose:** To see the high-level split between Movies and TV Shows.
* **Insight:** The library is dominated by Movies, which account for approximately **69.7%** of titles, compared to **30.3%** for TV Shows.

### Chart 2: Top 10 Countries (Bar Chart)
* **Purpose:** To identify which regions are the primary content hubs.
* **Insight:** The **United States** is the leading producer, followed by **India** and the **United Kingdom**.

### Chart 3: Historical Added Content (Line Chart)
* **Purpose:** To observe the growth of the Netflix library over time.
* **Insight:** A sharp increase in content additions began around **2015**, reaching a peak between **2018 and 2019**.

### Chart 4: Rating Distribution (Count Plot)
* **Purpose:** To understand the target audience and content maturity levels.
* **Insight:** **TV-MA** (Mature Audiences) and **TV-14** are the most frequent ratings, indicating Netflix focuses heavily on adult and teen demographics.

### Chart 5: Content Release Year (Histogram)
* **Purpose:** To see the age profile of the library.
* **Insight:** Most content is very modern, with a massive concentration of titles released after **2010**.

### Chart 6: Monthly Trends (Bar Chart)
* **Purpose:** To check for seasonality in content additions.
* **Insight:** Content addition is relatively steady, with slight peaks during end-of-year holiday periods and mid-year cycles.

### Chart 7: Correlation Matrix (Heatmap)
* **Purpose:** To find relationships between release year, duration (movies only), and add date.
* **Insight:** An analysis of `release_year` and `duration_min` revealed a slight **negative correlation**, suggesting a recent trend toward shorter runtimes in newer releases.

## 5. Summary of Learning
From this analysis, we can learn that Netflix transitioned to a library heavily skewed toward modern, adult-oriented movies produced primarily in the US and India. The platform's rapid growth peaked just before 2020, and its strategy relies on fresh content rather than historical cinema.




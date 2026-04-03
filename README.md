# Machine-Learning-1
# Netflix Movies and TV Shows: Exploratory Data Analysis (EDA)

## 1. Project Overview
This project involves a comprehensive Exploratory Data Analysis (EDA) of the Netflix library. By utilizing data cleaning and visualization techniques, the study uncovers trends in content distribution, geographical production hubs, and the temporal growth of the streaming platform.

## 2. Dataset Description
The following details outline the structure and origin of the data used in this analysis:

* **Dataset Source:** The data was sourced from the **Netflix Movies and TV Shows** dataset available on **Kaggle**.
* **Dataset Dimensions:** The original dataset contains **8,807 rows** (individual titles) and **12 columns** (features).
* **Purpose of using this Dataset:** The purpose of this dataset is to perform a retrospective analysis of Netflix's content strategy. It allows for the identification of patterns in the types of content produced, audience targeting through ratings, and how the platform has scaled its library over the last decade.

### Description of Features (Columns)
| Column Name | Description | Data Type |
| :--- | :--- | :--- |
| `show_id` | Unique identifier for every movie or show | Object |
| `type` | Categorization as either a 'Movie' or 'TV Show' | Object |
| `title` | The name of the specific title | Object |
| `director` | The director(s) involved in the production | Object |
| `cast` | The main actors featured in the content | Object |
| `country` | The country or countries where the content was produced | Object |
| `date_added` | The specific date the title was released on the Netflix platform | Datetime |
| `release_year` | The original year the movie or show was released | Int64 |
| `rating` | The target audience age rating (e.g., TV-MA, PG-13) | Object |
| `duration` | The length of the movie (minutes) or the number of seasons for a show | Object |
| `listed_in` | Genres and descriptive categories for the title | Object |
| `description` | A brief summary of the movie or show | Object |



## 3. Data Cleaning & Preparation
To ensure data integrity, the following cleaning steps were applied:
* **Missing Value Management:** Significant missing data was found in `director` (2,634), `country` (831), and `cast` (825).
* **Imputation:** Empty entries in the `country` column were filled using the **Mode** (most frequent value), which identified the "United States" as the primary producer.
* **Row Removal:** Records with null values in the essential `date_added` and `rating` columns were removed to maintain analysis quality.
* **Data Type Conversion:** The `date_added` field was converted from a string format to a `datetime` object to allow for chronological sorting.
* **Feature Engineering:** A `year_added` feature was extracted from the date to facilitate annual growth comparisons.

## 4. Key Findings from EDA

### Univariate Analysis
* **Content Type:** The library is dominated by Movies, which account for approximately **69.7%** of the titles, compared to **30.3%** for TV Shows.
* **Ratings:** **TV-MA** is the most frequent rating, showing that Netflix content is largely tailored for mature audiences.

### Bivariate Analysis
* **Global Production:** The **United States** is the leading producer of titles, followed by India and the United Kingdom.
* **Movie Duration:** Runtimes for the majority of movies fall between **80 and 120 minutes**.

### Time-Based Analysis
* **Library Growth:** A sharp increase in content additions began in **2015**, reaching a peak between **2018 and 2019**.
* **Seasonality:** Monthly trends indicate that Netflix prefers adding content during the end-of-year holiday period and mid-year cycles.

### Correlation Matrix (Movies Only)
* An analysis of `release_year` and `duration_min` revealed a slight **negative correlation**, suggesting a recent trend toward shorter runtimes in newer releases.

## 5. Tools Used
* **Python:** Programming language.
* **Pandas:** Data cleaning and manipulation.
* **Matplotlib & Seaborn:** Data visualization.
* **Jupyter Notebook:** Development environment.




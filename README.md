# Machine-Learning-1
# Netflix Movies and TV Shows: Exploratory Data Analysis (EDA)

## 1. Project Overview
This project involves a comprehensive Exploratory Data Analysis (EDA) of the "Netflix Movies and TV Shows" dataset sourced from Kaggle. The objective of this assignment is to apply data cleaning and visualization techniques to uncover trends in content distribution, geographical production, and temporal growth of the Netflix library.

## 2. Dataset Description
The dataset consists of metadata for approximately **8,807** titles available on Netflix, including movies and TV shows.

### Data Dictionary
| Column Name | Description | Data Type |
| :--- | :--- | :--- |
| `show_id` | Unique ID for every movie/show | Object |
| `type` | Identifier for 'Movie' or 'TV Show' | Object |
| `title` | Title of the movie/show | Object |
| `director` | Director of the movie | Object |
| `cast` | Actors involved in the movie/show | Object |
| `country` | Country where the movie/show was produced | Object |
| `date_added` | Date it was added on Netflix | Datetime |
| `release_year` | Actual release year of the movie/show | Int64 |
| `rating` | TV Rating of the movie/show | Object |
| `duration` | Total duration in minutes or number of seasons | Object |
| `listed_in` | Genere/Category | Object |
| `description` | Summary description of the content | Object |



## 3. Data Cleaning & Preparation
To ensure the accuracy of the analysis, the following cleaning steps were performed:
* **Missing Values:** Significant missing data was identified in `director` (2,634), `country` (831), and `cast` (825).
* **Imputation:** Missing values in the `country` column were filled using the **Mode** (most frequent value), which was the "United States".
* **Data Integrity:** Rows with null values in critical columns such as `date_added` and `rating` were dropped.
* **Type Conversion:** The `date_added` column was converted from a string to a `datetime` object to facilitate time-based analysis.
* **Feature Engineering:** A new column, `year_added`, was extracted from the date to track annual growth.

## 4. Key Findings from EDA

### Univariate Analysis
* **Content Type:** Approximately **69.7%** of the content on Netflix consists of Movies, while **30.3%** are TV Shows.
* **Ratings:** The most prevalent rating is **TV-MA**, indicating that a majority of Netflix's library is geared toward adult audiences.

### Bivariate Analysis
* **Global Production:** The **United States** is the leading producer of Netflix content, followed by India and the United Kingdom.
* **Movie Duration:** Most movies on the platform have a runtime ranging between **80 and 120 minutes**.

### Time-Based Analysis
* **Growth:** There was a massive surge in content added to the platform starting around **2015**, peaking between **2018 and 2019**.
* **Seasonality:** The monthly trend analysis shows that Netflix frequently adds new content during the holiday months (December/January) and mid-year.

### Correlation Matrix (Movies Only)
* Analysis of numerical features (`release_year`, `duration_min`, `year_added`) showed a slight **negative correlation** between release year and duration, suggesting a trend toward slightly shorter movies in recent years.

## 5. Tools Used
* **Python:** Main programming language.
* **Pandas:** Data manipulation and cleaning.
* **Matplotlib & Seaborn:** Data visualization and styling (`sns.set()`).
* **Jupyter Notebook:** Environment for code execution and documentation.

---

### How to use this repository?
1. Clone the repository.
2. Ensure you have `netflix_titles.csv` in the root folder.
3. Open `EDA.ipynb` in a Jupyter environment and run all cells to reproduce the visualizations.




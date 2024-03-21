Final Project Submission
Please fill out:

Student name: CAROL MUNDIA
Student pace: HYBRID
Scheduled project review date/time:
Instructor name: MARYANN MWIKALI
Blog post URL:
**Project Overview**
My objective is to conduct exploratory data analysis on the movie dataset, aiming to provide actionable insights and recommendations for Microsoft Corporation. Through a thorough examination of the data, I will identify key trends, patterns, and opportunities within the movie industry. By leveraging exploratory techniques, I aim to offer strategic guidance to Microsoft on potential avenues for entry or expansion in this sector, ultimately informing their decision-making process and maximizing their success in the entertainment market.
**Project Objectives**
My main objectives are;
1. Find out which movie genres are the most popular.
2. Discover which movie publishers are the most popular.
3. Figure out which movie ratings are the most common.
4. Explore how production budgets relate to movie profits.
**Business Understanding**
Microsoft has observed the success of major companies venturing into original video content creation and is eager to join the trend. Recognizing the potential in this arena, they have made the strategic decision to establish a new movie studio. Despite their expertise in other areas, Microsoft acknowledges their lack of experience in the movie industry. Therefore, they are seeking to gain insights and expertise to ensure the success of their venture into movie production.
**Data Understanding**
Before diving into data analysis, it's crucial to import essential libraries that streamline the process of reading and manipulating datasets. 

**Pandas** simplifies data manipulation with its high-level data structures and functions, making tasks like data cleaning, transformation, and analysis straightforward. 

**NumPy** provides efficient numerical computing capabilities, enabling complex mathematical operations on multi-dimensional arrays with ease.

**SQLite** offers a lightweight, embedded relational database engine for local data storage and querying directly within Python applications, making it ideal for small to medium-sized datasets. 
#The next step involves accessing and familiarizing ourselves with the datasets.
#I start by establishing a connection to the database and inspecting the available tables.
# I proceed to determine the number of entries, columns, and their respective data types.
#Understanding the dataset's dimensions by determining the number of rows and columns, along with inspecting the data types of each column.
# reading the data and assigning it to rv_df
#Displaying the last 3 entries of the dataset.
**Data Preparation**
*After briefly reviewing the dataset, I commenced the data preparation phase, which entailed data cleansing with the following objectives:
#Handling the NaNs or missing values.
#Verify that all columns have the appropriate data type.
#Address any placeholders present.
In the subsequent cells, I will perform data cleaning and ETL for each dataset.
#Dealing with missing Values
*The initial step involves determining the percentage of missing values in each column of the bomovies_df dataset.
Based on the findings, it appears that the bomovies_df dataset has a relatively low proportion of missing values across all columns, except for the foreign_gross column, which has a slightly higher percentage.
Nevertheless, the foreign_gross column exhibits a significantly higher missing value percentage, nearing 40%. I've inferred that these missing values indicate movies that were exclusively distributed domestically and didn't generate revenue from international markets. Hence, I've replaced the missing values in the foreign_gross column with 0.
I additionally substituted missing values in the domestic_gross column with zero, under the assumption that these movies did not generate sales in the domestic market.
The following code segments substitute NaN values with 0 in the domestic_gross and foreign_gross columns, respectively.
dtype: float64
In the studio column, I replaced missing values with the mode, representing the most frequently occurring studio.
To identify the most frequent studio, I utilized the following code:
I have successfully handled the missing values in the bomovies_df dataset.
Converting columns to their appropriate data types.
However, I observed that the domestic_gross, foreign_gross, and year columns are in incorrect data types, so I cast them to the appropriate data types.
Handling missing values in rt_df.
Dealing with the nulls;
In the rt_df dataframe, I identified that only two columns would be relevant for my analysis: genre and rating. I extracted them from the main data frame as follows:
Subsequently, I addressed the missing values by removing the rows containing null values in the specified columns.
Addressing missing values by dropping all rows containing null values.
The next step involves splitting the ratings column in the rt_reviews (rv_df) dataset into two columns. This allows for standardizing ratings across all entries through feature engineering.
Before standardizing the ratings, I'll convert the column types from string to integer to enable mathematical computation.
Perfect! This data has no any missing value.
Check for missing values
budgets.isna().mean()*100  #checks for percentage of missing values. 
The budgets_df is also complete!
As the domestic_gross, Production_budget, and Worldwide_gross columns are currently in string format, it's necessary to convert them to integers to enable feature engineering and enhance the data's insightfulness.
The following code converts the columns containing dollar signs into integers to facilitate feature engineering.
budgets.info()  # checkig if  we have the correct datatypes
**Data Analysis**
After ensuring the data is clean and ready, I proceeded to delve into data analysis. In this section, I aim to derive meaningful insights from the data. I will merge datasets to uncover deeper analyses and craft a compelling narrative that Microsoft would undoubtedly be interested in.
My Data Analysis will focus on Establishing the following:
Which is the most popular genre of movies
Which is the most popular studio
Which rating is most preferred
Most Popular Genre of Movies
From the rt_ movies dataset I can establish the top 5 genres of movies
Based on the results above, Drama emerges as the most popular genre of movies, followed by Comedy, and then comedy|Drama, and so forth. This information can be effectively visualized in the chart below:
# Getting the X and Y  values 
# Ploting  Most popular  Genres and their frequencies
#Most Popular studio
I can identify the most popular studio from the bomovies_df dataset.
Most Popular Rating
Is There a Relationship Bewteen Movie Production Budget and Profits Realised
To ascertain whether the production budget affects profitability, I calculated the correlation between the production budget and profit realised domestically and worldwide
C:\Users\user\AppData\Local\Temp\ipykernel_10264\2354375143.py:1: FutureWarning: The default value of numeric_only in DataFrame.corr is deprecated. In a future version, it will default to False. Select only valid columns or specify the value of numeric_only to silence this warning.
 In the correlation matrix provided, it's evident that the correlation between the Production budget and worldwide is positive and stronger compared to that between the Production budget and domestic profit. A scatter plot depicting this relationship is presented below:
Most Popular Genre_ids
This insight can be obtained
Popularity By Language
C:\Users\user\AppData\Local\Temp\ipykernel_10264\1549669306.py:1: FutureWarning: The default value of numeric_only in DataFrameGroupBy.sum is deprecated. In a future version, numeric_only will default to False. Either specify numeric_only or select only columns that should be valid for the function.
Merging Datasets
Merged_df= pd.merge(rv_df, budgets)
Merged_df.head()
Summary
The visualizations presented above provide valuable insights that will guide Microsoft's foray into movie production. With these insights, Microsoft can be confident in their data analysis approach and make informed decisions to ensure success in their movie-production endeavors.

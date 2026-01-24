# Data 200: Independent Project Option 1

## Introduction to the data: Asthma Prevalance

This data on asthma prevalence comes from the California Open Data Portal <https://data.ca.gov/dataset/asthma-prevalence>. 

These datasets contain the estimated percentage of Californians with asthma (asthma prevalence). Two types of asthma prevalence are included: 1) lifetime asthma prevalence describes the percentage of people who have ever been diagnosed with asthma by a health care provider, 2) current asthma prevalence describes the percentage of people who have ever been diagnosed with asthma by a health care provider AND report they still have asthma and/or had an asthma episode or attack within the past 12 months. The tables “Lifetime Asthma Prevalence by County” and “Current Asthma Prevalence by County” are derived from the California Health Interview Survey (CHIS) and include data stratified by county and age group (all ages, 0-17, 18+, 0-4, 5-17, 18-64, 65+) reported for 2-year periods. 


## Instructions

Essentially this project will require the same skills you have been learning in class and practicing in the labs and homework, but without the guard rails. I am not instructing you on what functions to use, just the tasks to accomplish.

Remember that you can use resources, but responsibly. If you ask a friend for help, make sure you two do not have identical responses. If you use the AI tools or Google searches for help, do not just copy code, make sure you understand what it is doing.

You'll write all of your code in the `individual-project.qmd` file in this repo.

### Data cleaning:

- Read in your data and clean the column names to comply with tidyverse style guide rules.
- For each data set identify number of rows and columns.
- For each data set what does one observation represent?
- Identify the type for each variable and if it has an appropriate R type.
- Identify how many counties are in each data frame.
- For each data set rename the `lifetime_prevalence` and the `current_prevalence` columns to `prevalence`.
- Add a column to each data set called `prevalence_type`. This column should store `current` for every row of the "current" dataset and `lifetime` for the "lifetime" dataset.
- Join data frames, keeping all rows and columns from each.
- Make the `prevalence_type` variable into a factor.
- Currently the `years` variable stores a 2 year range and is recorded as a string. Define two new variables called `start_year` and `end_year` which record the start and end years. For example: for a row where  year is "2015-2016" I want the `start_year` variable to store just "2015" and the `end_year` variable to store "2016". 
- Drop the original `years` variable and convert the `start_year` and `end_year` variables to integers.
- Your final task will be to create a map with our data. First we will need to include latitude and longitude for each county. The `map_data()` provides the necessary longitude and latitude data for different geographic regions, including California counties. Use `map_data("county", region = "california")` to load in the geographic data. Notice there is a mismatch between the county variables is your asthma data and the geographic data. Identify and rectify the issue, then join the data frames, keeping only rows and columns present in both data frames.
- Save the cleaned data frame into the `data` folder and name it `asthma-data-cleaned.csv`

### Data summarizing:

- Plot the distribution of lifetime prevalence for all counties and for all age groups (together, not separately).
- Plot asthma prevalence for Ventura county over the years for all age groups, colored by whether the prevalence is for current or lifetime.
- Which California counties have the minimum and maximum lifetime asthma prevalence across all ages for the years 2021-2022?
- Challenge: Plot lifetime asthma prevalence by county on a map across all ages for the years 2021-2022. Hint: You can use the following code to produce a map by county `ggplot(aes(x = long, y = lat, group = county, fill = prevalence)) + geom_polygon()`.
- Finally, pose your own question and produce a visual to help answer it. Make sure the write out your question.

### Version control:

- Make sure to commit and push fairly frequently, especially after you make a big change or take a break.
- Part of your grade will be based on appropriate commit frequency (minimum 3 times).
- Part of your grade will be based on clear and concise commit messages 

### Coding

- Follow tidyverse style guide.
- When reporting calculations use inline R code instead of typing out a number.
- For all plots specif: axes labels, plot titles, and alternate text.

### Resources used

- Have you done the project by yourself, with a peer(s), or used tools like ChatGPT? 
- If you provided help to a peer(s) and/or got help from your peers(s) please explain briefly what this entailed. 
- If you used tools like ChatGPT, include the prompts you used and explain how the tool helped supported your learning. 


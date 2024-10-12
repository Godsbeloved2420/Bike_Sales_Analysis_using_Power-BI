## 1.0. Title:

Bike Sales Analysis using Power-BI

## 2.0. Introduction

## 2.1. Objective: 

The purpose of this analysis is:

i) to visualize  how various demographic factors such as income, gender, region and marital status influence the bike purchase decision of customers. 

ii) identify patterns and trends in the dataset that could allow the bike sales company make informed decisions.

## 2.2. Context: 

The dataset is made up of data collected by a company that deals on bike. The different fields contain different socio-demographic and bike purchase information of the customers. Which includes: ID,	Marital Status,	Gender,	Income,	Children,	Education,	Occupation,	Home Owner,	Cars,	Commute Distance,	Region,	Age,	Purchased Bike. The dataset contains two datatypes: strings and integers.

### 2.3. Data Sources

The primary source of data used here is bikedata.xlsx which was gotten as an excel file and it's an open source data which was given as a practice data. The following is the link to the dataset: 

https://docs.google.com/spreadsheets/d/1qzPm4m7N8K8KQcNwRcOZfbIZJ5YC0t0O/edit?usp=drive_link&ouid=106458428464023242528&rtpof=true&sd=true



## 3.0. Data Understanding

### 3.1. Data description
The dataset was gotten in a structured form and contains 1,026 rows and 13 columns. 

### 3.2. Exploratory data analysis (EDA)

Microsoft Power BI was implored in cleaning, analyzing and visualizing the dataset. At the end of the analysis, we were able to visualize:

a) region that made the highest purchase.

b) gender that made the highest purchase.

c) commute distance that made the highest bike purchase.

d) age bracket and region that purchased bike most 

e) educational qualification that purchased bike most

f) car owners that decided to purchase bike.


## 4.0. Methodology

### 4.1. Data preprocessing

The dataset was imported into Google Drive then into Google Colab. The different libraries were also imported (Numpy, pandas, Matplotlib and Seaborn). The dataset was called 'file'.

#### Some of the steps taken in cleaning of the dataset includes:

a) removing of duplicates (file.drop_duplicates (inplace = True)

b) replacing 'M' and 'S' in the Marital Status column of the dataset with 'Married' and 'Single' respectively 

```Python
file['Marital Status']=file['Marital Status'].replace(['M','S'],['Married','Single'])
```

c) replacing 'M' and 'F' in the Gender column with 'Male' and 'Female' respectively 

```Python
file['Gender']=file['Gender'].replace(['M','F'],['Male','Female']).
```

d) grouping 'Age' into different age brackets.

```Python
def age_grouping(age):
    if age<=30:
        return 'Adolescent'
    elif age<=54:
        return 'Middle Age'
    else:
        return 'old'
    
file['Age Bracket']=file['Age'].apply(age_grouping)
```


Data Description: The data set contains columns like:
Marital Status: Both married and single customers are well-represented. 
Gender: The data set includes a mix of male and female customers.
Income: Income levels vary across customers.
Age Bracket: The customers are grouped into Youth, Middle Age, and Old brackets, with a higher concentration in the Middle Age group.
Purchased Bike: Shows whether the person has purchased a bike or not using boolean (Yes/No) etc.
The data set was examined for duplicate values (26), which were found and removed. Several columns, such as marital status and gender, were cleaned to replace abbreviations with full text (e.g., "M" with "Married" and "S" with "Single"). The income column was also rounded to 0 decimal places for consistency.
Exploratory Data Analysis (EDA):
Initial data exploration involved:
Checking for duplicates and removing them.
Cleaning the columns for better readability.
Visualizing the distribution of key factors like gender, marital status, and income levels.
4. Methodology
Data Processing:
Handling Missing Values: Missing or incomplete data points were checked, though no specific mention of missing data handling was observed in the notebook.
Data Transformation: The gender and marital status columns were transformed from coded values ("M", "F",, “M”, "S") to more descriptive text labels ("Male", "Female", "Married", "Single"). The income data was also rounded for simplified analysis.
Feature Engineering: No additional features were created, but transformations were made to ensure proper data handling and interpretation.
Analytical Approach:
The analysis focuses on basic exploratory statistics and visualizations. No advanced machine learning models or complex statistical tests were used. The analysis relies on descriptive statistics and visual examination to draw insights.
Assumptions:
It is assumed that the data set is a representative sample of the population of interest.
It is assumed that the gender, marital status, and income factors are key drivers of bike purchase decisions, though other factors could also play a role.


Analysis

Results:
After cleaning the data, the following observations were made:
Income Distribution: There is variability in income levels across individuals, most people who earn within the average of the demography purchase bike.
Marital Status and Gender Influence: From the cleaned data, patterns emerged showing potential differences in bike purchase behavior based on marital status and gender.
Interpretation:
The initial EDA suggests that:
Married individuals might show different purchase behaviors compared to singles, potentially due to differences in financial situations.
Gender may also play a role in influencing bike purchases.
Validation:
No specific validation techniques were used in this analysis. 
6. Conclusion
Key Insights:
Target Demographic: Middle-aged individuals with moderate to high income seem like potential target customers for bike marketing.
Regional Focus: Regions with higher purchase rates should receive targeted marketing, while regions with lower rates might benefit from awareness campaigns.
Lifestyle Considerations: Short commute distances and a lack of car ownership are lifestyle factors that could be highlighted in marketing campaigns to attract more bike buyers.
Recommendations:
The insights on demographic patterns can be used to inform targeted marketing strategies, such as promoting bikes to specific income group’s e.g the middle age bracket or tailoring messaging for married vs. single customers.
Limitations:
Further research could include additional factors, such as geographic location or education level, to provide a more comprehensive analysis.

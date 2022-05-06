# AIT 664 DL1 - Obesity Study
### Eun Lee, Mike Lewis, Nitin Panwar, and Paul Buckley
<hr/>


### About the data
Our data comes directly from the CDC. We focus on leveraging the Behavioral Risk Factor Surveillance data. This department was initially established in 1984 and currently collects data on all 50 states. Each year, 400,000 or more adults are interviewed and the data is aggregated by state into individual stratifications. The dataset unfortunately only provides a single stratification per record. This means that a record can describe an income group, age group, or ethnicitic group. The data is further divided into a category; physical activity, overweight/obesity, and nutritional habits.

#### Data Cleaning and Assumptions

The BRFS set contained several columns that contained the same information but in a slightly different format (example... QuestionID and Question described the aspect of the record - obesity/overweight, nutritional habits, physical activity habits. We chose to drop several columns from the dataset because of this. Additionally, our study focuses on the 50 states but our dataset included the territories as well. We droped all records that focused on the territories. Finally, our machine learning algoritms focused on records that were based on a statistically signifigant sample size (drop records with < 100 samples).

Since our study is primarily done using BI tools and a cloud hosted spark cluster, we saved our clean data into a csv file. 

# Machine Learning and Modeling

We leveraged spark on databricks for the ML and modeling of this study. THe sample size distribution of our dataset. Our dataset was skewed slightly to larger sample sizes.

 - Number of Records : 23925
 - mean sample size : 2058
 - stddeviation : 2461
 - minimum : 101 NOTE: we dropped statistically insigfigant records so 101 is our smallest possible sample size
 - 25% : 625
 - 50% : 1236
 - 75% : 2496
 - Maximum: 33,186

Our dataset was narrowed down to just question 36 which concentrates on the percentage of people who have an Obese classification. The resulting dataset had 12704 records which is about 1/2 of the overall BRFS dataset. We then conducted a 75-25 split of the dataset so that we could build and train our model. We focused on the stratification field as our analysis point. We then built a random forest model based on the sample size and value for the percentage of the people who have the obese classification. There were a total of 28 unique stratifications possible in our dataset. The model attempted to predict which stratification the percentages and sample sizes would be associated with. Our initial prediction had a very poor accuracy rating of about 26%. We had to revisit this several times and tune the model. 

Obese Dataset stats 
 - Number of Records : 11963
 - mean sample size : 2058
 - stddeviation : 2461
 - minimum : 101
 - 25% : 625
 - 50% : 1236
 - 75% : 2496
 - Maximum: 33,186



```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/staticresponse/AIT_664/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.

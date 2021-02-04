# Food interaction analysis

The purpose of this analysis and data processing is to prepare the food interaction data provided by 
drugBank for automated graph generation using FCA. This would enable to show the food interaction
data in two ways:
- text - in form of a table. Can show more detailed descriptions but connections are hard to find
if there are too many drugs
- graph - with FCA. This should be an additional view option to the table format and would allow the 
user to see the links between selected drugs and their food interactions

This project focuses on preparing the data for the automated graph visualization. The code was written in
*python* and the jupyter notebook files containing the code, results, graphs and explanations are located in the 
`analysis` folder. The following is a summary of the process and the results.

## 1. Analysis

The data was taken from drugbank. I used an sql script to convert the following sql tables to csv: categories, food interactions, drugs and 
analysed the first two. They have the following attributes:

### Categories
![Categories table](plots/category%20table.PNG)

The table has 68860 entries with 6142 unique drug ids and 3606 unique categories. 
The following plot shows the most common categories from this dataset.

![Most frequent categories plot](plots/Most%20frequent%20categories.png)

### Food interactions
![Food interactions table](plots/food%20int%20table.PNG)

This dataset is the most significant one and is the main interest of this project. 
It contains 2388 food interactions with 498 unique food interaction descriptions.

![Most frequent food interactions plot](plots/Most%20frequent%20descriptions.png)

After analysing the data (see the `Food interactions - data analysis & cleaning` file) I gathered the
following findings:
- multiple sentence descriptions, which can be split into separate descriptions
- redundant descriptions which can be removed (ex. 'No food effects.', 'No known food interactions.')

## 2. Data cleaning

In this section, I split each description into separate sentences in the dataset and added them as new rows with the corresponding drug id. In the previous steps I also identified some useless data which I also eliminated (ex. 'No food effects.', 'No known food interactions.'). Finally, I exported the cleaned data to a new csv file.

For the sentence splitting I had to make sure to ignore abbreviations and other not relevant punctuation
marks. I found a suitable python library which I could use with some adjustments. I added a new column 
to my dataset with the newly generated tokens (every token symbolizes one sentence), deleted the old description 
column and expanded the token list according to the linked drug ids.

## 3. Result evaluation
This section evaluates the new, cleaned data retrieved from the previous step. 

![Word count plot](plots/Word%20count%20plot.png)
This plot shows the result of the sentence splitting. The initial data (blue) has a lower rate of short
sentences (measured in words), which is improved by the processed data (orange).

![Frequent food nouns plot](plots/frequent%20food%20nouns.PNG)

   

 
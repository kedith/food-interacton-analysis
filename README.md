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



![Most frequent categories](plots/Most%20frequent%20categories.png)
 
- 498 unique food interaction descriptions
- 2388 food interactions
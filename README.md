# The Aggregation Script

We developed this script to replace the old one (not on github) to make it easier to support and use. Also we designed the aggregation rules from scratch. 

## Aggregation rules

### 1. Select Multiple Questions

- if only one value, return it
- if two values, see if there is a full consensus. if yes, return the value, otherwise - no consensus (NC)
- if three or more values, return the majority ($\geq50%$) answer

### 2. Numeric Questions

- if just one value return NA
- if two values, see if there is a full consensus. if yes, return the value, otherwise - no consensus (NC)
- if three or more return mean and median

### 3. Select One Categorical Questions

- turn the column into several columns with one-hot encoding
- apply the rules for select multiple questions

### 4. Select One Ordinal Questions

- convert the options into numbers
- apply the rules for numeric questions
- convert back

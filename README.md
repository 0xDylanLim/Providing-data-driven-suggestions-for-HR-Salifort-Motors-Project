# Providing-data-driven-suggestions-for-HR-Salifort-Motors-Project

The HR department at Salifort Motors wants to take some initiatives to improve employee satisfaction levels at the company. They collected data from employees, but now they don’t know what to do with it. They refer to you as a data analytics professional and ask you to provide data-driven suggestions based on your understanding of the data. They have the following question: what’s likely to make the employee leave the company?

The following dataset is given:

![Screenshot 2023-06-21 053813](https://github.com/0xDylanLim/Providing-data-driven-suggestions-for-HR-Salifort-Motors-Project/assets/98394792/cc743b5d-2167-42a3-bd59-2eaf6610aa7f)

Objective: Analyse the data and build a model that predicts whether or not an employee will leave the company.

The first step of the EDA process is to examine and understand the data. This involves obtaining tables of information about the data, then checking for missing values, duplicates, and outliers.

The next part of the EDA process is data exploration through visualizations. The following visualisations are made to further visualize the relationship between the variables in the data. These have been created using Python seaborn and matplotlib. 

The new variable tenure stayed = 0, is the employees who stayed compared to tenure_left = 1, and a boxplot was created.

![Screenshot 2023-06-21 212542](https://github.com/0xDylanLim/Providing-data-driven-suggestions-for-HR-Salifort-Motors-Project/assets/98394792/7b413cf7-07ec-494c-be14-8f56d4788504)

Findings:
1. People who left the company worked: A. worked fewer hours than their peers on the same n.o projects and B. worked much more hours.
2. Everyone with 7 projects left, and employees with 6 projects who worked higher hours also left.
3. The optimal number of projects seems to be 3-4 because the ratio of left : stayed is very small.
4. assuming 40 hours per week = 166.67 hours per month. Employees that worked on 2 projects seem to be overworked.

This graph shows hours worked compared to the satisfaction levels of those that left and stayed.

![Screenshot 2023-06-21 213242](https://github.com/0xDylanLim/Providing-data-driven-suggestions-for-HR-Salifort-Motors-Project/assets/98394792/e603553d-a0f0-4e74-bdfd-58d000171d9b)

Findings:
1. Satisfaction levels were close to zero for those that left and worked 240 - 312 hours per month.
2. There is another group that left with lower hours. This could indicate that they feel pressure to work more than their peers, hence lowering their satisfaction levels.
3. Satisfaction levels were highest in those who left when hours ranged between 210 - 280 hours per month.









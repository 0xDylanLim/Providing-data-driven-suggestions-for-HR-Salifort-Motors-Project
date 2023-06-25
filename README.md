# Providing-data-driven-suggestions-for-HR-Salifort-Motors-Project

The HR department at Salifort Motors wants to take some initiatives to improve employee satisfaction levels at the company. They collected data from employees, but now they don’t know what to do with it. They refer to you as a data analytics professional and ask you to provide data-driven suggestions based on your understanding of the data. They have the following question: what’s likely to make the employee leave the company?

The following dataset is given:

![Screenshot 2023-06-21 053813](https://github.com/0xDylanLim/Providing-data-driven-suggestions-for-HR-Salifort-Motors-Project/assets/98394792/cc743b5d-2167-42a3-bd59-2eaf6610aa7f)

Objective: Analyse the data and build a model that predicts whether or not an employee will leave the company.

The first step of the EDA process is to examine and understand the data. This involves obtaining tables of information about the data, then checking for missing values, duplicates, and outliers.

![Screenshot 2023-06-22 000827](https://github.com/0xDylanLim/Providing-data-driven-suggestions-for-HR-Salifort-Motors-Project/assets/98394792/2df434f3-dc46-449b-86c8-c5bb049209ec)

This table shows the duplicates, however, there is no need to remove them as it seems unlikely that it would be due to human error. This is because the values vary despite having similar values.

![Screenshot 2023-06-22 000648](https://github.com/0xDylanLim/Providing-data-driven-suggestions-for-HR-Salifort-Motors-Project/assets/98394792/2f2f2a35-d833-4059-bb08-3454700dd5bb)

This shows that there are outliers, hence we identify how many rows in 'tenure' contain outliers. 

![Screenshot 2023-06-22 001103](https://github.com/0xDylanLim/Providing-data-driven-suggestions-for-HR-Salifort-Motors-Project/assets/98394792/20261650-5680-402f-be26-0083d6ecd29c)

The next part of the EDA process is data exploration through visualizations. The following visualizations are made to further visualize the relationship between the variables in the data. These have been created using Python Seaborn and Matplotlib. 

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

Next, we create a boxplot and histogram on the satisfaction levels by tenure

![Screenshot 2023-06-22 001419](https://github.com/0xDylanLim/Providing-data-driven-suggestions-for-HR-Salifort-Motors-Project/assets/98394792/0aabec5c-3d4a-44c2-bada-a86fc19143f8)

Findings:
1. employees who left either have: A. dissatisfied with short tenure OR B. satisfied with longer tenure
2. 4-year tenure showed very low satisfaction for people who left.
3. longest tenured employees didn't leave
4. very few longer-tenured employees, possibly due to higher ranking and paid employees

![Screenshot 2023-06-22 011125](https://github.com/0xDylanLim/Providing-data-driven-suggestions-for-HR-Salifort-Motors-Project/assets/98394792/82b09fc0-820b-4554-8011-e3af4954c3b5)

The mean and median for those who left are much lower than those who didn't in terms of satisfaction levels.

![Screenshot 2023-06-22 011306](https://github.com/0xDylanLim/Providing-data-driven-suggestions-for-HR-Salifort-Motors-Project/assets/98394792/0aa9f720-3f6e-4842-9000-94017532d3a2)

By creating a histogram of salary vs tenure, we can differentiate if salary plays a large role.

We can see if there is a correlation between long hours and receiving high evaluation scores via scatterplot.

![Screenshot 2023-06-22 011551](https://github.com/0xDylanLim/Providing-data-driven-suggestions-for-HR-Salifort-Motors-Project/assets/98394792/976ab55b-78d1-483d-a485-c695cdda8af7)

Findings:
1. two groups: 1. overworked employees who performed well AND 2. under avg hour employees with lower evaluation scores
2. appears to be a correlation between hours worked and evaluation score.
3. most employees worked > 167 hours.

![Screenshot 2023-06-22 012721](https://github.com/0xDylanLim/Providing-data-driven-suggestions-for-HR-Salifort-Motors-Project/assets/98394792/722a3397-3d1b-4fc3-8efb-a2b4fca4a345)

Whilst investigating monthly hours by promotions we find:
1. very few employees who were promoted in the last five years left
2. very few employees who worked the most hours were promoted
3. all of the employees who left were working the longest hours

![Screenshot 2023-06-22 012938](https://github.com/0xDylanLim/Providing-data-driven-suggestions-for-HR-Salifort-Motors-Project/assets/98394792/447bb370-7884-4153-bf81-6fef5202570b)

There is no significant difference between departments for people who left.

Next, we will construct a logistic regression model to determine the likelihood that an employee will leave. This is under the assumptions:
- Outcome variable is categorical
- Observations are independent of each other
- No severe multicollinearity among X variables
- No extreme outliers
- A linear relationship between each X variable and the logit of the outcome variable
- Sufficiently large sample size

First, we use one-hot encoding to convert categorical variables to numerical ones. Then create a heatmap to consider variables of interest.

![Screenshot 2023-06-22 140521](https://github.com/0xDylanLim/Providing-data-driven-suggestions-for-HR-Salifort-Motors-Project/assets/98394792/b7a674bd-73ef-4821-92c2-8d9645449363)

We can visualize the n.o employees across the departments.

![Screenshot 2023-06-25 164906](https://github.com/0xDylanLim/Providing-data-driven-suggestions-for-HR-Salifort-Motors-Project/assets/98394792/72d6133d-8126-4ec6-9cc9-3d99a1a83047)

Next, we must remove the outliers and isolate the outcome variable that we want our model to predict. Consider variables that predict the outcome variable. Then split the data into training and test set.

Ultimately, a confusion matrix is produced.

![Screenshot 2023-06-25 165132](https://github.com/0xDylanLim/Providing-data-driven-suggestions-for-HR-Salifort-Motors-Project/assets/98394792/defa082a-800f-4b65-830e-adc0f66776d3)

When we check the class balance, it shows an 83%-17% split which is not too perfectly balanced and imbalanced.

![Screenshot 2023-06-25 165219](https://github.com/0xDylanLim/Providing-data-driven-suggestions-for-HR-Salifort-Motors-Project/assets/98394792/9b542985-053e-4101-9900-82a86b9bb4de)

Lastly, a classification report is created for the logistic regression model.

![Screenshot 2023-06-25 165308](https://github.com/0xDylanLim/Providing-data-driven-suggestions-for-HR-Salifort-Motors-Project/assets/98394792/d6b7c953-9894-4bdf-92cc-f9abfc46fa66)

The classification report above shows that the logistic regression model achieved a precision of 80%, recall of 83%, f1-score of 80% (all weighted averages), and accuracy of 83%.

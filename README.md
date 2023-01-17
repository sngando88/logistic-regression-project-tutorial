<!-- hide -->
# Logistic Regression Project Tutorial
<!-- endhide -->

- Understand your data
- Follow the cleaning instructions
- Model your data using Logistic Regression
- Optimize your model and save it.

## 🌱  How to start this project

You will not be forking this time, please take some time to read these instructions:

1. Create a new repository based on [machine learning project](https://github.com/4GeeksAcademy/machine-learning-python-template/generate) by [clicking here](https://github.com/4GeeksAcademy/machine-learning-python-template).
2. Open the recently created repository on Gitpod by using the [Gitpod button extension](https://www.gitpod.io/docs/browser-extension/).
3. Once Gitpod VSCode has finished opening, you start your project following the Instructions below.

## 🚛 How to deliver this project

Once you are finished creating your logistic regression model, make sure to commit your changes, push to your repository and go to 4Geeks.com to upload the repository link.

## 📝 Instructions

**Bank Marketing Campaign**:

Business Understanding:

Term deposits allow banks to hold money for an specific amount of time, which allows the bank to use that money for better investments. The marketing campaigns for this product were based on phone calls. Often, more than one contact to the same client was required, in order to know if the term deposit would be or not subscribed.

Problem Description:

Portuguese bank is having a decrease in its revenue, so they want to be able to identify existing clients that have a higher chance to subscribe to a term deposit. This will allow the bank to focus marketing efforts on those clients and avoid wasting money and time on clients that will probably not subscribe, as they want to increase their revenue.

To approach this problem, we will create a classification algorithm that helps predict if a client will subscribe or not to a term deposit.


**Step 1:**

The dataset can be found in this project folder as 'bank-marketing-campaign-data.csv' file. You are welcome to load it directly from the link (`https://raw.githubusercontent.com/4GeeksAcademy/logistic-regression-project-tutorial/main/bank-marketing-campaign-data.csv`), or to download it and add it to your data/raw folder. In that case, don't forget to add the data folder to the .gitignore file.

Only a labeled dataset has been provided because we want you to practice your modeling skills. 
There is no need for you to make the predictions as no test set has been provided, however, make sure to divide your data in train and validation sets to evaluate your model performance, because the bank would request a reliable model for them to use it.

This time we want you to focus on the modeling and optimization part, so we will give you some hints for the cleaning process.

Time to work on it!

**Step 2:**

Make some quick exploratory data analysis. Check what categories are in each feature.

Is your data balanced or imbalanced? 

You can use a barplot to visualize your target variable in order to verify if it is balanced or not.

If you don't remember how to deal with imbalanced datasets, you can go to your statistics class and look for the tips in the specific paragraph of imbalanced datasets: https://github.com/4GeeksAcademy/machine-learning-content/blob/master/02-6d-stats/hypothesis-testing.ipynb 

> Hint: Choose your evaluation metric correctly if your data is imbalanced. 

**Step 3:**

Meaning of each attribute:

1. Age (numerical).

2. Job: Type of Job (categorical).

3. Marital: marital status (categorical).

4. Education: (categorical).

5. Default: has credit in default? (categorical).

6. Housing: has a housing loan? (categorical).

7. Loan: has a personal loan? (categorical).

8. Contact: contact communication type (categorical).

9. Month: last contact month of the year (categorical).

10. day_of_week: last contact day of the week (categorical).

11. Duration: last contact duration, in seconds (numerical).

Important note: this output highly affects the output target (if duration = 0, then y = 'no'). Yet, the duration is not known before a call is performed. Also, after the end of the call, y is obviously known. Consider if you should include it or not for a realistic predictive model.

12. campaign: number of contacts performed during this campaign and for this client (numerical)

13. pdays: number of days that passed by after the client was last contacted from a previous campaign (numeric; 999 means the client was not previously contacted)

14. previous: number of contacts performed  before this campaign and for this client (numerical)

15. poutcome: outcome of the previous marketing campaign (categorical)

Important note: this attribute has three categories: 'failure', 'success' and 'non-existent'. 86% of the data falls into the 'non-existent' category.

16. emp.var.rate: employment variation rate - quarterly indicator (numeric)

17. cons.price.idx: consumer price index- monthly indicator (numeric)

18. cons.conf.idx: consumer confidence index - monthly indicator (numeric)

19. euribor3m: euribor 3 month rate: - daily indicator(numeric)

20. nr.employed: number of employees - quarterly indicator (numeric)

Target variable: 

21. y: has the client subscribed to a term deposit?   


Hint for the cleaning process:

1. The dataset has no null values, but make sure to drop any duplicated rows.

2. There are some features that include unknown values.

- In the categorical features, replace the unknown category with the most frequent value. 

- In the numerical features, replace the unknown values with the mean.

>Creating a function that works in all those categories is a good practice.

3. Check for outliers. There are three features showing outliers. Eliminate all outliers using the IQR to establish upper and lower bounds.   

4. Convert age into categorical data by creating age-groups of ten years.

>Use .cut in pandas and use the following bins: [10,20,30,40,50,60,70,80,90,100]. 

5. Insert categories 'basic.9y','basic.6y','basic4y' into 'middle_school'

6. Convert the target variable into binary

7. Encode categorical features

8. Scale your data

9. Feel free to select the features that you consider important for the model.

**Step 4:**

Time to build your model!

1. Separate your target variable from the predictors

2. Choose how to divide your data to evaluate the performance of your model

3. Build a first Logistic Regression model with default hyperparameters.

4. Hypertune your model to improve your results.

5. Use the app.py to create a pipeline

6. Save your final model in the 'models' folder.

7. In your README file write a brief summary.

8. Deliver your repo link.

Solution guide: https://github.com/4GeeksAcademy/logistic-regression-project-tutorial/blob/main/cleaning-solution.ipynb

# **Optimizing Employee Retention for Salifort Motors**
# Overview
`Salifort Motors`, a fictional alternative energy vehicle manufacturer, has taken a proactive step by seeking data-driven insights to enhance employee satisfaction levels within the company. The Human Resources (HR) department has collected extensive data from employees, creating an invaluable resource that, when harnessed effectively, can guide strategic initiatives to mitigate turnover. The goal of this capstone project is, to conduct a thorough `analysis` of the HR data collected by Salifort Motors and develop a robust `predictive` model capable of foreseeing whether an employee is likely to `leave the company`. The `PACE` framework was used to structure and complete this project. - **P**lan - **A**nalyze - **C**onstruct - **E**xecute.

# Business Understanding
The HR department, recognizing the impact of high turnover on operational stability and costs, seeks to leverage data-driven insights to proactively enhance employee satisfaction and retention. The project aims to discover data-driven insights to inform strategic decisions, improve the working environment, and ultimately `reduce employee turnover`. By viewing data as a strategic asset, Salifort Motors aims to optimize HR practices, placing employees at the center of organizational success.

# Data Understanding
The dataset was collected by the HR department, capturing a wide range of information pertaining to employees' professional activities, evaluations, projects, tenure, salaries, and overall satisfaction levels. Understanding the significance of each variable and the relationship between them were discoved in `Exploratory data analysis`. The scatter plot below shows the relationship between average_monthly_hours and promotion_last_5years, which was used to examine whether employees who worked very long hours were promoted in the last five years. The plot shows that very few employees who worked the most hours were promoted and all of the employees who left were working the longest hours.

![Scatter plot of average_monthly_hours v tip amount](images/hours_promotion.png)

A correlation heatmap was also constructed to confirm that the number of projects, monthly hours, and evaluation scores all had some positive correlation with each other, and whether an employee leaves was negatively correlated with their satisfaction level.

# Modeling and Evaluation
In the comparative analysis between logistic regression and tree-based models (random forest and xgboost) for predicting employee turnover, XGBoost emerged as the most effective model based on its superior performance on the validation dataset. The `XGBoost` model achieved AUC of 93.9%, precision of 89.3%, recall of 89.9%, f1-score of 89.6%, and accuracy of 96.5%, on the test set. In the final model, `last_evaluation`, `number_project`, `tenure`, `salary_low` and `overworked` had the highest importance, in that order. These variables were most helpful in predicting the outcome variable, **left**.


![Feature Importance of XGBoost](images/feature_importance.png)

# Conclusion
The data-driven analysis has provided valuable insights into the factors influencing employee turnover at Salifort Motors. The XGBoost model, outperforming other models, has identified critical predictors such as last_evaluation, number_project, tenure, salary levels (especially "salary_low"), and overwork status. Recomendations were made such as considering project delegation, workload balancing, and resource allocation adjustments to reduce overwork. Explore the possibility of predicting other critical factors such as employee performance scores or satisfaction levels and assess whether these alternative targets provide meaningful insights into employee turnover and satisfaction, could be the next steps.

----
----

# Installation
- Clone this repo to your computer. `git clone` <[repository_url](https://github.com/farahdahir/Salifort_Motors)>
- Navigate to the project directory: using `cd Salifort_Motors`
- Install the required libraries from the `requirements.txt` file using pip: `pip install -r requirements.txt`

# Reviewing the Project
The project has 3 files and 2 folders. The `salifort_motors.ipynb` is the main notebook for the project. It is divided into sections alining with the PACE frame-work Plan, Analyse, Construct and Execute. For the Construct stage some code cells are commented out, where the predictive models are fitted to save you time. This does not affect the overral work flow of the project, since the models were fitted and saved as pickle files.

The project also includes an images folder and data folder. Remember all datasets are stored in the data folder along with the pickled models.

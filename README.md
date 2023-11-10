# **Optimizing Employee Retention for Salifort Motors**
# Overview
`Salifort Motors`, a fictional alternative energy vehicle manufacturer, has taken a proactive step by seeking data-driven insights to enhance employee satisfaction levels within the company. The Human Resources (HR) department has collected extensive data from employees, creating an invaluable resource that, when harnessed effectively, can guide strategic initiatives to mitigate turnover. The goal of this capstone project is, to conduct a thorough `analysis` of the HR data collected by Salifort Motors and develop a robust `predictive` model capable of foreseeing whether an employee is likely to `leave the company`. The `PACE` framework was used to structure and complete this project. - **P**lan - **A**nalyze - **C**onstruct - **E**xecute.

# Business Understanding
The project tackled the issue of supporting New York City taxi drivers in achieving a `sustainable income` by understanding the aspects that motivate riders to give tips. Although the model can forecast whether a rider will be a generous tipper `gives > 20%`, future endeavors might include estimating the specific tip amount or including more data on a rider's tipping track record for a more comprehensive solution.

# Data Understanding
Data used in the project was from the New York City Taxi and Limousine Commission, sourced from NYC.gov, comprising around 22,699 distinct taxi journeys with 18 features, covering trip duration, destination, vendor details, tolls, and payment method. `Exploratory data analysis` revealed insights such as the relationship between features. The Bar plot below shows the relationship between passenger count and tip amount, excluding 0, rides with 5 passengers had the highest average tip amount ($1.87), followed by rides with 2 passengers ($1.86). It was clear that the number of passengers had some influence on the average tip amount, with larger groups tending to leave slightly higher tips.


![Bar plot of passenger count v tip amount](images/passengerCount_tipAmount.png)

A `two-sample t-test` was also carried out that revealed there was a `statistically` significant `difference` in the average total fare amount between customers who use credit cards and customers who use cash. Purpose of the A/B test was to find ways to generate more revenue for taxi cab drivers. 

# Modeling and Evaluation
For trip duration, a `Linear Regression` was constructed that achieved an R-squared value of 0.7319, which suggests that it explains approximately 73% of the variance in the dependent variable **trip duration**. And as for predicting generous tippers, `XGBoost` model that achieved precision of 70%, recall of 48%, f1-score of 57%, and accuracy of 74%, on the test set outperformed the RandomForest Model constructed before. In the final model, `duration`, `trip_distance`, `fare_amount`, `extra` and `passenger_count` had the highest importance, in that order. These variables were most helpful in predicting the outcome variable, **generous**.


![Accuracy score of the models](images/importance_plot.png)

# Conclusion
Type II errors `false negative` were more common in the final predictive model. For this use case, this was more desirable, because it's better for a driver to be pleasantly surprised by a generous tip when they weren't expecting one than to be disappointed by a low tip when they were expecting a generous one. The model has the potential to assist taxi drivers in anticipating whether they will receive generous tips, but it does not provide a detailed understanding of how each variable affects the exact tip amount. In the future, enhancing the model with additional data related to a rider's historical tipping patterns could prove advantageous in addressing the stakeholder's business challenges.

----
----

# Installation
- Clone this repo to your computer. `git clone` <[repository_url](https://github.com/farahdahir/Automatidata)>
- Navigate to the project directory: using `cd Automatidata`
- Install the required libraries from the `requirements.txt` file using pip: `pip install -r requirements.txt`

# Reviewing the Project
The project follows has 3 files and 2 folders. The `automatidata.ipynb` is the main notebook for the project. It is divided into sections aigning with the PACE frame-work Plan, Analyse, Construct and Execute. For the Construct stage some code cells are commented out, where the predictive models are fitted to save you time. This does not affect the overral work flow of the project, since the models were fitted and saved as pickle files.

The project also includes an images folder and data folder. Remember all datasets are stored in the data folder along with the pickled models.

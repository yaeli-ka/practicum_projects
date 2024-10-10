Predictive Analytics for Customer Churn for Telecom Company

Telecom operator "TeleHome" wants to reduce a customer churn. To do this, it'll start offering promo codes and special conditions to everyone planning to discontinue their service. To identify such users in advance, "TeleHome" needs a model that can predict whether a subscriber will terminate their contract. The operator's team has collected personal data about some clients, information on their tariffs, and services. Our task is to train a model on this data to predict customer churn.

Services description:

The operator provides two main types of services:
* Landline phone service. A phone can be connected to several lines simultaneously.
* Internet. The connection can be of two types: via a telephone line (DSL, short for digital subscriber line) or a fiber optic cable.

Also available are such services as:
* Internet security: antivirus (DeviceProtection) and blocking unsafe websites (OnlineSecurity);
* Dedicated technical support line (TechSupport);
* Cloud storage for data backup (OnlineBackup);
* Streaming TV and a movie catalog.
* Clients can pay for services monthly or sign a contract for 1–2 years. It's possible to pay the bill in various ways, as well as to receive an electronic check.

Data description:

The data consists of several files obtained from different sources:
* contract_new.csv — contract information;
* personal_new.csv — client's personal data;
* internet_new.csv — information about internet services;
* phone_new.csv — information about telephony services.

File contract_new.csv:
* customerID — subscriber identifier;
* BeginDate — contract start date;
* EndDate — contract end date, **based on this feature, we'll generate our target feature (if the client has left, a date is set)**;
* Type — type of payment: once a year or monthly;
* PaperlessBilling — electronic billing agreement;
* PaymentMethod — payment type;
* MonthlyCharges — monthly expenses;
* TotalCharges — total subscriber expenses.

File personal_new.csv:
* customerID — user identifier;
* gender — gender of customer;
* SeniorCitizen — whether the subscriber is a senior citizen;
* Partner — whether the subscriber has a spouse;
* Dependents — whether the subscriber has children.

File internet_new.csv:
* customerID — user identifier;
* InternetService — type of connection;
* OnlineSecurity — blocking unsafe sites;
* OnlineBackup — cloud storage for data backup;
* DeviceProtection — antivirus;
* TechSupport — dedicated technical support line;
* StreamingTV — streaming television;
* StreamingMovies — movie catalog.

File phone_new.csv:
* customerID — user identifier;
* MultipleLines — connecting a phone to multiple lines simultaneously.

The contract information is up to date as of February 1, 2020.

Work plan:

We face to a binary classification task: we have to predict the customer's churn.

The target feature will be the information stored in the EndDate field: it indicates whether the contract is concluded or not.

We'll use ROC-AUC metric as the main metric to assess the model's quality.
For model interpreation we'll use the a confusion matrix with the Accuracy metric and also feature importances.

1. Load the data and get acquainted with it.
2. Preprocess data for each dataframe and select the necessary features.
3. Concatenate the data into a single dataframe.
4. Do an exploratory data analysis, including a correlation analysis. If necessary, generate new features.
5. Prepare the data for training models.
6. Train different models, with hyperparameter tuning, to select the best one.
7. Check the model's quality on the test sample.
8. Write the final conclusions.

# Car Insurance Claims Classification
**Author:** Lerato Matlala


## **Business Problem:**

The business problem at hand revolves around a classification task in the insurance industry. Specifically, the objective is to predict whether a customer will make an insurance claim or not based on a comprehensive dataset containing various customer attributes and historical data related to insurance claims. This classification problem is critical for insurance companies as it directly impacts decision-making processes, risk assessment, and resource allocation.

**Stakeholders:**

Insurance Company: The primary stakeholder is the insurance company itself. They are keenly interested in accurate predictions to optimize various aspects of their operations, including premium pricing, underwriting, claims processing, and risk management. Accurate predictions help them reduce financial risks, streamline operations, and enhance profitability.

**Source of Data:**

The dataset used in this analysis is from Kaggle. It represents annual car insurance data, offering insights into real customer behaviors and interactions with their insurance products.

**Description of Data:**

The dataset consists of the following key attributes:
  - **Outcome Column:** The primary target variable is the "outcome" column, which indicates whether a customer has claimed from their car       insurance. It uses binary values, with "1"       indicating a claim and "0" indicating no claim. This forms the basis of a classification           problem.
  - **Features:** There are 18 features derived from practical world scenarios and logged by the company. These features encompass a wide       range of customer attributes and interactions   with car insurance.
  - **Observations:** The dataset contains a total of 10,000 observations or rows, each corresponding to a specific customer. These observations provide valuable insights into individual customer behaviors and characteristics.

## Method
### 1. Exploratory and Explanatory Data Analysis
The initial phase involves exploring the dataset to understand its structure, identify patterns, and detect any anomalies. EDA and ExDA help us visualize relationships between variables, discover trends, and prepare the data for modeling. This phase guides feature selection, and engineering, and prepares us for model construction.

#### Univariate Analysis

Univariate analysis focused on the exploration of individual features within the claims dataset. This analysis encompassed several data visualization techniques. Histograms were used to visualize the distribution of numerical features, including Credit Score and Annual Mileage. Additionally, count plots were used to provide valuable insights into their respective distributions. This univariate analysis aids in understanding the characteristics and patterns present within the data.

Below are examples of some univariate analysis that was done:

<img width="812" alt="image" src="https://github.com/LeratoMatlala1/Car-Insurance-Claims-Classification/assets/138568742/bb407289-3696-459c-a62d-632e923a81ab">

From the above we can note that:

  - The majority of customers fall into the "26-39" and "40-64" age groups, with similar counts.
  - There is a roughly equal distribution between "16-25" and "65+" age groups.
  - The dataset is nearly balanced in terms of gender, with slightly more females (4998) than males (4982).
  - The majority of customers belong to the "majority" race category, significantly outnumbering the "minority" category.
  - The majority of vehicles are categorized as "before 2015," with significantly more customers falling into this category compared to "after 2015."

<img width="813" alt="image" src="https://github.com/LeratoMatlala1/Car-Insurance-Claims-Classification/assets/138568742/ca248daf-5b35-4012-a47f-b0dafd5224ff">

From the above, we can note that:

  - The majority of customers (6964) own a vehicle, while a smaller portion (3016) do not own a vehicle.
  - The dataset is almost evenly split between married (4980) and unmarried (5000) customers.
  - Specific mileage values like 11,000, 12,000, and 13,000 appear more frequently in the data.
  - There are 6862 customers with an outcome of 0 (not claimed) and 3118 policyholders with an outcome of 1 (claimed).

#### Multivariate Analysis

The objective of multivariate analysis was to uncover associations and dependencies between pairs of variables within the claims dataset. To achieve this, a correlation heatmap was constructed to visualize the relationships among numerical attributes. This heatmap facilitated the identification of potential collinearities and provided insights into how variables interacted with each other. This multivariate analysis contributes to a deeper understanding of the interplay between various features.

Below is an example of some multivariate analysis that was done:
<img width="1100" alt="image" src="https://github.com/LeratoMatlala1/Car-Insurance-Claims-Classification/assets/138568742/4c9e0e1a-1547-48f1-936f-d77497521480">

<img width="669" alt="image" src="https://github.com/LeratoMatlala1/Car-Insurance-Claims-Classification/assets/138568742/0af5f87f-4300-4098-86d6-2d7739688fd9">

Some of the Key Insights from the above visuals are:

  - The negative correlation (-0.2) between credit score and insurance claims suggests that individuals with higher credit scores are less likely to file insurance claims.
  - The negative correlation (-0.26) between marital status and insurance claims suggests that married individuals are less likely to make insurance claims
  - The positive correlation (0.18) between annual mileage and insurance claims indicates that individuals who drive more miles are slightly more likely to make insurance claims. Higher         mileage might lead to an increased risk of accidents or incidents.
  - These variables (speeding violations, DUIs, and past accidents) all have positive correlations with insurance claims. This suggests that individuals with a history of speeding         violations, DUIs, or past accidents are more likely to file insurance claims
  - There is a strong negative correlation (-0.44) between annual mileage and marital status ('MARRIED'). This suggests that married individuals tend to have lower annual mileage, which could be due to shared commuting or family-related travel.
  - There is a strong positive correlation (0.36) between speeding violations and DUIs. This suggests that individuals with a history of speeding violations are more likely to have DUIs as well, indicating risky driving behavior.

## Model Evaluation Metrics
Multiple machine learning models were evaluated to predict insurance claims based on customer data. The models considered include K-Nearest Neighbors (KNN), Decision Trees, and Random Forests. For each of these models, both their original configurations and tuned hyperparameter settings were assessed to determine their predictive performance. Additionally, Principal Component Analysis (PCA) was applied to the data, allowing for an evaluation of the models' performance when using reduced-dimensional representations of the features. This  evaluation process aimed to identify the most effective model for accurately classifying customers into claim or no-claim categories while considering various modeling approaches and data transformations.

Below is the results of the accuracies of all the models:
<img width="730" alt="image" src="https://github.com/LeratoMatlala1/Car-Insurance-Claims-Classification/assets/138568742/7c6a36d8-6ee3-49fb-9158-79fe574afc16">


The primary objective for the insurance company is to correctly identify clients who are likely to make claims (class 1) while avoiding unnecessary payments to clients who do not make claims (class 0). This is where precision plays a crucial role.

Precision for class 1 is a key metric for this business problem. The Tuned Random Forest Model has a high precision of 77% for predicting claims. This means that when the model predicts a client is likely to claim, it is correct 77% of the time. High precision is important for minimizing the incorrect prediction of claims, which can result in unnecessary payouts and financial losses.

Therefore, based on these metrics, the Random Forest model with tuned hyperparameters outperforms the other models in terms of precision for class 1.It has the highest accuracy (85%) among all the models, which means it correctly predicts the likelihood of clients claiming or not claiming insurance the most accurately.

By accurately distinguishing between claims and non-claims, the model assists the insurance company in effective risk management. It enables the company to allocate resources and assess premiums more accurately, ensuring that insurance claims are paid out only to those who genuinely need them. This contributes to improved profitability and financial stability. Furthermore, the model's ability to make accurate predictions helps in optimizing decision-making processes within the insurance company. It allows for informed and data-driven decisions related to underwriting, policy pricing, and claims processing. This, in turn, enhances the overall efficiency of the insurance operations.

## Recommendations

- **Optimize Premium Pricing:**

The insights generated by the "Tuned Random Forest Model" can be used to optimize premium pricing strategies. The model's accurate predictions can be leveraged to assess risk more precisely, allowing the company to offer competitive premiums to low-risk clients and adjust pricing for higher-risk clients accordingly. This data-driven approach can improve competitiveness and profitability.

- **Enhance Claims Processing Efficiency:**

The model can be implemented within the claims processing workflow to enhance efficiency. By using the model to prioritize claims based on their likelihood of being genuine, the insurance company can expedite the processing of legitimate claims, ensuring that clients in need receive prompt support. This reduces administrative overhead and allows claims adjusters to focus on critical cases.

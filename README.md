# Titanic Data Analysis

### Dashboard Link : https://app.powerbi.com/groups/me/reports/1beb9920-a3c1-4df6-9655-20750c932522/7ae56c4777a236ee53f2?experience=power-bi

![image_2024-08-03_230501463](https://github.com/user-attachments/assets/eaffe1a1-d7db-4660-bda5-f00cc1d1ecfc)
#### Project Overview
The project was undertaken to provide deeper insights into the Titanic incident. The goal was to understand the demographics of those affected, analyze survival rates, and identify factors that influenced survival. This analysis can help shed light on the tragic event and highlight patterns within the data.

#### Data Sourcing
The data for this project was sourced from publicly available datasets on the Titanic disaster. The dataset includes various details such as passenger id, ticket information, and survival status etc. The data was extracted and downloaded in Excel format for further analysis.

#### Data Cleaning Process
The columns having null values are: Age, Cabin, Embarked. They need to be filled up with appropriate values later on.

#### Features: The titanic dataset has roughly the following types of features:

* Categorical/Nominal: Variables that can be divided into multiple categories but having no order or priority. 
Eg. Embarked (C = Cherbourg; Q = Queenstown; S = Southampton)
* Binary: A subtype of categorical features, where the variable has only two categories. 
Eg: Sex (Male/Female)
* Ordinal: They are similar to categorical features but they have an order(i.e can be sorted). 
Eg. Pclass (1, 2, 3)
* Continuous: They can take up any value between the minimum and maximum values in a column. 
Eg. Age, Fare
* Count: They represent the count of a variable. 
Eg. SibSp, Parch
Useless: They don’t contribute to the final outcome of an ML model. Here, PassengerId, Name, Cabin and Ticket might fall into this category.

#### Power Query
The data was finally updated to PowerBi for analysis and visualization The following insights were drawn from the data:

![sex survival](https://github.com/user-attachments/assets/ecb39ab9-ad7f-4c6e-9c7f-f3406f446a72)
Just by observing the graph, it can be approximated that the survival rate of men is around 20% and that of women is around 75%. Therefore, whether a passenger is a male or a female plays an important role in determining if one is going to survive.

![HeatMap](https://github.com/user-attachments/assets/0f009c80-e546-429d-9339-ccfdd75e31f6)

It helps in determining if higher-class passengers had more survival rate than the lower class ones or vice versa. Class 1 passengers have a higher survival chance compared to classes 2 and 3. It implies that Pclass contributes a lot to a passenger’s survival rate.

![Violin Chart](https://github.com/user-attachments/assets/7c9beb9e-890d-451b-8c7d-f0f80d37a087)
This graph gives a summary of the age range of men, women and children who were saved. The survival rate is –  

* Good for children.
* High for women in the age range 20-50.
* Less for men as the age increases.
Since Age column is important, the missing values need to be filled, either by using the Name column (ascertaining age based on salutation – Mr, Mrs etc.) or by using a regressor. 
After this step, another column – Age_Range (based on age column) can be created and the data can be analyzed again.

![ribbon](https://github.com/user-attachments/assets/8019fcf1-f0fc-429b-a911-ea82ec6d18ce)
Fare denotes the fare paid by a passenger. As the values in this column are continuous, they need to be put in separate bins(as done for Age feature) to get a clear idea. It can be concluded that if a passenger paid a higher fare, the survival rate is more.

![pclass](https://github.com/user-attachments/assets/739c36f6-baf5-42ae-9906-ac5c3d30064f)
Some notable observations are: 

Majority of the passengers boarded from S. So, the missing values can be filled with S.
Majority of class 3 passengers boarded from Q.
S looks lucky for class 1 and 2 passengers compared to class 3.

#### Conclusion :  

The columns that can be dropped are: 
PassengerId, Name, Ticket, Cabin: They are strings, cannot be categorized and don’t contribute much to the outcome. 
Age, Fare: Instead, the respective range columns are retained.
The titanic data can be analyzed using many more graph techniques and also more column correlations, than, as described in this article.
Once the EDA is completed, the resultant dataset can be used for predictions.

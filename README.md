# Applying supervised learning to predict student dropout rate

In this project, we will examine student data and use supervised learning techniques to predict whether a student will drop out. In the education sector, retaining students is vital for the institution's financial stability and for students’ academic success and personal development. A high dropout rate can lead to significant revenue loss, diminished institutional reputation, and lower overall student satisfaction. 

While this project is focused on predicting student dropout in the education sector, the principles and methodologies applied are versatile and extend to various industries:

Healthcare: Predicting patient dropouts from treatment programmes based on demographics, treatment history, and health metrics to improve patient adherence and outcomes
Finance: Forecasting customer churn in banking and financial services by analysing transaction history, customer engagement, and financial behaviour to enhance customer retention strategies
Telecommunication: Identifying customers at risk of switching service providers by analysing usage patterns, customer service interactions, and billing information in order to tailor retention offers
Retail: Predicting customer attrition by examining purchase history, engagement with marketing campaigns, and customer satisfaction scores to design targeted loyalty programmes.

# Business context
Ready Group specialises in providing educational services and resources to students and professionals across various fields. The company's primary focus is on enhancing learning experiences through a range of services, including online courses, tutoring, and educational consulting. By leveraging cutting-edge technology and a team of experienced educators, Ready Group aims to bridge the gap between traditional learning methods and the evolving needs of today's learners.

Ready Group serves its university partners by establishing strategic partnerships to enhance the universities’ global reach and diversity. It supports the universities in their efforts to attract international students, thereby enriching the cultural and academic landscape of their campuses. It works closely with university faculty and staff to ensure that the universities are prepared and equipped to welcome and support a growing international student body. Its partnership with universities also offers international students a seamless transition into their chosen academic environment. Ready Group runs several International Study Centres across the UK and Dublin, in partnership with universities, with the aim of preparing a pipeline of talented international students from diverse backgrounds for degree study. These centres help international students adapt to the academic, cultural, and social aspects of studying abroad. This is achieved by improving conversational and subject-specific language skills and academic readiness before students progress to a full degree programme at university. 

Through its comprehensive suite of services, it supports learners and universities at every stage of their educational journey, from high school to postgraduate studies. Its approach is tailored to meet the unique needs of each learner, offering personalised learning paths and flexible scheduling options to accommodate various learning styles and commitments.

Ready Group's services are designed to be accessible and affordable, making quality education a reality for many individuals. By focusing on the integration of technology and personalised learning, the company aims to empower learners to achieve their full potential and succeed in their academic and professional pursuits. Ready Group is at the forefront of transforming how people learn and grow through its dedication to innovation and excellence.

Ready Group has provided you with one data set: course-level data set.

# Objective
To apply advanced machine learning techniques to create a predictive model for student dropout. This project will involve comprehensive data exploration, preprocessing, and feature engineering to ensure high-quality input for the models. You will employ and compare multiple predictive algorithms - XGBoost and neural network-based model, to determine the most effective model for predicting student dropout.

# Solution
![image](https://github.com/user-attachments/assets/3a1937f3-86dc-4fba-b9b1-9b1b364faf31)

![image](https://github.com/user-attachments/assets/ba6e2c68-a986-4ccc-aa21-8ede617d69a7)

* learner_df has 2 features with nulls
* learner_extended_df has 4 features with nulls

![image](https://github.com/user-attachments/assets/5b37b35a-d8f8-4d75-ba73-8f5fcd3b6c22)

![image](https://github.com/user-attachments/assets/c67be953-c65a-4483-aae6-fa5ba94ebb15)

![image](https://github.com/user-attachments/assets/d8134a2b-485c-4cfb-8e8b-8abacf91f0a7)

### Plot histogram
![image](https://github.com/user-attachments/assets/a56eb0b8-0bb5-4548-a91b-063fca1a766c)

### Box plots
![image](https://github.com/user-attachments/assets/e5040bfb-91ef-4d4f-92dc-824810ca54af)
![image](https://github.com/user-attachments/assets/37c67e68-840f-4e89-a6eb-5d12bb79996c)
![image](https://github.com/user-attachments/assets/985d6c6e-7593-4a89-bfd8-71fd56502374)
![image](https://github.com/user-attachments/assets/199895ba-ccb2-43fe-a1fc-bb91706f61ad)
![image](https://github.com/user-attachments/assets/c087aa51-ff66-43ec-a39f-d82da43ad7df)

## XGBoost
![image](https://github.com/user-attachments/assets/4bd214ef-7164-4ae3-b092-d7ddcb476434)
![image](https://github.com/user-attachments/assets/9e9a014e-3868-4b50-a34c-4d6b7926166d)

![image](https://github.com/user-attachments/assets/0e46ceff-6d9d-4aac-86bb-c2751775525f)
![image](https://github.com/user-attachments/assets/375948d7-87ff-477f-a292-9fa6db2c2a9a)

After dropping colinear features

* XG Boost Basic Model Accuracy: 0.968942731277533
* XG Boost tuned Model Accuracy: 0.9711453744493392
Without dropping multi-colinear features

* XG Boost Basic Model Accuracy: 0.9662995594713656
* XG Boost tuned Model Accuracy: 0.968942731277533

The XGBoost basic model predicted with 96.65% accuracy.

Although the accuracy is higher that the positive class percentage. The False Positive is higher than False Negative. Ideally we would like False Positive to be as low as possible.

GridSearchCV gave the following as the best parameters:

* 'learning_rate': 0.3
* 'max_depth': None
* 'n_estimators': 15
Using the hyperparameter values tuned by GridSearchCV, the XGBoost model gave 97.07% accuracy, improving both the precision and recall for both positive and negative class.

## XGBoost with additional features: AttendancePercentage and ContactHours
![image](https://github.com/user-attachments/assets/a30b6850-b56a-43c5-8208-182a06a528d6)
![image](https://github.com/user-attachments/assets/a1ce25e0-89e5-4777-b080-6f6fc70450d3)

![image](https://github.com/user-attachments/assets/1e44355d-e72c-4700-a9cc-407658875a81)
![image](https://github.com/user-attachments/assets/be1785b3-dd99-4aa4-b0ca-d9134cf1d7b4)

## Plot feature importance
![image](https://github.com/user-attachments/assets/d46b25e2-4032-4064-8c6f-6230f07a2ded)

XG Boost with additional features

* XG Boost Basic Model Accuracy: 0.9801762114537445
* XG Boost tuned Model Accuracy: 0.9784140969162995

The XGBoost with additional features predicted with 98.01% accuracy.

The False Positive is still higher than False Negative although the absolute numbers have reduced compared to models with reduced features.

GridSearchCV gave the following as the best parameters:

* 'learning_rate': 0.6
* 'max_depth': 20
* 'n_estimators': 25
Using the hyperparameter values tuned by GridSearchCV, the XGBoost model gave 97.84% accuracy, resulting in slight degradation in the precision and recall for the negative class.


## Neural Network model
![image](https://github.com/user-attachments/assets/c022131a-7ef3-4c88-bccf-464aad35b5ce)

![image](https://github.com/user-attachments/assets/d3e2dff6-4641-4143-b570-92dd7edbdee8)
![image](https://github.com/user-attachments/assets/ef532f1f-ed22-42ab-9c31-b915bc59c92e)

![image](https://github.com/user-attachments/assets/d78355ae-53b3-4d2f-89e4-36445d037850)

### Neral Network Hyperparameter tuning
![image](https://github.com/user-attachments/assets/295ed469-a0f7-4416-823b-0533b1755fa4)
![image](https://github.com/user-attachments/assets/377dae9c-dab1-4a6a-b62f-e3d5a18d8f8d)
![image](https://github.com/user-attachments/assets/5cdcf0eb-b94c-4b6b-965e-623e064fda74)
![image](https://github.com/user-attachments/assets/826ae7e8-c46b-4659-8139-bd5d300915c7)

* Neural Network basic Model Accuracy: 0.9789889454841614
* Neural Network tuned Model Accuracy: 0.9792965650558472

### Neural Network model with additional features
![image](https://github.com/user-attachments/assets/3b1e2218-61e0-433e-8729-d70e06f7817d)

![image](https://github.com/user-attachments/assets/aacabf3a-835b-432e-9602-7aefa33ed31e)
![image](https://github.com/user-attachments/assets/b94018e0-0eb8-4446-bea3-92d2c1700ac0)
![image](https://github.com/user-attachments/assets/84d90034-f2eb-4ce4-85d2-757d0d9490df)

## With Additional features

* Neural Network basic Model Accuracy: 0.986534833908081
* Neural Network tuned Model Accuracy: 0.9844355583190918

The basic model of Neural Network with additional features predicted with 98.65% accuracy.

The False Positive is lower than False Negative which is good as we would like True Negative to tend towards 100%

Hyperparameter tuning gave the following as the best parameters:

* optimizer: adam
* num_hidden_layers: 2
* num_neurons: 128

Using the hyperparameter values, the Neural Network model gave 98.44% accuracy, resulting in slight degradation in the recall for the negative class.

# Conclusion

Comparing XGBoost and Neural Network, the latter performed slightly better on this dataset, but the difference is less than a percentage point. Therefore, I would conclude they are very similar. Additionally, both models performed better with the 2 additional features.

Similarly, the performance of both models seemed to degrade after hyperparameter tuning. Again, the difference is less than a percentage point and therefore hyperparameter tuning is still beneficial in terms of performance improvement and reduced computational cost. It also ensures the models are not overfitted.

We were able to determine the features that were important in making the prediction using XGBoost. CreditWeightedAverage seems to make much higher impact than any other features. ContactHours is in the top 15 features confirming its importance as confirmed by the 2 models’s improvement after the 2 additional features were added.

The models could be tuned better with tuning additional hyperparameters if time allowed. However, as the accuracy is already above 98% the models are already near optimal as we have observed that there are good number of outliers in the data. The model could be tuned to predict the negative class more accurately at the cost of overall accuracy as this would ensure that institutions could target most, if not all, students who are likely to drop out.

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

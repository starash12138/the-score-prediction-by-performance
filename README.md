### the-score-prediction-by-performance

**Chen Xu**  

#### Abstract
This project aims to build a student performance prediction model using machine learning techniques, analyzing the impact of Exam_Score such as Hours_Studied and Parental_Involvement on exam scores.  
Through data preprocessing, model training, and evaluation, the project validates the improvement of feature engineering on prediction accuracy and identifies key influencing factors.  
Future work may explore cross-disciplinary data integration to optimize model generalization.  

#### Rationale
The prediction of student performance is of vital practical significance for the optimization of educational resource allocation and personalized teaching support.   
Precisely identifying the key factors that influence academic results can help educators intervene in learning risks proactively, improve teaching efficiency,  
and provide students and parents with a scientific reference for learning planning.  

#### Research Question
1、What key factors (e.g.,Hours_Studied, Attendance, Access_to_Resources) are significantly related to student Exam_Score?   
2、How do machine learning models quantify the impact of these factors and predict scores?  

#### Data Sources
A dataset of 6,607 records is used, covering 17 features (e.g., Sleep_Hours，Previous_Scores,Motivation_Level...), with exam scores as the target variable.  
The dataset is collected by Lai Ng. in the Kaggle website.  

#### Methodology
1、Data Preprocessing
（1）Categorical variables (e.g., Internet_Access，School_Type) were encoded using one-hot encoding to convert them into binary features, ensuring no assumed order between categories.  
（2）Features significantly correlated with exam scores (e.g.Hours_Studied, Attendance) were selected through correlation analysis.  
（3）Outliers (e.g.samples with study hours > 40 hours) were removed to clean the dataset.  
2、Model Construction  
（1）Base Model: A Gradient Boosting Regressor was employed to capture non-linear relationships in the data.  
（2）Cross-Validation: 5-fold stratified cross-validation was applied to evaluate model stability across different data splits.  
3、 Evaluation Methods  
（1）Performance Metrics: The model was assessed using R² (coefficient of determination) and Mean Squared Error (MSE) to measure prediction accuracy and error magnitude.  
（2）Visual Analysis:  
 — Learning Curves: Plots were generated to analyze model performance with varying training sample sizes, identifying underfitting or overfitting trends.  
 — Validation Curves: These were used to study how hyperparameters (e.g., tree depth) affected model performance, guiding parameter tuning.  
 
#### Results
(1)Key Factors：Hours_Studied, Attendance, Previous_Scores, and Tutoring_Sessions are positively correlated with exam scores,   
while factors like Motivation_Level and Learning_Disabilities have weaker impacts.  
(2)Model Performance：The optimized model achieves an R² of 0.92 and an MSE of 0.84 on the test set. Learning curves show reduced gaps between training and validation scores,   
indicating lower overfitting risks.  
(3)Visual Insights：Bubble charts show high-scoring samples concentrate in the 10-30 study hours range, validating the importance of "moderate study duration."  

#### Next steps  
Explore ensemble learning methods (e.g., combining random forests and GradientBoostingRegressor) to improve prediction accuracy;  
Conduct educational intervention experiments to validate the practical effects of model recommendations (e.g., targeted tutoring sessions).  

#### Conclusion
1、Positive Results  
（1）High Model Performance: The predictive model achieved an R² of 0.92 and an MSE of 0.84, demonstrating exceptional accuracy in explaining exam score variability and minimizing prediction errors.  
This indicates strong effectiveness in capturing relationships between input features (e.g.Hours_Studied, Attendance) and student performance.  
（2）Actionable Insights: Key factors like study hours (10–30 hours correlated with high scores), previous academic performance, and tutoring sessions were identified as significant predictors,   
providing clear targets for educational interventions.  
（3）Visual Validation: Bubble charts and learning curves visually confirmed trends, such as the concentration of high scores within optimal study hour ranges, enhancing the credibility of findings.  
 
2、Negative Results  
（1）Missing Dynamic Features: Real-time data on student behavior (e.g., classroom engagement, mental health) and contextual factors (e.g., family emergencies) are absent,   
limiting the model’s ability to adapt to sudden changes.  
（2）Interpretability challenges: As a black-box model, gradient boosting lacks transparency in explaining feature interactions   
(e.g.,how learning time and parental involvement work together to affect scores), hindering understanding of the model  

3、Cautions  
(1)Avoid Overgeneralization:Don't assume model performance will replicate in populations with different educational structures or cultural contexts without validation.  
(2)Continuous Monitoring: Regularly retrain the model with updated data to account for changes in curriculum or students  
(3)Limitations in Causality: Correlations identified do not imply causation (e.g., high study hours may correlate with good scores but not guarantee them).   
Avoid framing predictions as deterministic outcomes.  

### Bibliography   
Tan, Pang-Ning, Michael Steinbach, Anuj Karpatne, and Vipin Kumar. Introduction to Data Mining. 2nd ed. Pearson, 2018.  


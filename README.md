### Project Title: Semiconductor Manufacturing Process Classification

**Xin Li**

#### Executive summary

Nowadays, our world is driven by semiconductor chips that power everything from our mobile phones to cars. Being one of the most technologically and highly complicated processes, semiconductor manufacturing have long been studied using machine learning models to increase production.

In this study, semiconductor data collected from manufacturing line are analyzed to detect wafer defects. Five different classification models are constructed to predict the faults during wafer fabrication process. These predictive models are compared againest each other to build the best model for wafer defect predication.

#### Rationale
In modern semiconductor industry, semiconductor wafers undergo a series of processing tools where their electric and physical characteristics can be altered. A wafer is a thin slice of material usually in a round shape with a mirror-like finish surface.

During wafer fabrication, various types of defects are commonly introduced through the processes of crystal growth, oxidation, diffusion, lithography, etching, deposition, and annealing. At each manufacturing stage, large number of monitoring sensor readings are collected and analyzed. Process engineers need to monitor any unusual defect distribution and take appropriate actions for the corresponding problems. The classification of wafer defect using machine learning models can provide critical information for yield management and facility maintenance.

In addition, the sensor readings collected are not equally valuable. While some of them may contain useful data, others could be just noise. Machine learning techniques of feature selection through dimensionality reduction can be adopted the obtaining of most relevant features to assist process engineers to figure out quickly the root cause of the wafer defects to increase productivity.

#### Research Question
The research question this study intends to answer is to find the best way to choose the important monitoring sensor readings and use them to classify the defects. It covers two subjects.

The first subject is how to construct the best machine learning model to effectively predict the occurrence of the wafer defects using the sensor readings collected from the manufacturing process. Different predictive models will be explored in order to achieve the best performance of classification.

The second part is how to select important sensor readings to allow the process engineers to identify of the root causes of the defects in order to manage yield and achieve higher profit.

#### Data Sources
The data source I chose to use in this study is from the UCI SECOM Dataset of the link: https://www.kaggle.com/datasets/paresh2047/uci-semcom

This semiconductor dataset contains real sensor readings collected from manufacturing process by at various monitoring and measurement points. These attributes are multivariate in nature which includes total of 591 attributes of 1567 instances.

The target to be classified is inbalanced with 1463 passes and 104 fails, where –1 corresponds to pass and 1 corresponds to fail. The time stamp corresponds to each test points are also included.

#### Methodology
(1) Data Pre-processing

The initial data pre-processing takes multiple steps. 

Firstly, the 'Time' column is dropped to focus on processing sensor readings data. Secondly, columns with more than 20% missing values are dropped. Thirdly, the remaining missing values are filled with the column average.

(2) Feature Selection

For feature selection, various dimensionality reduction techniques are applied to reduce the number of data columns. After calculating the correlation matrix, the less correlated features are dropped. After that, the low variance features are dropped by using VarianceThreshold() method.

Next, the train-test data are split to make 30% of test data. Finally, data normalization is performed using StandardScaler() to bring the features into the same range before the modeling.

(3) Model Construction

During model construction, five different models of Logistic Regression, SVM, KNN, Decision Tree and Naive Bayes are constructed and analyzed. These test MSE and test accuracy of these five models are examined and compared. Among these models, the SVM and Naive Bayes out-performed others due to their lower test MSE and higher test accuracy.


#### Results
Achieving both objectives of dimensionality reduction and classification are crucial to identify the root cause of the chip yield loss in the semiconductor manufacturing process. In this study, the following results are achieved:

(1)	The dimensionality reduction is conducted during feature selection, the high-dimensional 591 features were transformed into lower-dimensional space of 96 features while still preserving the essence of the original data.

(2)	In the classification phase, five of models of Logistic Regression, SVM, KNN, Decision Tree and Naive Bayes were constructed to figure out the best classification to predict the wafer defects using the selected features.

(3)	The ROC curve shows the performance of the selected classification model. It can be further improved using methods that are listed in the “Next Steps”.

(4)	The permutation importance shows the top 10 features that are most important to the identify the “Pass/Fail” rate are { '589', '129', '63', '64', '68', '71', '88', '90', '115', '117'}. These features can assist the process engineers to quickly determine the key sensor signals that are contributing to yield loss. 


#### Next steps
For next steps, I plan to make improvements from four different areas to achieve higher model performance:

(1) Refine feature selection by exploring other techniques of vector classifier and PCA.

(2) Adopt over-sampling methods such as SMOTE to handle imbalanced data classification

(3) Enhance classification models by examining other classifiers such as random forest 

(4) Clean code and make the work presentable for technical and non-technical audiences

#### Outline of project

https://github.com/xinli-git-01/Capstone-Project-20.1


##### Contact and Further Information

Email: xinli.sf@gmail.com
Phone: 1-408-921-6312
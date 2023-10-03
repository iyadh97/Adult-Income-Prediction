# **Adult Income Dataset** 
Mohamed Iyadh Tajouri 

![image](https://github.com/iyadh97/Project-2/blob/a87ee9aca194d700fe9c60c8c79c9675288f1edd/Dataset_Adult%20Income/Ressources/word-cloud-3269304_1280-1.png)

## **Context**

The central business problem addressed by this dataset is to empower financial institutions, businesses, and researchers to make data-driven decisions by predicting whether an individual's annual income exceeds $50,000 based on a set of demographic and employment-related features.

## **Background and motivation**

**The prediction task is to determine whether a person makes over $50K a year given their demographic variation. To achieve this, several classification techniques are explored and the random forest model yields to the best prediction result.. This predictive capability can have a transformative impact on various sectors in several countries around the world.**

Data Source :
*  [overview of the data](http://archive.ics.uci.edu/ml/machine-learning-databases/adult/adult.data)
  
Click [here](https://www.kaggle.com/datasets/wenruliu/adult-income-dataset?resource=download) to download the data from kaggle 

Click [here](https://archive.ics.uci.edu/dataset/2/adult) to download the data from the UC irvine Machine Learning Repository  

  
### **Data Description :** 
* This dataset, a well-known extract from the 1994 Census bureau database by Ronny Kohavi and Barry Becker, holds great significance across multiple domains. Its importance lies in its capacity to shed light on income distribution and disparities, offering valuable insights that can drive progress in various fields. 
This dataset serves as a versatile tool that can catalyze advancements in several critical domains.
* The importance of census statistics :
The census is a special, wide-range activity, which takes place once a decade in the entire country. The purpose is to gather information about the general population, in order to present a full and reliable picture of the population in the country - its housing conditions and demographic, social and economic characteristics. The information collected includes data on age, gender, country of origin, marital status, housing conditions, marriage, education, employment, etc.

This information makes it possible to plan better services, improve the quality of life and solve existing problems. Statistical information, which serves as the basis for constructing planning forecasts, is essential for the democratic process since it enables the citizens to examine the decisions made by the government and local authorities, and decide whether they serve the public they are meant to help.

Read more: Use of [Census Data](https://www.statcan.gc.ca/en/census/census-engagement/about/how-data-used)


### **Data Dictionary**
---

**1. Categorical Attributes**

* workclass: (categorical) Private, Self-emp-not-inc, Self-emp-inc, Federal-gov, Local-gov, State-gov, Without-pay, Never-worked.
  * Individual work category

* education: (categorical) Bachelors, Some-college, 11th, HS-grad, Prof-school, Assoc-acdm, Assoc-voc, 9th, 7th-8th, 12th, Masters, 1st-4th, 10th, Doctorate, 5th-6th, Preschool.
  * Individual's highest education degree

* marital-status: (categorical) Married-civ-spouse, Divorced, Never-married, Separated, Widowed, Married-spouse-absent, Married-AF-spouse.
  * Individual marital status

*  occupation: (categorical) Tech-support, Craft-repair, Other-service, Sales, Exec-managerial, Prof-specialty, Handlers-cleaners, Machine-op-inspct, Adm-clerical, Farming-fishing, Transport-moving, Priv-house-serv, Protective-serv, Armed-Forces.
  * Individual's occupation

* relationship: (categorical) Wife, Own-child, Husband, Not-in-family, Other-relative, Unmarried.
  * Individual's relation in a family

* race: (categorical) White, Asian-Pac-Islander, Amer-Indian-Eskimo, Other, Black.
  * Race of Individual

* sex: (categorical) Female, Male.
* native-country: (categorical) United-States, Cambodia, England, Puerto-Rico, Canada, Germany, Outlying-US(Guam-USVI-etc), India, Japan, Greece, South, China, Cuba, Iran, Honduras, Philippines, Italy, Poland, Jamaica, Vietnam, Mexico, Portugal, Ireland, France, Dominican-Republic, Laos, Ecuador, Taiwan, Haiti, Columbia, Hungary, Guatemala, Nicaragua, Scotland, Thailand, Yugoslavia, El-Salvador, Trinadad&Tobago, Peru, Hong, Holand-Netherlands.
  * Individual's native country

**2. Continuous Attributes**
 
* age: continuous.
  * Age of an individual

* education-num: number of education year, continuous.
  * Individual's year of receiving education

* fnlwgt: final weight, continuous.
The weights on the CPS files are controlled to independent estimates of the civilian noninstitutional population of the US. These are prepared monthly for us by Population Division here at the Census Bureau.


* capital-gain: continuous.

* capital-loss: continuous.
  
* hours-per-week: continuous.
  * Individual's working hour per week

**This shows that we have 48842 observation and 15 attributes including target attribute(income).**

## Exploratory Data Analysis:

![image](https://github.com/iyadh97/Project-2/blob/a87ee9aca194d700fe9c60c8c79c9675288f1edd/Dataset_Adult%20Income/Ressources/hoursperweek.png)

**Description about the distribution:**

* In this data the hours per week attribute varies within the range of 1 to 99.
* Most people work 30-40 hours per week, they are roughly 27,000 people. There are also few people who works 80-99 hours per week and some less than 20 which is unusual. 75 percentage of the people spend 45 or less working hours per week.

![image](https://github.com/iyadh97/Project-2/blob/a87ee9aca194d700fe9c60c8c79c9675288f1edd/Dataset_Adult%20Income/Ressources/age.png)

**Description about the distribution:**

* "age" attribute is not symmetric.
* It is right-skewed(But this is totally fine as younger adult earn wages not the older ones) Minimum and Maximum age of the people is 17 and 90 respectively. The mean age is around 38 years.
* This dataset has fewer observations(868) of people's age after certain age i.e. 70 years.

![image](https://github.com/iyadh97/Project-2/blob/a87ee9aca194d700fe9c60c8c79c9675288f1edd/Dataset_Adult%20Income/Ressources/educ.png)

**Description about the distribution:**

* There are 6 unique categories present in the education attribute(after modification).

* HighGrad has 32.49% of all the education attribute.
* HighGrad (15573) has the maximum number of observations followed by CommunityCollege (14324) and Bachelors(7803).

* Doctorate has the minimum number with only 562 having a doctorate (1.17%).
  

![image](https://github.com/iyadh97/Project-2/blob/a87ee9aca194d700fe9c60c8c79c9675288f1edd/Dataset_Adult%20Income/Ressources/incomebyeduc.png)

**Description about the distribution:**

* Despite the fact that most of the categories fall under the HighGrad but the interesting thing is only 5.17% of all people belong to the income group 1(i.e. earns more than 50k), surprisingly less than the Bachelors which is 6.75%.
* There are only few categories in "education" attribute whose percentage to fall under income group 1 is greater than the falling under income group 0. These are masters and doctorate.

* **We can also infer that higher education may provide better earnings.**

![image](https://github.com/iyadh97/Project-2/blob/a87ee9aca194d700fe9c60c8c79c9675288f1edd/Dataset_Adult%20Income/Ressources/incomebygender.png)

**Description about the distribution:**

* For "female" earning more than 50k is rare with only 3.63% of all observations.

* But for male, 20.28% of all people earn more than 50k.

## Maching Learning Using the Following Models:

* RandomForestClassifier
* Logistic Regression
* K-Nearest Neighbors (KNN) 

## Best Model Evaluated & Results:

![image](https://github.com/iyadh97/Project-2/blob/290545138dce8ef45d184403792fdcadaf99fab0/Dataset_Adult%20Income/Ressources/RF_Res.png)

> **Based on the evaluation metrics of the tuned models, it appears that the Random Forest Classifier outperforms both the Logistic Regression and K-Nearest Neighbors (KNN) models. The Tuned Random Forest Classifier achieved the highest accuracy of approximately 87%, coupled with a balanced recall and precision, making it a strong choice for this classification task. It exhibits an impressive ability to correctly predict both income groups (<=50K and >50K) while maintaining good overall precision and recall scores.**

* **While all models exhibit room for improvement, the Random Forest Classifier demonstrates the most promising results among the three, offering a robust foundation for further refinement and optimization in subsequent analyses and**

## Final recommendations based on the results :

**In conclusion, this dataset provides a valuable foundation for addressing income-related challenges across various sectors. Based on our analysis, we recommend the following:**
---

**Enhance Data Quality:** Continuously monitor and improve data quality to ensure accurate and reliable predictions.

**Refine Feature Engineering:** Invest in further feature engineering to extract more meaningful insights from the data, potentially incorporating additional external data sources to enrich the dataset.

**Fine-Tune Models:** Experiment with different machine learning algorithms, hyperparameter tuning, and model ensembles to improve prediction accuracy.

**Looking ahead, there are several avenues for enhancing the effectiveness of this project:**
---

**Advanced Models:** Explore the use of advanced machine learning and deep learning models to further improve prediction accuracy.

**Interpretability:** Models like Random Forest, which offer interpretability, are preferred in contexts where stakeholders need to understand the reasons behind predictions.applications.

## For Further Information
For any additional questions, please contact:

**Mohamed Iyadh Tajouri**

* mohamediyadhtajouri@gmail.com

And this is my [LinkedIn](https://www.linkedin.com/in/mohamed-iyadh-tajouri-251527181/)

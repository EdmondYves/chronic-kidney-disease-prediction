**Project Summary: Chronic Kidney Disease Prediction through supervised machine learning model**

**Project Overview**

Chronic kidney disease is a pathology that affects the kidney, rendering it inefficient or completely unable to filter the blood passing through it. In this practicum, I will investigate the likelihood of an individual to suffer from chronic kidney disease, in other words, I will attempt to predict through machine learning modeling the odds of an individual being diagnosed with the disease based on certain factors.

**Contents**

1. Problem or Situation 
2. Research Question 
3. The Data (Dataset)
4. Methodology 
5. Results
6. Model Evaluation
7. Conclusions

**1. Problem or Situation**

In this project, my goal is to look at the factors that could be indicative of kidney failure and predict the likelihood of someone suffering from the disease. I approach the problem from two angles. I first looked at “Factors to be taken seriously at home” and then explored “Factors from a physician perspective”. I used a copy of the "kidney_disease" dataset from the data repository of the University of California Irvine (UCI).

**2. Research Question**

- What are the factors increasing the likelihood of an individual 
   to suffer from ckd (chronic kidney disease)? 

- Predict the odds of a  random individual to suffer from ckd.

**3. The Data (Dataset)**

**The Dataset**
For this project, I will be using a copy of the “kidney_disease” dataset from the University of California Irvine (UCI) that can be found at:  
https://archive.ics.uci.edu/ml/datasets/chronic_kidney_disease
It is a multivariate dataset made of real data. It has 400 Instances and 25 attributes. To increase the accuracy of the model that will be used for the prediction, these missing values will need special treatment. It is worth mentioning that all the attributes of the dataset are not “equal” regarding the question that is being investigated in this project. The one with no direct relevancy to the model will be eliminated to improve the performance of the algorithm. 

**The Data**
1) age: Age(numerical) - age in years
2) bp: Blood Pressure(numerical) bp in mm/Hg
3) sg: Specific Gravity(nominal) sg - (1.005,1.010,1.015,1.020,1.025) concentration of particles in urine (density of urine compared with the density of water)
4) al: Albumin(nominal)al - (0,1,2,3,4,5)
5) su: Sugar(nominal) su - (0,1,2,3,4,5)
6) rbc: Red Blood Cells(nominal) rbc - (normal, abnormal)
7) pc: Pus Cell (nominal)pc - (normal, abnormal) pus cells (White blood cells) in urine (Pyuria) are signs of infection, it is significant if there are more than 4 pus    cells/HPF in a centrifuged urine sample.
8) pcc: Cell clumps(nominal)pcc - (present, notpresent) Large clumps of WBCs are typically observed when there is inflammation or bacterial infections of the renal and    urinary tract.
9) ba: Bacteria(nominal) ba - (present, notpresent)
10) bgr: Blood Glucose Random(numerical) bgr in mgs/dl
11) bu: Blood Urea(numerical) bu in mgs/dl
12) sc: Serum Creatinine(numerical) sc in mgs/dl
13) sod: Sodium(numerical) sod in mEq/L
14) pot: Potassium(numerical) pot in mEq/L
15) hemo: Haemoglobin(numerical) hemo in gms
16) pcv: Packed Cell Volume(numerical) Hematocrit (HCT) and packed cell volume (PCV) are used to measure red blood cell mass. An increase in red blood cell mass is equivalent to erythrocytosis and a decrease indicates an anemia.
17) wc: White Blood Cell Count(numerical) wc in cells/cumm
18) rc: Red Blood Cell Count(numerical) rc in millions/cmm
19) htn: Hypertension(nominal) htn - (yes, no)
20) dm: Diabetes Mellitus(nominal) dm - (yes, no)
21) cad: Coronary Artery Disease(nominal) cad - (yes, no)
22) appet: Appetite(nominal) ppet - (good, poor)
23) pe: Pedal Edema(nominal) pe - (yes,no)
24) ane: Anemia(nominal)ane - (yes,no)
25) classification: Class (nominal) class - (ckd, notckd)

**4. Methodology**
The approach used to solve this problem will consist of different steps: 

1) Clean and prepare the data.

The cleaning and the preparation of the data were completed by:

- Identifying NaNs with the use of the isnull() function.
- Replacing categorical NaNs with the mode.
- Replacing numerical NaNs with the MICE (Multivariate Imputation by Chained Equations).

2)  Exploratory data analysis and correlation testing.

Pearson's correlation methods led to finding a strong correlation between these variables:

- Determining factors from a physician’s perspective:
Chronic Kidney Disease and Specific Gravity: corr = -0.7
Chronic Kidney Disease and Albumin: corr = +0.6
Chronic Kidney Disease and Hemoglobin (gms): corr = -0.73
Chronic Kidney Disease and Packed Cell Volume: corr = -0.69

- Determining Factors to be taken seriously at home: 
(May point towards the disease pending further analysis)
Chronic Kidney Disease and Hypertension: corr = -0.59
Chronic Kidney Disease and Diabetes Mellitus: corr = +0.56
Chronic Kidney Disease and Appetite: corr = -0.39
Chronic Kidney Disease and Pedal Edema: corr = +0.38
Chronic Kidney Disease and Anemia: corr = +0.33

**Determining Factors to be taken seriously at home:** 

**Distribution of the target variable**

![image](https://user-images.githubusercontent.com/122956155/223883064-c15b580b-81d8-43cb-b2ce-311552d81de4.png)

The interpretation of the above graph showed us that more people suffered from chronic kidney disease compared to the "healthy". In other words, among all the patients, the number of individuals that were found sick from ckd was superior to the number of individuals that did not suffer from the disease. Precisely, among a total of 400 individuals, 250 ended up being diagnosed with the disease compared to 150 that were found not ill.

**Chronic Kidney Disease and Anemia: corr = +0.33**

**Distribution**

![image](https://user-images.githubusercontent.com/122956155/223883106-11edaa1c-ce2b-406c-b6c4-e52076ffab66.png)

The "Anemia" distribution above revealed to us that among the 400 individuals, 16.25% of them were anemic while 83.75% did not have the pre-existing condition of anemia.

**CKD vs Anemia**

![image](https://user-images.githubusercontent.com/122956155/223883004-5b51a7bd-379f-4bb7-8f19-698d52ea61fa.png)

The result of the graph speaks for itself. Individuals suffering from Anemia as a pre-existing condition are shown to also be diagnosed with ckd while the ones with no anemia tend not to be diagnosed with ckd. This indicates to us that anytime a relative is diagnosed with anemia, even before seeing a doctor we should keep in mind that this may also be an indication of a kidney problem.

**Chronic Kidney Disease and Pedal Edema: corr = +0.38**

Let us look at how the "Pedal Edema" population is distributed.

![image](https://user-images.githubusercontent.com/122956155/223917593-fe51ba2b-b09a-48bd-8d92-042be9e99e66.png)

The "Pedal Edema" distribution above revealed to us that among the 400 individuals, 12.5% of them suffered from lower extremities swelling while 87.5% did not have the condition.

Now, let us draw the "Chronic Kidney Disease" vs "Pedal Edema" diagram, I will also use a factor plot for this diagram.

![image](https://user-images.githubusercontent.com/122956155/223917744-6f9bad83-d782-480e-8323-25b402de08e2.png)

The result of the above graph shows us that the likelihood of someone suffering from ckd is very high when the person is experiencing pedal edema. Noticing the swelling of the lower extremities should be a sign that the patient's kidney may be starting to fail.

**Chronic Kidney Disease and Appetite: corr = -0.39**

Let us look at how the "Appetite" population is distributed.

![image](https://user-images.githubusercontent.com/122956155/223917915-f3277339-d724-442a-b1f3-d32e70a85b16.png)

The distribution above shows us that about 18.75% of our total population experienced a lack of appetite while 81.25% had a normal appetite.

![image](https://user-images.githubusercontent.com/122956155/223918037-686559f5-2407-421c-891a-5e006dc23363.png)

Appetite appears to be related to the ckd in the sense that the less appetite a patient may be experiencing the more likely he may be starting to suffer from ckd. Here it is important to note that a factor such as appetite does not have too much weight when taken individually but will be of great importance when associated with other actors with a strong correlation with the target variable.

**Chronic Kidney Disease and Diabetes Mellitus: corr = +0.56**

![image](https://user-images.githubusercontent.com/122956155/223918202-9a6c53f7-c109-41b5-9689-d3a3f9d63243.png)

The "Diabetes Mellitus" distribution graph displays 36.5% of the total population suffering from diabetes while 63.5% do not have diabetes.

![image](https://user-images.githubusercontent.com/122956155/223918307-bdc3228a-dcbd-4c62-883f-5e2b963c2aec.png)

People with diabetes mellitus are more likely to suffer from ckd while individuals that do not have diabetes mellitus are less prone to suffer from ckd.

**Chronic Kidney Disease and Hypertension: corr = -0.59**

![image](https://user-images.githubusercontent.com/122956155/223918551-15e53f5b-7fdf-47fe-a2c5-a84bd979dd5f.png)

37 % of the total population suffered from hypertension while 63 % did not have hypertension.

![image](https://user-images.githubusercontent.com/122956155/223918606-b72118a0-3fe6-497b-a8ec-ad9bce732241.png)

Being hypertensive dramatically increases the odds of also suffering from ckd. This will be another factor to look closely at while suspecting someone to suffer from ckd. In association with the other factors that were previously explored, hypertension should be considered while evaluating the chances of a patient experiencing kidney failure.

**Determining factors from a physician's perspective:**

Chronic Kidney Disease and Specific Gravity: corr = -0.7

![image](https://user-images.githubusercontent.com/122956155/223918756-c73ab655-4f60-4b8f-b286-bb2fcbbd3562.png)

The graph above shows us that Specific Gravity is concentrated around four main values. Let us draw a different graph that will enable us to visualize these values.

![image](https://user-images.githubusercontent.com/122956155/223919524-a0c0b1a2-ed9c-49f2-8ca1-1dade780eba2.png)

![image](https://user-images.githubusercontent.com/122956155/223919559-8672aaac-53b6-4160-af8b-8f2bdf2282e7.png)

![image](https://user-images.githubusercontent.com/122956155/223919635-1a84157f-2c95-451c-a04e-eaa7dfeef329.png)

The plots presented in the above three graphs show us that the lower the value of the "specific gravity" the higher the chances to suffer of ckd are.

**Chronic Kidney Disease and Albumin: corr = +0.6**

![image](https://user-images.githubusercontent.com/122956155/223919803-497e7150-4ecf-4ee5-95d6-d03e0dd05c50.png)

![image](https://user-images.githubusercontent.com/122956155/223919832-c6aec0b8-9656-4dc6-ac84-a477c94dd905.png)

![image](https://user-images.githubusercontent.com/122956155/223919848-2a105e3d-a1a7-4dd3-aec4-756ed775aead.png)

In the three graphs above, it is evident to note that the higher the values of the Albumin are, the higher the odds of the patient to suffer of ckd is. This should be one of the values to be used by the physician in association with other parameters to establish a diagnostic of ckd.

**Chronic Kidney Disease and Hemoglobin (gms): corr = -0.73**

![image](https://user-images.githubusercontent.com/122956155/223919940-fd678365-4710-432f-b777-1bf7d4295568.png)

As we can notice, categorical plots are great for binary values as we can use a count to group the values into only two categories. Hemoglobin values are not binary values and we should use a scatter plot for example for a better representation.

![image](https://user-images.githubusercontent.com/122956155/223920083-885fd98a-1ae4-47d5-b5ed-f38b5e8bea60.png)

![image](https://user-images.githubusercontent.com/122956155/223920139-09bc208d-1a0a-435e-9429-d92ef9dfecfe.png)

![image](https://user-images.githubusercontent.com/122956155/223920200-d378dca9-3996-45d8-b212-4ccd935fcccc.png)

These three graphics put in evidence the behavior of hemoglobin values compared to the odds of a patient to suffer from ckd. The higher the values of the hemoglobin the lower the chances of the patient getting ill with ckd, respectively, the lower the values of the hemoglobin, the higher the chances of the patient to suffer from the disease. This Can be understandable because the kidney plays a critical; role in the synthesis of red blood cells through a hormone that it produces (erythropoietin). It makes sense that a sick kidney will no longer produce the hormone efficiently thus red blood cells will not be produced at an optimal level necessary to guarantee great values for hemoglobin.

**Chronic Kidney Disease and Packed Cell Volume: corr = -0.69**
 
![image](https://user-images.githubusercontent.com/122956155/223920479-6dfff419-3e6b-4032-9911-68bbf3eeb400.png)

![image](https://user-images.githubusercontent.com/122956155/223920559-a83ffd1e-499d-4847-85a0-4f4764624710.png)

![image](https://user-images.githubusercontent.com/122956155/223920618-dc15a702-92d2-4d48-a9f3-3364b177e869.png)

![image](https://user-images.githubusercontent.com/122956155/223920688-15382fe1-b2e1-4e8d-9334-1d6a3e1b2819.png)

The plots above show us that the higher the values of the "Packed Cell Volume" is, the lower the chances of the individual to suffer of ckd, inversely, the lower the value of the "Packed Cell Volume" is the higher the odds of the patient to be diagnosed of ckd. This should be another factor of great interest to the physician while diagnosing ckd in a patient.

**3) Splitting the data into a training and a testing set.** 

 The  “train_test_split” from the Sklearn library was used to split the data at a ratio of  
  (70:30) respectively for the training and testing set.
  
  ![image](https://user-images.githubusercontent.com/122956155/223921782-c9ee2f5c-148d-4727-8ead-52f23d989173.png)

**4) Machine Learning algorithms applied to training and testing sets.**

**4.1 Importing the model.**
The best method to solve these types of classification problems appears to be the logistic regression model.

![image](https://user-images.githubusercontent.com/122956155/223922356-1708adcf-d32a-46be-b34c-98f7cf5c877c.png)

**4.2 Creating an instance of the Model.**

![image](https://user-images.githubusercontent.com/122956155/223922702-da921d82-7b69-4d66-a63e-09ba12d6777e.png)

**4.3 Training the model on the data.**

![image](https://user-images.githubusercontent.com/122956155/223923399-968d1241-9940-40fc-8b92-5ee4dbb86a3b.png)

**Results**

**5.1 Testing the model.**
The model uses the information it learned during the model training process in “4.3” to predict the outcome of the first 10 patients of the testing set.

**0:** The individual suffers from CKD
**1:** The individual does not suffer from CKD

![image](https://user-images.githubusercontent.com/122956155/223924519-60e21ac7-4fea-4718-982f-5c5827cc7712.png)

**5.2 Applying the model on the whole test data set**

![image](https://user-images.githubusercontent.com/122956155/223924832-8cd6697a-5159-4012-9018-44a5742e957b.png)

**Model Evaluation**

**6)  Model accuracy evaluation.**
**6.1. Using the “score” method to evaluate the accuracy of the model.**
The accuracy test is used as a calculation to determine how accurate the model is. 

![image](https://user-images.githubusercontent.com/122956155/223925273-cbf2b668-50a1-4421-b66a-5cb72af564b5.png)

The accuracy was 96.67. This is a good result in my opinion. 

**6.2. Running the data through additional models and ranking all the models.**
Comparing the model with other models to see how it fares.

![image](https://user-images.githubusercontent.com/122956155/223925430-4eeb9fba-8b55-4caa-8764-91e7cae56655.png)

**Conclusion**

**Goal of the project:** 
(finding the most important factors influencing the likelihood of an individual to suffer from chronic kidney disease)

**Two categories of factors were put in evidence.**

![image](https://user-images.githubusercontent.com/122956155/223926940-0256e3fa-15d8-470d-a071-158bfdc38956.png)

- **"LogisticRegression()" used for the predicting phase of the project** (Accuracy score of 96.67)

- **Random Forest** and **Decision Tree** ended up scoring better than regression.

- **Model executed on** **“Factors to be taken seriously at home”** 
(The exact same predictive result was obtained confirming the validity of approaching the problem from both perspectives “home factors” & “hospital factors”)

- **Factors that impacted the accuracy of the model and possibilities of improvement.** (restricted sample data used / missing values)

- **Final thought on the project**  
  (very comprehensive data science project).

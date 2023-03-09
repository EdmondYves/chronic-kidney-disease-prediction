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

**Chronic Kidney Disease vs Anemia: corr = +0.33**

**Distribution**

![image](https://user-images.githubusercontent.com/122956155/223883106-11edaa1c-ce2b-406c-b6c4-e52076ffab66.png)

**CKD vs Anemia**

![image](https://user-images.githubusercontent.com/122956155/223883004-5b51a7bd-379f-4bb7-8f19-698d52ea61fa.png)

**Chronic Kidney Disease vs Pedal Edema: corr = +0.38**



 

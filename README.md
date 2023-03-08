Edmond Tetsuekoue
Regis University
MSDS692 - Data Science Practicum I
January 10, 2023
Problem or Situation
Chronic kidney disease is a pathology that affects the kidney, rendering it inefficient or completely unable to filter the blood passing through it. In this practicum, I will investigate the likelihood of a patient to suffer of chronic kidney disease, in other words, I will attempt to predict through machine learning modeling the odds of an individual being diagnosed with the disease based on certain factors.

Research Question
What is(are) the most critical factor(s) that influence the likelihood of a patient to suffer of chronic kidney disease (ckd)?

The Data
For this project, I will be using a copy of the "kidney_disease" dataset from the data repositoty of the University of California Irvine (UCI). The dataset can be found at: https://archive.ics.uci.edu/ml/datasets/chronic_kidney_disease. This is a multivariate dataset made of real data. It has 400 Instances and 25 attributes. There are missing values in the dataset making it interesting for this project because this will involve a data engineering and pre-processing aspect.

1) Data cleaning and preparation
Importing packages.
import pandas as pd
import numpy as np
#conda install -c https://conda.anaconda.org/plotly plotly
#! pip install plotly
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import plotly.express as px
Next step, loading the data.
By taking a quick look at the file through the editor notepad++, the file appeared to be comma-delimited. Next, let us attempt to open it up with the use of the classical method.

Getting to the file directory !
! dir "C:\Master In Data Science Regis University\MSDS695_X70_Data Science Practicum I"
 Volume in drive C is OS
 Volume Serial Number is 881C-FF69

 Directory of C:\Master In Data Science Regis University\MSDS695_X70_Data Science Practicum I

03/05/2023  06:34 PM    <DIR>          .
01/24/2023  01:13 AM    <DIR>          ..
01/17/2023  07:33 PM           815,914 dataverse_files.zip
03/05/2023  06:30 PM           883,200 Edmond Tetsuekoue Final Practicum 1 Presentation.ppt
01/17/2023  10:47 PM           199,168 Edmond Tetsuekoue Practicum1's Proposal.ppt
01/11/2023  04:47 PM            48,551 kidney_disease.csv
01/17/2023  07:21 PM       328,279,281 U.S._Chronic_Disease_Indicators__CDI_.csv
               5 File(s)    330,226,114 bytes
               2 Dir(s)  24,133,914,624 bytes free
Opening up the file.

# One-Year-Mortality-Prediction
## Overview and Background 
### Goals 
This project is aimed to establish a model to predict the one-year mortality of the patients at their admissions to hospitals with best accuracy based on several aspects of individuals that might be the potential causes of the mortality in a year.

### Importance
For health care, it is usually interesting to know the health outcomes of the patients after the treatments accepted in hospitals. It is essential for health system to keep improving the quality of care in long term aspect by eliminating some reducible factors. Also, knowing the posibility of motality of patients might help doctors to decide on specific treatment plans, such as conserved one or a more risky one. By studying one year motality of population, health care could further enhance the survival of patients with existing technologies.

However, it would a more valuable model for patients. Since some major causes of death are associated with increased ages or some really severe diseases that hospital treatments barely have effects, with this model, specialized course of action could be arranged, and patients or their families and friends could get some preparation in many ways.

### Usage
Using this model, the patients could predict the possibility of mortality in one year based on their age, diagnose, comorbidities, and demographics.

## Data
The data was obtained from the Medical Information Mart for Intensive Care III (MIMIC-III) database. It is released as a relational database comprised of 26 data tables, of which three were used in this project. These are ADMISSIONS, PATIENTS and DIAGNOSES. This databse contains over 58,000 hospital admissions of around 40,000 patients in an 11-year period.

Another data tables was gained from an online sources, which category the ICD_9 codes into different classifications. In this project, I used the most general classification, which separate the ICD_9 codes into 11 groups. Further classification could be also be used for more detailed study.

Data selection in this project is based on features used in previous similar studies, and refined during the process of modification based on current data.

### One Year Mortality 
This part is to calculate the length of days that patients lived after the admission to hospital (if applicable) using 'ADITTIME' in 'ADMISSION' table and 'DOD' in 'PATIENTS" table. Then one-year mortality (positive/negativa) could be assigned to every encouter of patients.

### Ages 
Since increased ages are one of the most important factors to increase the possibility of mortality, in this part, the ages at the admmission for each encounter of patients are calculated, using the 'ADMITTIME' in 'ADMISSION' table and 'DOB' in 'PATIENTS' table. 

As I process the data, it could be seen that some of the patients had the ages over 300 years. Therefore, there might be some invalid data. In order to eliminate these outliers, the upper limit and lower limit for ages were chosen using Q1 and Q3. Finally, this feature is combined with one-year mortality by encounter.

### Age at First Admission
There are researches indicating that the ages at patients' first admission to hospital would also have correlation with the one-year mortality. However, after I collected this information, I found out that this feature has a strong correlation (0.9988) with ages for current admission. This may be because this database only cover the information for 11-year periods. Therefore the data I collected is not accurate. Therefore, I did not use this feature in final analysis.

### Diseases
Diseases is also another major cause of mortality. Here I catecorized the diseases into 11 groups based on classifications from http://www.icd9data.com/.

### Comorbidity
Comorbidity means that more than one disorders happened at the same time. Researches show that comorbidity usually associates with more complicated clinical management and worse health outcomes. In this project, the number of disorders for single encounter was considered as one of the features.

### Demographics
Demographics could also be an important factor. Different regions, incomes, races and so on could impact the one-year mortality in various ways. However, due to the limitation of database, for this project, I only considered gender as one of the features.
- Gender
